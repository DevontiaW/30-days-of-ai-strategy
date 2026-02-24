# Day 12: Success Metrics That Matter

## The Idea

Here's a scene I've watched play out too many times: a data science team presents to leadership, beaming with pride. "Our model achieved 95% accuracy!" The room nods. Budgets get approved. Six months later, someone asks the obvious question — "So what actually changed?" Silence.

Model accuracy is not a business metric. Neither is F1 score, latency, or training loss. These are *engineering diagnostics*. They tell you whether the model works. They tell you nothing about whether the model matters.

The gap between "our AI works" and "our AI creates value" is where most initiatives go to die. And the root cause is almost always the same: nobody defined what success looks like in terms the business actually cares about.

If your AI metrics dashboard doesn't include a dollar figure, you're tracking science projects, not business initiatives.

## In Practice

A mid-size manufacturer rolled out a computer vision system for quality inspection on their production line. The model hit 95% accuracy in detecting defects. The team celebrated. Leadership was impressed.

Twelve months later, they ran the numbers. Defect rates shipped to customers hadn't changed. At all.

The problem wasn't the model — it was the integration. The model flagged defects, but the alerts went to a dashboard nobody checked. The operators on the floor still relied on visual inspection because no one had changed the process. The AI was right 95% of the time, and it didn't matter even once.

This is what happens when you measure the technology instead of the outcome. The model was accurate. The initiative was a failure. Those are two completely different statements.

They eventually fixed it — not by improving the model, but by wiring the output to the PLC that controlled the line, automatically diverting flagged items for manual review. Defect escape rate dropped 40% in the first quarter after that change. The model hadn't changed. The metric that mattered finally moved.

## Framework

**The AI Metrics Hierarchy**

Most teams live at the bottom of this pyramid and never climb up. The value is at the top.

```
                    ╱╲
                   ╱  ╲
                  ╱    ╲
                 ╱ STRA ╲
                ╱ TEGIC  ╲        Market share, competitive
               ╱──────────╲       positioning, new revenue
              ╱            ╲      streams, strategic optionality
             ╱  BUSINESS    ╲
            ╱    METRICS     ╲    Revenue impact, cost savings,
           ╱──────────────────╲   margin improvement, customer
          ╱                    ╲  lifetime value, NPS change
         ╱  OPERATIONAL         ╲
        ╱    METRICS             ╲  Process time reduction,
       ╱──────────────────────────╲ throughput, error rates,
      ╱                            ╲ adoption rate, ticket volume
     ╱  TECHNICAL                   ╲
    ╱    METRICS                     ╲ Model accuracy, latency,
   ╱──────────────────────────────────╲ uptime, drift, F1 score
  ╱────────────────────────────────────╲
```

**The rule:** Every technical metric should trace upward to a business metric. If it can't, ask why you're measuring it.

Here's what that looks like in practice for a customer service AI:

```
  STRATEGIC     │ Customer retention rate, market differentiation
  ──────────────┤
  BUSINESS      │ Support cost per ticket (-$4.20), CSAT (+12pts)
  ──────────────┤
  OPERATIONAL   │ Avg handle time (-35%), first-contact resolution (+18%)
  ──────────────┤
  TECHNICAL     │ Intent classification accuracy (91%), response latency (1.2s)
```

If intent classification drops to 80%, does handle time go up? Does cost per ticket increase? If the answers are yes, the technical metric is connected to value. If you can't trace that chain, you've got a vanity metric.

### Leading vs. Lagging Indicators

You need both. Leading indicators tell you if you're on the right trajectory *before* the financial results show up. Lagging indicators confirm the value was real.

```
┌─────────────────────────────────┬──────────────────────────────────┐
│  LEADING INDICATORS             │  LAGGING INDICATORS              │
│  (predictive, actionable)       │  (confirmatory, retrospective)   │
├─────────────────────────────────┼──────────────────────────────────┤
│  User adoption rate             │  ROI / payback period            │
│  Data quality score improvement │  Total cost savings (annualized) │
│  Process cycle time reduction   │  Revenue directly attributed     │
│  Employee trust/satisfaction    │  Margin improvement              │
│  Prediction accuracy trend      │  Competitive win rate change     │
│  Time-to-decision reduction     │  Customer lifetime value shift   │
│  Manual override frequency      │  Headcount reallocation savings  │
│  Pipeline/data freshness        │  Risk reduction (quantified)     │
└─────────────────────────────────┴──────────────────────────────────┘
```

