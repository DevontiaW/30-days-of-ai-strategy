# Day 10: Technical Architecture Decisions

## The Idea

You don't need to be an engineer to make good technical architecture decisions. But you do need to understand the trade-offs, because the wrong architecture choice will either blow your budget, lock you into a dead end, or — most commonly — create a "pilot that worked" but can never actually scale.

Here's the uncomfortable truth: the architecture you need for a pilot is NOT the architecture you need for production. And that's fine. Design your pilot architecture to be thrown away. If you design it for permanence from day one, you'll over-engineer it based on requirements you don't actually understand yet. The pilot's job is to prove value and reveal requirements. The production architecture's job is to deliver reliably at scale.

Too many teams try to build the cathedral when they should be building a tent. Tents are fast, cheap, and teach you where the cathedral should go.

## In Practice

A state government agency needed to process 2.3 million documents per year — permit applications, compliance reports, public records requests. Their existing process was 40 people manually reading, classifying, and routing documents. Average turnaround: 14 business days.

The agency's IT department proposed building a custom NLP model trained on their historical documents. They estimated 18 months and $2.1 million, including hiring three ML engineers.

We pushed back. Here's the analysis we ran:

**Was their data truly proprietary?** Partially. The documents used specialized regulatory language, but 80% of the content was standard legal and administrative English. The classification taxonomy (28 document types) was custom, but not complex.

**Did they need real-time processing?** No. Documents arrived in batches (mail, email, uploaded PDFs). A 2-hour processing window was perfectly acceptable.

**What was the actual differentiator?** The routing logic — knowing which of 12 departments should handle which document type, based on content and regulatory requirements. That was institutional knowledge, not an ML problem.

The recommendation: use a cloud AI service (Azure AI Document Intelligence) for text extraction and base classification, then build a lightweight rules engine for the routing logic. Total cost: $340K including integration work. Time to pilot: 8 weeks. Time to production: 5 months.

The custom NLP model would have taken longer, cost more, and required ongoing ML talent they'd struggle to recruit in a government pay band. The cloud service handled the commodity NLP. The custom routing logic — the part that was genuinely unique — was a few hundred lines of business rules, not a neural network.

Eighteen months later, they're processing documents in 26 minutes average. They redeployed 30 of the 40 staff to higher-value review work. And they didn't hire a single ML engineer.

## Framework

### Decision 1: Where Does It Run?

```
┌──────────────┬────────────────┬────────────────────┐
│    Cloud      │   On-Premise    │      Hybrid         │
├──────────────┼────────────────┼────────────────────┤
│ Fast to start │ Full control   │ Best of both       │
│ Scales easily │ Data stays put │ Complex to manage  │
│ Pay-per-use  │ High upfront   │ Two environments   │
│ Vendor dep.  │ Your problem   │ Requires maturity  │
├──────────────┼────────────────┼────────────────────┤
│ Best for:    │ Best for:      │ Best for:          │
│ Pilots, SaaS │ Regulated ind. │ Transition states  │
│ Variable load│ Sensitive data │ Latency-critical + │
│ Startups     │ Air-gapped env │ burst capacity     │
└──────────────┴────────────────┴────────────────────┘
```

**Rule of thumb:** Start in the cloud unless regulation or data sensitivity forces you on-premise. You can always migrate later, but you can't get back the 6 months you spent setting up GPU clusters for a pilot that might not work.

### Decision 2: Build, Fine-Tune, or Call an API?

This is the model selection decision, and it trips up more teams than any other. Use this tree:

```
Is your use case served by a general-purpose model?
│
├── YES → Use an API (OpenAI, Anthropic, Google, etc.)
│         Cost: $0.001-0.06 per request
│         Time to pilot: Days
│         When to reconsider: Volume > 100K requests/day
│                             or latency < 100ms required
│
└── NO → Is your domain data large and labeled?
         │
         ├── YES (>10K labeled examples)
         │   → Fine-tune a foundation model
         │     Cost: $10K-100K + ongoing training
         │     Time to pilot: 4-8 weeks
         │     Best for: Industry-specific language,
         │               custom classification, specialized extraction
         │
         └── NO
             │
             ├── Can you get labeled data in < 3 months?
             │   ├── YES → Label data, then fine-tune
             │   └── NO → Use API + prompt engineering + RAG
             │             (Retrieval-Augmented Generation)
             │             Feed your domain docs as context
             │             80% of "we need a custom model"
             │             cases are actually RAG cases
             │
             └── Is this a novel research problem?
                 └── YES → Build custom (and budget accordingly:
                           $500K+, 12+ months, dedicated ML team)
                           This is rare. Be honest about whether
                           your problem is actually novel.
```

**The uncomfortable reality:** 90% of enterprise AI use cases in 2026 can be solved with API calls plus good engineering. The "we need our own model" instinct is usually a status play, not a technical requirement. Fine-tuning has a legitimate sweet spot, but custom model training from scratch is almost never the right call unless you're a tech company or research institution.

