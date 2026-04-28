# Day 26: Competitive Moats in the AI Era

## The Idea

Every other LinkedIn post in 2024-2025 announced that some company had "an AI moat." Most of those claims were nonsense. The companies were using AI capabilities available to anyone with an API key. There was no moat. There was technology adoption, sometimes done well — but adoption is not a moat.

Real moats are durable structural advantages competitors can't easily replicate. The classic strategy framework — Hamilton Helmer's *7 Powers* — gives us a sharp tool for asking which AI-era advantages are actually moats and which are temporary capabilities anyone can copy in 18 months.

This matters because most AI investment decisions are pitched as moat-building. *"This will give us a sustainable competitive advantage."* If that's the pitch and it's wrong, you're funding short-term capability building under false pretenses. The work might still be valuable — but you should know what kind of value you're getting.

## In Practice

A mid-market financial services firm spent $12M over two years building a proprietary AI underwriting model. The pitch to the board was "AI moat." The reality, eighteen months in, was that three of their competitors were using off-the-shelf models from major vendors that performed within 5% of the proprietary model on the same task — at a fraction of the operating cost.

The proprietary model wasn't bad. It was better. But the gap wasn't structural. Within another year, the vendor models had caught up. The "moat" turned out to be a 24-month head start, not a sustainable advantage.

The board postmortem asked the right question: where *would* a real moat have come from? Not from the model architecture. The model was always replicable. A real moat would have come from:

- **Proprietary data** the firm had collected over decades that competitors couldn't access
- **Workflow integration depth** that made the AI inseparable from how customers actually used the product
- **Distribution and brand** that meant new entrants couldn't reach the customer base even with equivalent technology

The firm pivoted. The next $8M went into data infrastructure (cleaning and structuring 30 years of underwriting decisions and outcomes), workflow integration (making the AI a built-in part of agent tools rather than a separate system), and distribution partnerships (locking in third-party agents who'd refer customers exclusively if they used the firm's tools).

That investment has held up. The proprietary model spend, in retrospect, was capability-building dressed up as moat-building.

## Framework

**Hamilton Helmer's 7 Powers, Applied to AI:**

```
                                 IS THIS A REAL AI MOAT?
                                          │
                                          │
    ┌────────────────────────────┬────────┴────────┬────────────────────────────┐
    │                            │                 │                            │
    ▼                            ▼                 ▼                            ▼
   ┌────────────────┐    ┌────────────────┐    ┌────────────────┐    ┌────────────────┐
   │  COUNTER-      │    │  SCALE         │    │  NETWORK       │    │  SWITCHING     │
   │  POSITIONING   │    │  ECONOMIES     │    │  ECONOMIES     │    │  COSTS         │
   │                │    │                │    │                │    │                │
   │  YES if AI    │    │  YES if your  │    │  YES if more  │    │  YES if your  │
   │  enables a    │    │  data scale   │    │  users make   │    │  AI is deeply │
   │  business     │    │  produces a   │    │  the AI more  │    │  woven into   │
   │  model        │    │  meaningful   │    │  valuable for │    │  customer     │
   │  competitors  │    │  performance  │    │  everyone     │    │  workflows    │
   │  can't adopt  │    │  gap          │    │  (rare)       │    │  and data     │
   │  without      │    │                │    │                │    │                │
   │  cannibaliz- │    │  WATCH FOR:   │    │                │    │                │
   │  ing them    │    │  LLMs are    │    │                │    │                │
   │              │    │  flattening   │    │                │    │                │
   │              │    │  this         │    │                │    │                │
   └────────────────┘    └────────────────┘    └────────────────┘    └────────────────┘

   ┌────────────────┐    ┌────────────────┐    ┌────────────────┐
   │  BRANDING      │    │  CORNERED       │    │  PROCESS       │
   │                │    │  RESOURCE       │    │  POWER         │
   │                │    │                 │    │                │
   │  YES if AI    │    │  YES if you    │    │  YES if you   │
   │  trust is a   │    │  have access   │    │  have organi- │
   │  trust signal │    │  to data,       │    │  zational     │
   │  competitors  │    │  talent, or     │    │  capabilities │
   │  can't easily │    │  IP that com-   │    │  competitors  │
   │  replicate    │    │  petitors       │    │  can't copy   │
   │              │    │  cannot get     │    │                │
   │  Often a      │    │                 │    │  This is the   │
   │  late-stage   │    │  Most common    │    │  rarest and    │
   │  moat         │    │  real AI moat   │    │  most durable │
   │              │    │  source         │    │                │
   └────────────────┘    └────────────────┘    └────────────────┘
```

## Which AI "Moats" Are Real?

**Real (or potentially real):**