Manual override frequency is one of my favorites. When operators stop overriding the AI's recommendations, that's a proxy for trust — and trust is what separates a deployed model from a model that actually gets used.

### The Baseline Problem

You cannot measure improvement if you don't know where you started. This sounds obvious. It is routinely ignored.

Before you launch any AI initiative, document the current state of every metric you plan to improve. Not a rough estimate. Actual numbers with dates. "Our average claims processing time is 4.2 days as of March 2025, based on the trailing 90-day average across 12,400 claims."

If you skip this step, you'll end up six months later arguing about whether things got better, worse, or stayed the same. I've seen teams spend more time debating the baseline retroactively than they spent building the model.

### Time Horizons: The 30-90-180 Cadence

Different metrics matter at different stages:

```
  30 DAYS   │ Technical metrics stable? Users actually using it?
            │ Measure: adoption rate, system uptime, data pipeline health
            │ Question: "Does this work and are people touching it?"
            │
  90 DAYS   │ Operational improvements visible? Processes changing?
            │ Measure: cycle time, throughput, error rates, override rate
            │ Question: "Is the work actually getting better/faster/cheaper?"
            │
  180 DAYS  │ Business value quantifiable? Financial impact real?
            │ Measure: cost savings, revenue impact, ROI, margin change
            │ Question: "Can we put a dollar figure on this?"
```

Teams that demand ROI at 30 days kill good projects. Teams that accept "we're still learning" at 180 days are funding hobbies. Match the metric to the maturity of the initiative.

### The Attribution Problem

Even when the numbers look good, you face a harder question: did AI cause the improvement, or just correlate with it?

Your customer churn dropped 15% after deploying a predictive model. Great. But you also hired three new account managers, launched a loyalty program, and your biggest competitor had a PR crisis — all in the same quarter.

There's no perfect solution to attribution, but there are practical approaches:

- **A/B testing where possible.** Run the AI-assisted process alongside the existing one. This is the gold standard but not always feasible.
- **Staggered rollout.** Deploy to one region or team first. Compare against the control group.
- **Pre/post with controls.** Measure the metric before and after, but also measure a similar process that didn't get AI. If both improved equally, AI probably wasn't the driver.
- **Contribution analysis.** Don't claim AI "caused" the full improvement. Estimate its contribution as one factor among several. Leadership respects intellectual honesty more than inflated claims.

### Full Cost Accounting

The other metric nobody wants to talk about: what this actually costs. A complete picture includes:

- **Compute costs** — training, inference, hosting, API calls
- **Data costs** — acquisition, cleaning, labeling, storage, pipeline maintenance
- **People costs** — data engineers, ML engineers, project managers, change management
- **Opportunity cost** — what else could this team have built?
- **Maintenance cost** — monitoring, retraining, drift management, incident response

I've seen teams proudly report $500K in annual savings from an AI system that costs $600K per year to run. That's not an AI success story. That's a math problem.

## Your Move

Pick your current AI initiative (or your top planned one). Build a one-page metrics brief:

1. **Baseline:** Document the current state of the top 3 metrics you expect to improve. Use real numbers and dates.
2. **Trace the chain:** For every technical metric you're tracking, draw the line up through operational, business, and strategic metrics. If a metric doesn't connect, drop it.
3. **Leading + lagging pair:** Identify at least one leading indicator you'll watch weekly and one lagging indicator you'll evaluate quarterly.
4. **Full cost:** Estimate the all-in cost of the initiative (compute + data + people + opportunity cost). Divide by expected annual benefit. If the ratio is uncomfortable, that's important information.

## Go Deeper

- [Google's HEART Framework](https://research.google/pubs/measuring-the-user-experience-on-a-large-scale-user-centered-metrics-for-web-applications/) — Happiness, Engagement, Adoption, Retention, Task success. Originally for UX, adapts well to AI products.
- [McKinsey, "The Hard Math Behind AI Transformation"](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai) — Includes data on how leading companies measure AI value vs. laggards.
- [Gartner's AI Business Value Framework](https://www.gartner.com/en/articles/keep-your-ai-projects-on-track) — Structured approach to tying AI projects to business outcomes with measurable KPIs.
