# Day 22: AI Portfolio Management

## The Idea

Welcome to Week 4. The last three weeks have been about doing AI well at the level of a single initiative — strategy, pilot, people. This week zooms out. Once you have one thing working, how do you manage *the next five*?

Most organizations transition from "doing AI" to "doing AI badly at scale" precisely at this moment. They had one focused pilot. It worked. Suddenly they have eight ideas, three half-funded projects, two vendors selling into different VPs, and no shared view of what's actually happening across the portfolio. Resources scatter. Quality drops. The wins from the first pilot get diluted by the noise of unfocused expansion.

The fix is portfolio thinking. Same discipline VCs use, same discipline pharma R&D groups use — applied to your AI work. Not every initiative is going to win. Most won't. The portfolio's job is to make sure the winners get the resources and the losers get killed cleanly before they consume the organization's appetite.

## In Practice

A national logistics company hit a moment of strategic awkwardness in early 2025. They'd shipped a successful AI initiative — route optimization that saved measurable cost in their largest division. Energy was high. The CEO had mentioned it in two earnings calls. Other VPs had taken notice.

By Q3 2025, they had eleven AI projects underway. Eleven. Across operations, customer service, finance, HR, marketing, fleet maintenance, claims, and three different attempts at "predictive analytics" that nobody could quite distinguish. Each had its own sponsor, its own vendor, its own data pipeline. Total committed budget: $14M. Total people involved: about 40 across the company.

Here's what an honest assessment looked like:
- 2 projects were on track and producing measurable results
- 3 projects were stuck in the valley of disillusionment but still burning resources
- 4 projects were vendor-led "exploration" with no clear success criteria
- 2 projects were the same thing under different names, run by different VPs who didn't know about each other

The CFO ran the numbers. The 2 successful projects had generated about $3.2M in net value. The other 9 had collectively burned $8M with no measurable returns. The portfolio was negative-ROI overall — not because AI didn't work, but because the organization had no portfolio discipline.

We restructured around the framework below. Within four months, three projects were killed cleanly (with their teams redirected), four were merged into two coherent initiatives, and resources concentrated on the things actually working. Eighteen months later, the same company had a portfolio of six initiatives — all with clear stage gates, all measured against business outcomes, with a $19M annualized run-rate of value creation. Different number of projects, dramatically better outcomes.

## Framework

**The Four-Stage AI Portfolio:**

```
                  STAGE              MOST PROJECTS DIE
                                          HERE
                                            │
    ┌─────────────┐    ┌─────────────┐     │
    │             │    │             │     ▼
    │ EXPLORATION │───▶│   PILOT     │───▶  KILL
    │             │    │             │     OR
    │  Cheap, fast│    │  Real users,│   ┌─────────────┐
    │  experiments│    │  measured   │   │             │
    │  (60% of    │    │  outcomes   │──▶│   SCALE     │
    │   ideas die │    │  (50% die   │   │             │
    │   here)     │    │   here)     │   │  Expanding  │
    │             │    │             │   │  to broader │
    │  20-40 hrs  │    │  3-6 months │   │  use, prod- │
    │  per idea   │    │  $50-300K   │   │  uction-grade│
    │             │    │             │   │             │
    └─────────────┘    └─────────────┘   │  6-18 mo    │
                                          │  $500K-3M   │
                                          │             │
                                          └──────┬──────┘
                                                 │
                                                 ▼
                                          ┌─────────────┐
                                          │             │
                                          │  MATURE     │
                                          │  OPERATIONS │
                                          │             │
                                          │  Maintained,│
                                          │  improving, │
                                          │  contributing│
                                          │  steady ROI │
                                          │             │
                                          │  Multi-year │
                                          │             │
                                          └─────────────┘
```

The stages have different economics, different success criteria, and different investment patterns:

**Exploration:** Fast, cheap, high mortality. The goal is to learn — does this idea even merit a pilot? Most exploration projects should die. That's not failure; that's the point. Budget: small. Timeline: weeks. Number active at any time: many.

**Pilot:** A real bet. Real users, real outcomes, real success criteria from Day 12. Most pilots will still die — but for documented reasons that produce learning. Budget: meaningful. Timeline: 3-6 months. Number active at any time: a handful.

**Scale:** The pilot worked. Now you're investing seriously in productionalization, broader rollout, and operational hardening. Budget: large. Timeline: 6-18 months. Number active: 1-3 at a time, because each consumes serious organizational attention.

**Mature Operations:** The system is in production, generating value, being maintained and improved. Budget: ongoing operating cost. Timeline: years. Number: as many as you've earned through the funnel.

**The 70/20/10 Resource Allocation:**

For mid-stage AI organizations (you have at least one mature system), a useful default is:

