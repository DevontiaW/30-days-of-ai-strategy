# Day 02: The Build vs. Buy Decision

## The Idea

Every AI initiative starts with this fork in the road: do you build a custom solution or buy something off the shelf? Get this wrong and you either waste months reinventing something that exists, or you lock yourself into a vendor that can't do what you actually need.

The honest answer is almost always "it depends" — but there's a framework that makes the decision systematic instead of political.

## In Practice

A healthcare company I advised wanted a clinical document summarization tool. Their initial instinct was to build — they had a small data science team and their documents were highly specialized.

We ran through the decision matrix (below) and the answer flipped. Their "unique" documents actually followed standard HL7 FHIR structures. Three vendors already handled their document type. Their data science team had two people, neither with NLP experience. And the summarization capability wasn't their competitive differentiator — their clinical protocols were.

They bought a specialized solution, customized it for their terminology, and were in production in 10 weeks instead of the 8-12 months a build would have taken.

The lesson: "our data is unique" is the most common justification for building, and it's wrong about 70% of the time.

## Framework

**The Build vs. Buy Decision Matrix:**

| Factor | Build | Buy | Partner/Hybrid |
|--------|-------|-----|----------------|
| **Competitive advantage** | Core differentiator | Commodity capability | Adjacent to core |
| **Data uniqueness** | Truly proprietary data | Standard industry data | Proprietary data, standard methods |
| **Internal talent** | Strong ML team (5+) | No ML team | Some talent, need acceleration |
| **Time pressure** | 12+ months acceptable | Need results in < 6 months | 6-12 month window |
| **Budget** | Can invest $500K+ | Under $200K | $200-500K range |
| **Maintenance appetite** | Can staff ongoing ops | Want vendor to manage | Shared responsibility |

**The hidden costs people forget:**

- **Build:** Ongoing maintenance is 2-4x the initial build cost over 3 years. You're not just building a model — you're building a team, a pipeline, a monitoring system, and an on-call rotation.
- **Buy:** Vendor lock-in, data portability issues, and the "80% fit" problem where the last 20% of customization costs more than the first 80%.
- **Partner:** Coordination overhead. Two teams, two roadmaps, two sets of priorities that will eventually conflict.

**Hot take:** Most organizations should buy first, learn what they actually need, then build only the components where they've proven the value and identified truly unique requirements. The "build everything" instinct is usually ego, not strategy.

## Your Move

Pick one AI initiative your org is considering. Score it against the six factors in the matrix above. Does the answer match your current plan? If there's a mismatch between what the matrix says and what the team wants to do, dig into why — that gap usually reveals assumptions worth challenging.

## Go Deeper

- [Gartner's Build, Buy, or Partner Framework](https://www.gartner.com/en/articles/build-buy-or-partner-how-to-decide) — Gartner's take on the decision framework with additional nuance on the "partner" option.
- [Harvard Business Review, "When to Build vs. Buy AI"](https://hbr.org/2020/10/is-your-company-actually-using-the-ai-it-is-buying) — Good reality check on what happens after the buy decision.
