# Day 08: Designing an AI Pilot That Actually Proves Value

## The Idea

Most AI pilots are designed to succeed, not to learn. That's why they never scale.

Here's the pattern: a team picks a friendly use case, hand-curates the data, assigns their best engineers, gives it executive air cover, and after six months declares victory. Then nothing happens. The pilot "succeeded" but nobody can articulate what it proved, whether it would work at scale, or what happens next. The demo was impressive. The business case is still a slide deck.

The problem isn't that pilots fail. The problem is that they're designed as science experiments — interesting but inconclusive — instead of decision instruments that generate clear evidence for or against a specific investment.

A well-designed pilot answers one question: **Should we invest in scaling this, yes or no?** Everything in the pilot design flows from that question.

## In Practice

A mid-size manufacturer with 14 production lines wanted to pilot AI-driven predictive maintenance. They'd been pitched the dream: sensors on every machine, real-time anomaly detection, zero unplanned downtime. The vendor made it sound like a 90-day project.

**The bad version of this pilot** would look like this: install sensors on one production line (the newest one, with the cleanest machines and most reliable operators), run the model for 90 days, compare its predictions to what happened, celebrate the high accuracy rate, and present a slide deck to the COO.

That pilot would "succeed" and prove almost nothing. Why? The newest line has the fewest breakdowns. The 90-day window is too short to see rare failure modes. There's no comparison to the current process. And the accuracy metric is misleading — if machines break down 2% of the time, a model that always predicts "no failure" is 98% accurate.

**The good version** started differently. The team wrote a hypothesis: "AI-based predictive maintenance on Line 7 (our oldest, highest-maintenance line) will reduce unplanned downtime by at least 15% compared to our current schedule-based maintenance program over a 6-month period."

Notice what's different:

- **Specific target**: Line 7, not the easiest line — the one where the problem is worst
- **Clear metric**: unplanned downtime reduction, not model accuracy
- **Baseline**: compared to the existing schedule-based program, not compared to nothing
- **Threshold**: 15% — a number the operations team agreed would justify the cost of scaling to all 14 lines
- **Timeframe**: 6 months, long enough to capture seasonal variation and rare failure modes

Six months later, the pilot showed an 11% reduction in unplanned downtime. It "failed" the hypothesis. But that 11% number, with real cost data attached, let the team make an informed decision: the ROI at 11% improvement was still positive across all 14 lines, but the payback period was 28 months instead of 16. The CFO approved a phased rollout to the 5 oldest lines first. That's a real business decision based on real evidence.

The "successful" pilot on the newest line would have generated a great demo and a stalled initiative. The "failed" pilot on the hardest line generated a funded program.

## Framework

Every pilot that actually proves value has three non-negotiable elements:

### 1. A Clear Hypothesis

Not "let's see what AI can do" but "we believe [specific AI capability] will improve [specific metric] by [specific amount] in [specific timeframe]." If you can't fill in those blanks, you're not ready to pilot — you're still in the exploration phase. That's fine, but call it what it is and don't budget like it's a pilot.

### 2. A Baseline and Control

You need a "before" to compare against. Ideally, you run the AI system alongside the existing process and measure both. In healthcare, this might mean having the AI flag potential diagnoses while physicians continue their standard workflow, then comparing detection rates. In financial services, this might mean running the AI fraud model in shadow mode alongside rule-based systems. Without a baseline, every result is anecdotal.

### 3. A Decision Gate

Before the pilot starts, define what happens at the end. Gartner calls this a "tollgate" — a predetermined point where leadership reviews evidence and makes one of three decisions: scale, pivot, or kill. If you don't define this upfront, the pilot enters organizational limbo — too successful to kill, too inconclusive to fund, slowly dying of neglect.

### The Pilot Lifecycle

```
  ┌──────────────────────────────────────────────────────────────────┐
  │                     THE PILOT LIFECYCLE                          │
  └──────────────────────────────────────────────────────────────────┘

  ┌───────────┐    ┌───────────┐    ┌───────────┐    ┌───────────┐
  │           │    │           │    │           │    │           │
  │ HYPOTHESIS│───>│  DESIGN   │───>│  EXECUTE  │───>│  MEASURE  │
  │           │    │           │    │           │    │           │
  │ "We       │    │ Scope,    │    │ Run it.   │    │ Compare   │
  │ believe   │    │ baseline, │    │ Resist    │    │ against   │
  │ X will    │    │ controls, │    │ urge to   │    │ baseline. │
  │ cause Y"  │    │ metrics,  │    │ tweak     │    │ Honest    │
  │           │    │ timeline  │    │ mid-run.  │    │ numbers.  │
  └───────────┘    └───────────┘    └───────────┘    └─────┬─────┘
                                                           │
                                                           v
                                                  ┌────────────────┐
                                                  │ DECISION GATE  │
                                                  │                │
                                                  │ Evidence says: │
                                                  └───────┬────────┘
                                                          │
                                          ┌───────────────┼───────────────┐
                                          │               │               │
                                          v               v               v
                                    ┌──────────┐   ┌──────────┐   ┌──────────┐
                                    │  SCALE   │   │  PIVOT   │   │  KILL    │
                                    │          │   │          │   │          │
                                    │ Fund the │   │ Adjust   │   │ Stop.    │
                                    │ rollout. │   │ scope or │   │ Reallocate│
                                    │ Production│   │ approach.│   │ budget.  │
                                    │ roadmap. │   │ Re-pilot.│   │ Move on. │
                                    └──────────┘   └──────────┘   └──────────┘
```