- **70%** of resources on Mature Operations and Scale-stage work — keeping what works running, improving steadily
- **20%** on Pilots — actively betting on 2-4 specific use cases that could become tomorrow's mature systems
- **10%** on Exploration — many small experiments, most of which will die fast

Early-stage organizations (no mature systems yet) flip this — more like 60/30/10 toward Pilots and Exploration. Late-stage organizations (multiple mature systems) shift the other way — 80/15/5 toward operations.

## The Portfolio View

Most AI executives can't tell you, off the top of their head, every active AI initiative in their organization. That's the first failure mode. You can't manage what you can't see.

The portfolio view is one document — usually a single page, updated monthly — that lists every AI initiative across the four stages, with key metadata for each:

```
   PROJECT       STAGE       OWNER       BUDGET    STATUS    DECISION
   ──────────────────────────────────────────────────────────────────
   Route Opt     Mature      Logistics   $1.2M/yr  GREEN     Continue
   Doc Class.    Scale       Operations  $2.5M     GREEN     On track
   Claims AI     Pilot       Claims      $400K     YELLOW    Decision Q2
   Predict Maint Pilot       Fleet       $300K     RED       Kill review
   GenAI CS      Pilot       Customer    $500K     GREEN     On track
   Marketing AI  Exploration Marketing   $50K      GREEN     Decide pilot
   HR Screen     Exploration HR          $30K      RED       Kill - bias
   Pricing AI    Exploration Pricing     $40K      GREEN     Continue
```

This view is the single most important artifact for AI portfolio management. It's also the thing most companies don't have. Without it, executives can't make resource allocation decisions — they only see the projects in front of them, not the ones competing for the same engineering capacity, data resources, or organizational attention.

## Stage Gates and Kill Decisions

The portfolio model only works if projects actually move through stages — and if losers actually die. This is harder than it sounds.

**Stage gate criteria** (define these before launching):

- **Exploration → Pilot:** Did the experiment learn what we hoped? Is there a defensible business case for a real pilot? Do we have a sponsor and a domain expert lined up?
- **Pilot → Scale:** Did the pilot meet its predefined success criteria? Are the unit economics defensible? Is the team ready to support production operations?
- **Scale → Mature:** Has the system been in production at full scope for 3+ months with stable performance? Is operational ownership clear? Is it generating documented value at the projected rate?

**Kill decisions** (the harder discipline):

Most organizations are bad at killing AI projects. The common failure mode is the **zombie project** — running 18 months past the point where its sponsor stopped believing in it, kept alive by inertia and the political cost of admitting failure.

The fix is making kill decisions a normal part of the portfolio review, not a special event. At every monthly portfolio review, every yellow or red project should have a documented kill criterion: "If we don't see X by Y date, we kill this and reallocate." When the date hits without X, the project dies. No drama, no recrimination. The team is redirected. The learning is documented.

If your organization has never killed an AI project, it doesn't have portfolio discipline. It has a graveyard of zombies you haven't admitted to.

## Hot Take

**Hot take:** The single biggest failure of AI strategy at the executive level is not picking the wrong use cases — it's failing to kill the wrong use cases fast enough. The opportunity cost of zombie projects is enormous: the same engineers, data scientists, and domain experts could be on the *next* high-value initiative instead of nursing along last year's bad bet.

The hardest cultural shift in AI portfolio management is making it normal to kill projects. The orgs that get this right typically have an explicit norm: "we expect 60% of explorations and 50% of pilots to die. That's the price of finding the 5-10% that scale. If we're not killing things, we're not being honest with the data."

## Your Move

Build your AI portfolio view. One page. Use the columns from the example above. List every active AI initiative — yes, including the ones underway that aren't formally part of the AI program (the underground experiments, the vendor pilots different VPs are running, the things you forgot existed).

For each, fill in stage, owner, budget, status (green/yellow/red), and the next decision date. If you can't fill in any column, that's the work to do.

Then identify: which projects should move to the next stage in the next 90 days? Which yellow/red projects need explicit kill criteria? Which exploration efforts should be either promoted or shut down?

Schedule a portfolio review with the relevant executives within two weeks. Bring this document. The conversation will be uncomfortable — and very useful.

## Go Deeper

- [Hamilton Helmer, "7 Powers"](https://7powers.com/) — Not specifically about AI, but the strategic framework that informs portfolio thinking. Day 26 builds on this directly.
- [HBR, "How to Win at Innovation"](https://hbr.org/2024/05/how-to-win-at-innovation) — Practical framework for portfolio discipline in innovation programs. Translates well to AI portfolios.
- [BCG, "Scaling AI Pilots"](https://www.bcg.com/publications/2024/scaling-ai-pays-off-only-if-done-right) — Hard data on AI portfolio outcomes by industry, with patterns that match the four-stage funnel above.