- **Proprietary data accumulated over time and not available to competitors.** A logistics company with 15 years of route + outcome data has an asset that a competitor can't acquire by writing a check. This is the most common real AI moat.
- **Distribution and integration depth.** Your AI is embedded in workflows that customers can't easily switch away from. Salesforce's Einstein has this; most AI startups don't. Switching costs in B2B SaaS are huge if the AI is genuinely woven into how customers work.
- **Regulatory positioning.** In regulated industries (healthcare, financial services, defense), being first to navigate the regulatory framework for an AI capability creates a moat that takes years for competitors to clear. This is real, though it has a shelf life.
- **Counter-positioning.** Your AI enables a business model that incumbents can't adopt without cannibalizing themselves. Stripe's payment-API-with-AI fraud detection vs. legacy banks couldn't have moved as fast.
- **Process power.** Some organizations are structurally better at deploying AI — they have the operating model, the talent flywheel, the change management capability. This is real but rare and slow-building.

**Not actually moats (despite the marketing):**

- **"Better model performance."** Off-the-shelf models close gaps within 12-24 months. Performance leads are temporary unless backed by something else.
- **"AI-first culture."** Real but not sticky. A culture is hard to copy but it's also hard to defend if a competitor poaches your top talent. People walk; cultures shift.
- **"Trained on our data."** True but increasingly less differentiating. Every company has training data. The question is whether the *combination* of data + model + workflow is uniquely valuable, which is the data + integration + process moat above.
- **"Cutting-edge AI capability."** Almost certainly not. The cutting edge moves every six months. Anyone who claims a moat from being on the latest model is funding R&D, not building durable advantage.

## The Moat-Aware Investment Question

For every major AI investment, ask: which of the 7 Powers does this strengthen?

If the answer is "none," the investment is capability-building, not moat-building. That's not bad — capability-building is valuable. But it's a different ROI argument and a different time horizon. Capability-building pays back in 1-3 years. Moat-building pays back over 5-10 years and requires patience most organizations don't have.

The honest framing for most AI investments: *"This will let us match competitors on AI-driven [X capability]. It's table-stakes for the next era. We need to do it. It is not, by itself, a moat."*

That framing is harder to sell to a board. It's also more honest. Boards that get this distinction tend to fund AI work better — they understand they're paying for industry parity, with select investments aimed at differentiation.

## Where Real AI Moats Come From

If you want to build a real moat, three patterns to focus on:

**1. Become the system of record for proprietary data.** Build workflows that generate data competitors don't have. Then that data becomes the moat — not the AI on top of it. The AI changes; the data persists and compounds.

**2. Embed deeply into customer workflows.** Switching costs are real moats. The deeper your AI is in the daily work of your users, the higher the switching cost. This usually means thoughtful integration, not standalone AI products. Salesforce's playbook.

**3. Build process power around AI deployment.** This takes 5+ years and is hard to copy. The org that has shipped 50 AI initiatives across business units, with a working operating model, governance, talent flywheel, and Community of Practice (Day 20) is materially more capable than a competitor starting from scratch — even if both have access to the same models. Process power is the only structural moat that improves with time.

**Hot take:** The most overhyped "AI moat" claim of the 2020s has been "we trained our own model." For 99% of companies, this is dollar-burning, not moat-building. Off-the-shelf foundation models from Anthropic, OpenAI, and others are catching up to most domain-specific models within 12-18 months — and the cost of operating proprietary models is far higher than the cost of using fine-tuned API access.

The companies that should train their own models are the ones with *unique data unavailable elsewhere* and *scale that justifies the operating cost*. That's a small set. Everyone else is funding pride, not strategy.

## Your Move

For your three largest AI investments, audit each against the 7 Powers framework:

1. Which power(s) does this investment strengthen?
2. How durable is that power — will competitors close the gap in 1 year, 3 years, 5+ years?
3. Is this investment best-described as moat-building, capability-building, or industry-parity?
4. If it's not strengthening any of the 7 Powers, is the ROI argument honest about that?

Most leaders find this exercise uncomfortable because it deflates a few proud claims. That's the point. Honest assessment of where moats actually come from leads to better investment decisions over the long run.

Document the audit. Share with your CFO and the executive sponsor. The conversation that follows is one of the highest-leverage strategic discussions you can have about your AI portfolio.

## Go Deeper

- [Hamilton Helmer, "7 Powers" (book)](https://7powers.com/) — The foundational text. Worth the time even though it predates the AI era; the framework applies cleanly. Helmer's blog has additional posts applying the framework to specific industries.
- [Stratechery (Ben Thompson)](https://stratechery.com/) — The best ongoing analysis of strategic moats in tech, increasingly focused on AI. Thompson's distinction between aggregators and platforms applies directly to AI moat analysis.
- [a16z, "Who Owns the Generative AI Platform?"](https://a16z.com/who-owns-the-generative-ai-platform/) — Influential post (and follow-ups) on how value accrues across the AI stack. Useful for thinking about where in the stack moats are actually possible.
