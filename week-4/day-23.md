# Day 23: Measuring ROI Beyond the Pilot

## The Idea

"This AI saved us 5,000 hours last quarter." Sounds great. It's almost always wrong.

Not because someone's lying. Because measuring AI ROI honestly is technically harder than most organizations realize. The naive method — count the times AI was used, multiply by some assumed time savings, declare victory — produces numbers that look defensible until anyone starts to poke at them.

The actual question is harder: **what would have happened without the AI system?** And answering that requires comparing the world that exists to a world that doesn't. That's not impossible. But it requires more discipline than most AI ROI claims show.

This isn't an academic concern. AI investment decisions are starting to be challenged by CFOs who've seen too many "AI saved us $X" claims that didn't hold up to scrutiny. If you can't defend your ROI with rigorous methodology, the portfolio you built last week is going to come under pressure — and the projects that should survive will lose to ones with better numbers.

## In Practice

A B2B SaaS company deployed an AI customer support system in 2024. After six months, the COO reported to the board that the system had "deflected 35% of support tickets, saving an estimated $2.1M annually."

The CFO asked the obvious question: how do we know?

The math worked like this. Pre-AI, the company received 4,000 support tickets per month. Post-AI, the AI handled 1,400 tickets without escalating to human agents. At an average cost of $50 per human-handled ticket, the math gave you $2.1M in annual savings.

The CFO probed harder. Three problems emerged:

**Volume drift.** Total support volume had grown from 4,000 to 6,500 tickets per month over the six months — partly because the company had added customers, partly because the AI made it easier to file tickets (the friction had dropped). The "tickets handled by AI" wasn't a savings; it was largely net new volume the company hadn't been seeing before.

**Quality questions.** A sample audit of AI-handled tickets found that 30% of them resulted in re-contact within seven days. Either the AI hadn't actually solved the problem, or it had given the customer a workaround that broke later. Those re-contacts now hit human agents. The "deflection" was partial.

**Counterfactual gap.** The "$50 per ticket" figure assumed that without AI, every one of those tickets would have hit a human at the same cost as previous tickets. But many of the AI-handled tickets were trivial questions (password resets, billing inquiries) that pre-AI had been handled in 90 seconds, not the 8-minute average that drove the $50 figure.

After the rigorous analysis, the actual savings were closer to $400K-$600K annually — still positive, but a quarter of the original claim. The CFO didn't kill the project. But she did request that all future AI ROI claims go through the finance team's rigor, and the AI program's credibility took a real hit.

The lesson isn't that AI doesn't deliver value. It often does. The lesson is that *unaudited AI ROI claims will eventually be audited*, and when they are, weak methodology becomes a credibility problem.

## Why AI ROI Is Hard

Three structural reasons AI ROI is harder to measure than most other business investments:

**1. Counterfactuals are slippery.** What would have happened without the AI? In most cases, you can't rerun the year without it. You're estimating an unobserved alternative.

**2. Behavior changes around AI.** The system itself shifts how users behave. Before AI, your sales team manually researched accounts; after AI, they accept the AI's research without verifying. Outcomes change because behavior changes — sometimes for the worse.

**3. Substitution effects compound.** AI doesn't usually eliminate work — it shifts work elsewhere. A document review AI saves the paralegal time but creates new work for the attorney reviewing AI output. Net savings is the saved time minus the new time, which is rarely measured.

These three together mean the lazy ROI methodology — count units processed, multiply by assumed time savings — systematically overstates AI value. Often by 2-3x.

## Framework

**The ROI Hierarchy of Evidence:**

```
                                          ┌─────────────────────┐
                                          │                     │
                                          │   STRONGEST         │
   ▲                                       │                     │
   │                                       │  Randomized A/B     │
   │  Confidence in                        │  test with control  │
   │  the ROI claim                        │  group              │
   │                                       │                     │
   │                                       └─────────────────────┘
   │
   │                          ┌─────────────────────┐
   │                          │                     │
   │                          │   Phased rollout    │
   │                          │   with adoption     │
   │                          │   cohort comparison │
   │                          │                     │
   │                          └─────────────────────┘
   │
   │             ┌─────────────────────┐
   │             │                     │
   │             │   Pre/post          │
   │             │   comparison with   │
   │             │   measured baseline │
   │             │                     │
   │             └─────────────────────┘
   │
   │  ┌─────────────────────┐
   │  │                     │
   │  │   Activity counts   │
   │  │   x assumed savings │
   │  │   per unit (NAIVE)  │
   │  │                     │
   │  └─────────────────────┘
   │  WEAKEST
   │
   └────────────────────────────────────────────────────► Methodology rigor
```

**The four levels:**

**Level 1 — Activity counts × assumed savings (the bottom).** This is what most "AI saved us $X" claims actually are. Count how many times AI did the thing, multiply by an assumed dollar savings per instance, declare victory. Easy to produce, easy to inflate, hard to defend under scrutiny.