### Decision 3: Batch or Streaming?

Most pilots should start with batch processing. Full stop.

**Batch:** Process data in scheduled chunks (hourly, daily, weekly). Simple. Cheap. Debuggable. If something goes wrong, you rerun the batch. Perfect for: reporting, document processing, periodic predictions, model retraining.

**Streaming:** Process data as it arrives, in real-time. Complex. Expensive. Hard to debug. Necessary for: fraud detection, real-time recommendations, autonomous systems, time-critical alerts.

**The test:** If a 1-hour delay in results is acceptable, start with batch. You can add streaming later when you've proven the value and understand the data patterns. Starting with streaming before you need it is like building a Formula 1 pit crew when you're still learning to drive.

### The ML Pipeline (and the MLOps Tax)

Here's what a production ML system actually looks like:

```
┌─────────┐    ┌───────────────┐    ┌─────────┐    ┌──────────┐
│  Data    │───>│ Feature Store │───>│  Train  │───>│ Validate │
│ Sources  │    │ (transform,   │    │ (model  │    │ (test on │
│          │    │  version,     │    │  fits   │    │  holdout │
└─────────┘    │  serve)       │    │  data)  │    │  data)   │
               └───────────────┘    └─────────┘    └────┬─────┘
                                                        │
                      ┌─────────────────────────────────┘
                      │ Passes validation?
                      ▼
               ┌─────────────┐    ┌───────────┐    ┌──────────┐
               │   Deploy    │───>│  Monitor  │───>│ Retrain  │
               │  (serve     │    │ (drift,   │    │ (trigger │──┐
               │   model     │    │  accuracy, │    │  when    │  │
               │   via API)  │    │  latency) │    │  needed) │  │
               └─────────────┘    └───────────┘    └──────────┘  │
                                                        │        │
                                        ┌───────────────┘        │
                                        ▼                        │
                                  Back to Feature Store ─────────┘
```

**The MLOps tax** is everything after "Deploy." Most teams budget for building and training a model. Almost nobody budgets for keeping it alive:

- **Model monitoring:** Is the model's accuracy degrading? Are the input distributions shifting? ($20-80K/year in tooling and time)
- **Retraining pipelines:** When accuracy drops, you need automated or semi-automated retraining. (Engineering time: 2-4 weeks to build, ongoing maintenance)
- **Data pipeline maintenance:** Source systems change. Schemas drift. New edge cases appear. (The #1 cause of ML system failures in production)
- **Compliance and audit:** Who changed what, when, and why? Model versioning, data lineage, decision logging. (Regulated industries: this alone can equal the model build cost)

**Industry estimate:** For every $1 spent building an ML model, plan to spend $3-5 maintaining it over three years. If that ratio makes your business case collapse, that's important information — better to know now than after you've built it.

### Decision 4: Integration Pattern

How does your AI system connect to everything else?

**API-first:** Your AI capability is a service that other systems call. Clean separation. Easy to swap out the AI component later. Best for most enterprise use cases.

**Embedded:** The AI model runs inside an existing application (e.g., a recommendation engine inside your e-commerce platform). Lower latency, tighter coupling. Best when milliseconds matter.

**Event-driven:** AI processes respond to events in a message queue (new order placed, document uploaded, sensor reading received). Loosely coupled, naturally scalable. Best for high-volume, asynchronous processing.

**Default choice for pilots:** API-first. It's the most flexible and the easiest to tear down when the pilot ends or the approach changes.

## Your Move

For your top AI use case, answer these four architecture questions:

1. **Where does it run?** Cloud, on-premise, or hybrid — and why?
2. **What's your model approach?** API, fine-tune, or custom — walk through the decision tree above with your actual data.
3. **Batch or streaming?** What's the minimum acceptable latency for your results? (Be honest — "real-time" is rarely actually required.)
4. **What's the integration pattern?** How will the AI output reach the people or systems that need it?

Write your answers down. If any of them feel uncertain, that's a signal to run a quick technical spike before committing to a full pilot architecture. A week of exploration now saves months of rework later.

## Go Deeper

- [Google's "Rules of ML"](https://developers.google.com/machine-learning/guides/rules-of-ml) — Practical engineering wisdom from Google's ML team. Rule #1: "Don't be afraid to launch a product without machine learning." Required reading.
- [Sculley et al., "Hidden Technical Debt in Machine Learning Systems" (NeurIPS)](https://papers.nips.cc/paper/2015/hash/86df7dcfd896fcaf2674f757a2463eba-Abstract.html) — The original paper on the MLOps tax. The diagram showing that ML code is the tiny box in the middle of a massive system is worth the read alone.
- [a16z, "Emerging Architectures for LLM Applications"](https://a16z.com/emerging-architectures-for-llm-applications/) — Andreessen Horowitz's breakdown of how modern LLM-based systems are actually architected. Especially useful for the RAG decision branch above.
