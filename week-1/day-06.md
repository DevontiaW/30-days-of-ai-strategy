# Day 06: The Vendor Landscape

## The Idea

The AI vendor market is a mess. Every SaaS company has added "AI-powered" to their marketing. Every consulting firm has an AI practice. And every demo looks incredible — because demos are designed to look incredible.

Navigating this landscape without getting sold requires understanding the market structure, knowing the right questions to ask, and recognizing the red flags that separate genuine capability from repackaged hype.

## In Practice

A manufacturing company evaluated five vendors for a predictive maintenance solution. All five gave impressive demos. All five had case studies. All five claimed 90%+ accuracy.

Here's what actually differentiated them when we dug deeper: Vendor A's "AI" was really a rules engine with a machine learning label. Vendor B had real ML but required six months of data integration before delivering any value. Vendor C had a strong product but was a 12-person startup that might not exist in two years. Vendor D was a major platform player whose predictive maintenance module was an afterthought — powerful but poorly supported. Vendor E had a solid mid-market product with a clear roadmap and reference customers in manufacturing.

We went with Vendor E. Not the most technically sophisticated, not the cheapest, not the biggest brand name. The best fit for this company's actual situation.

## Framework

**The Three Tiers of AI Vendors:**

```
Tier 1: PLATFORM PLAYERS
(Microsoft, Google, AWS, Salesforce)
├── Pros: Scale, integration, not going anywhere
├── Cons: AI is a feature, not their focus. Generic.
└── Best when: You're already on their platform and need "good enough"

Tier 2: SPECIALIZED AI VENDORS
(Domain-specific startups and mid-market companies)
├── Pros: Deep expertise, purpose-built, faster time to value
├── Cons: Viability risk, integration burden, smaller ecosystem
└── Best when: You need best-in-class for a specific use case

Tier 3: CONSULTING + CUSTOM BUILD
(Big 4, boutique AI consultancies, internal teams)
├── Pros: Tailored solution, knowledge transfer, your IP
├── Cons: Expensive, slow, quality varies wildly
└── Best when: Truly unique requirements, competitive differentiator
```

**Red Flags in Vendor Pitches:**

- "Our AI does everything" — No it doesn't. Breadth claims signal a lack of focus.
- Accuracy numbers without context — 95% accuracy means nothing without knowing the baseline, the test conditions, and what "accuracy" measures.
- No reference customers in your industry — If they can't connect you with someone like you, that's a signal.
- Demo uses their data, not yours — The demo always works with clean demo data. Ask for a proof of concept with YOUR data.
- "Just plug it in" integration story — Integration is always harder than the sales deck suggests. Ask for implementation timelines from actual customers, not the sales team.
- Contract requires multi-year commitment before proving value — If they won't let you start with a pilot, ask yourself why.

**Evaluation Checklist:**

1. **Capability fit:** Does it solve your specific problem, not a generic version of it?
2. **Data requirements:** What data does it need? Do you have it? In the right format?
3. **Integration complexity:** How does it connect to your existing systems? Who does the integration?
4. **Time to value:** When do you see first results? Not "potential ROI" — actual working output.
5. **Total cost of ownership:** License + implementation + integration + maintenance + training.
6. **Vendor viability:** How long have they been around? Funding? Revenue? Customer count?
7. **Exit strategy:** What happens if you want to leave? Can you export your data and models?

**Hot take:** The best vendor evaluation tool is a paid proof of concept with your actual data. Not a demo, not a free trial with sample data — a real PoC where the vendor has to make their product work in your environment. If a vendor won't do a paid PoC, they know their product won't survive contact with real-world conditions.

## Your Move

If you're currently evaluating AI vendors (or about to), build a scorecard using the seven evaluation criteria above. Weight each criterion based on what matters most for your org. Then score every vendor on the same card — it forces apples-to-apples comparison and makes the decision defensible to stakeholders.

## Go Deeper

- [Gartner Magic Quadrant reports](https://www.gartner.com/en/research/magic-quadrant) — Industry-standard vendor evaluations. Expensive but thorough. Your CIO probably has access.
- [Deloitte, "Building an AI-Ready Technology Stack"](https://www2.deloitte.com/us/en/pages/deloitte-analytics/articles/building-ai-tech-stack.html) — Good framework for thinking about how vendor choices fit into your broader technology architecture.