## Scoping: The Goldilocks Problem

Pilot scope is where most teams get it wrong. Too big, and the pilot takes 12 months, costs a fortune, and becomes a mini-transformation program. Too small, and the results are inconclusive — "we tested it on 50 records and it worked" doesn't convince anyone.

The right scope has four properties:

```
  PILOT SCOPE CHECKLIST
  ─────────────────────────────────────────────────
  [  ] Representative — reflects real-world conditions,
       not cherry-picked best-case scenarios

  [  ] Bounded — clear start date, end date, and budget
       cap (McKinsey recommends 8-12 weeks for most
       pilots, with a hard cap at 16)

  [  ] Measurable — enough volume/time to generate
       statistically meaningful results (not 50 records)

  [  ] Connected — a clear path to production exists
       if results are positive (same tech stack, same
       data sources, same team can continue)
  ─────────────────────────────────────────────────
```

That last one — **Connected** — is where the "pilot trap" lives. If your pilot uses hand-cleaned data that doesn't exist in production, or a cloud GPU cluster your IT team won't approve, or a vendor tool that can't integrate with your existing systems, then you've built a science fair project. It might win a ribbon, but it's not going to production.

Before starting any pilot, ask: "If this succeeds, what does the production version look like?" If the answer involves re-architecting data pipelines, hiring a team that doesn't exist yet, or getting budget approval that nobody has started — you have a gap between your pilot and reality. Close that gap before you start, or at least document it honestly so the decision gate isn't a surprise.

## The Pilot Trap

The pilot trap is the organizational pattern where pilots succeed, get celebrated, and then quietly die. BCG found that roughly 75% of AI pilots never make it to production. Three-quarters. That's not a technology problem — it's a design problem.

Pilots get trapped for predictable reasons:

- **No production path was designed in.** The pilot team used different tools, data, and processes than what production would require.
- **The wrong people ran it.** Data scientists built the pilot; nobody thought about who would operate it at scale. IT wasn't involved. The business team that needs to change their workflow wasn't consulted.
- **Success wasn't defined in business terms.** "The model achieved 94% accuracy" doesn't tell the CFO whether to write a check. "The model reduced claim processing time by 35%, saving $2.1M annually at scale" does.
- **No one owned the scale decision.** The pilot had a sponsor but no one had the authority or the budget to approve a production rollout. The decision gate was never defined.

The fix is straightforward: design the pilot backward from the scale decision. Start with "what evidence would convince the decision-maker to fund a full rollout?" and work backward to the pilot design that generates that evidence.

## Your Move

Take the top use case from your Day 04 prioritization. Write a one-page pilot design with: (1) a falsifiable hypothesis in the format "We believe [capability] will improve [metric] by [amount] in [timeframe]," (2) your baseline — what's the current performance you're comparing against, (3) your scope — which team, process, or location, and for how long, (4) your decision gate — who decides, what evidence do they need, and what are the three possible outcomes (scale/pivot/kill), and (5) the production gap — what's different between your pilot environment and your production environment.

If you can't fill in all five sections, that's useful information. The blank spots show you where your pilot would have been underdesigned.

## Go Deeper

- [BCG, "From Pilot to Scale: What Drives AI Adoption"](https://www.bcg.com/publications/2020/increasing-odds-of-success-in-digital-transformation) — Data on why most pilots don't scale and what differentiates the ones that do.
- [McKinsey, "An Executive's Guide to AI"](https://www.mckinsey.com/capabilities/quantumblack/our-insights/an-executives-guide-to-ai) — Covers pilot design principles including the "last mile" problem of moving from proof-of-concept to production.
- [Harvard Business Review, "Building the AI-Powered Organization"](https://hbr.org/2019/07/building-the-ai-powered-organization) — Why organizational readiness matters more than model performance for pilot success.