**Level 2 — Pre/post comparison with measured baseline.** Before deploying AI, you measured the relevant business metric (cycle time, error rate, cost per transaction). After deploying, you measured again. The difference is your effect, less anything else that changed in the environment.

This is meaningfully better than Level 1 — but the "anything else that changed" can be huge. Seasonal patterns, customer mix shifts, organizational changes, other concurrent initiatives. If your business changed at all in the measurement window, your pre/post comparison is contaminated.

**Level 3 — Phased rollout with cohort comparison.** Deploy AI to one team, region, or customer segment first. Measure outcomes for the AI cohort vs. the not-yet-AI cohort over the same period. The comparison is more controlled because both groups face the same external conditions.

This is what most rigorous AI deployments should aim for. It requires phased rollout (which most teams want anyway for risk management) and a willingness to keep a comparison group long enough to measure outcomes. Three to six months is typical.

**Level 4 — Randomized A/B test with control group.** The gold standard. Randomly assign users (or transactions, or accounts) to AI-enabled vs. AI-disabled groups for a defined period. Measure the outcome difference. This is the methodology used in clinical trials and tech-company experimentation platforms.

Hard to do for some AI use cases (the AI is usually meant for everyone, randomization may be unethical, regulatory constraints) but possible more often than people think. When you can do it, the resulting numbers are unimpeachable.

## The Three Numbers Every AI ROI Claim Needs

Whatever methodology you use, every credible AI ROI claim has three numbers, not one:

**1. The point estimate.** "AI X saved us $Y per year." The headline number.

**2. The confidence interval.** "Our 80% confidence range is $0.6M to $1.2M." Acknowledges that the point estimate is an estimate.

**3. The counterfactual assumption.** "This compares to a baseline scenario where the team continued with the previous manual workflow at current staffing levels." Makes explicit what you're comparing against.

A claim that has only the point estimate is a claim that hasn't been seriously analyzed. A claim with all three is auditable — and credible.

## What Actually Counts as ROI?

Three categories of AI value, in roughly increasing difficulty to measure:

**Cost savings (easiest):** Direct reduction in expense. Hours saved × loaded labor cost. Vendor contracts retired. Headcount avoided. The most common type of AI ROI claim, and the easiest to validate if methodology is sound.

**Revenue gains (moderate):** Increased conversion, larger deals, faster close cycles, customer retention. Harder because revenue is influenced by many variables. The honest version requires controlled comparison — Level 3 or 4 in the hierarchy.

**Strategic value (hardest):** Competitive positioning, optionality, organizational learning. Almost impossible to put a dollar figure on, but legitimately important. Don't try to fake-precision it; describe it qualitatively and let executives weight it themselves.

**Hot take:** Strategic-value-only ROI claims are a yellow flag. If a project has been running for 18 months and the only ROI argument is "we've learned a lot" or "we've built capability," it's probably a project that should have been a smaller exploration effort, not a multi-year investment. Real strategic value usually shows up downstream as cost savings or revenue gains. If those don't materialize on a reasonable timeline, the strategic value probably wasn't there.

## Your Move

Pick your most prominent AI ROI claim. Audit it against the framework:

1. **What level of evidence does it have?** Activity-count math, pre/post, phased rollout, or A/B?
2. **What's the counterfactual assumption?** Make it explicit. Would it survive a CFO's challenge?
3. **What's the confidence interval?** If you've never asked this, the point estimate is probably more uncertain than you've been claiming.
4. **What category of value is it?** Cost, revenue, or strategic? Are you using the right methodology for that category?

Then redo the math with the most rigorous methodology you can defend. If the new number is materially smaller than the original claim, that's a credibility-saving correction worth making before someone forces you to.

If you're early in an AI initiative, design the measurement methodology *before* deployment. Most ROI methodology problems are unfixable retroactively because the data needed for a credible counterfactual was never collected.

## Go Deeper

- [Ron Kohavi et al., "Trustworthy Online Controlled Experiments"](https://www.cambridge.org/core/books/trustworthy-online-controlled-experiments/D97B26382EB0EB2DC2019A7A7B518F59) — The definitive book on A/B testing methodology. Heavy but worth the time if you're going to do this seriously.
- [HBR, "How to Calculate the ROI of AI"](https://hbr.org/2023/11/how-to-calculate-the-roi-of-ai) — Practical, business-friendly framing of the methodology hierarchy above. Good document to share with skeptical CFOs.
- [Microsoft Research, "Online Experimentation at Microsoft"](https://www.microsoft.com/en-us/research/group/experimentation-platform-exp/) — Free papers on how a large tech company runs controlled experiments at scale, including for AI features. The methodology generalizes beyond Microsoft's specific tools.
