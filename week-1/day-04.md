# Day 04: AI Use Case Prioritization

## The Idea

Most organizations start their AI journey with the wrong use case. They pick the one that's most technically interesting, or the one the CEO saw at a conference, or the one the vendor pitched most convincingly. None of these are good selection criteria.

Good use case prioritization balances two things: business impact and implementation feasibility. The magic quadrant here isn't about technology — it's about finding the intersection of "this would meaningfully move a business metric" and "we can actually pull this off with what we have."

## In Practice

A financial services firm brainstormed 23 AI use cases in a workshop. The team was excited about a real-time fraud detection system with graph neural networks. Sophisticated, cutting-edge, genuinely cool technology.

We scored all 23 use cases on impact and feasibility. The fraud detection system scored high on impact but low on feasibility — they didn't have the real-time data infrastructure, the ML team had no graph ML experience, and their current rule-based system was actually performing well.

The winner? Automated document classification for loan applications. Not sexy. But it touched 40,000 applications per month, the current process was entirely manual, the data was readily available, and off-the-shelf NLP could handle it. They deployed in 12 weeks and saved 6,200 staff hours in the first year.

The "cool" use case would have taken 18 months and might have failed. The "boring" one was in production and generating ROI before the fraud project would have finished its data pipeline.

## Framework

**The Impact-Feasibility Matrix:**

```
                    HIGH IMPACT
                        │
        ┌───────────────┼───────────────┐
        │               │               │
        │   STRATEGIC   │   QUICK       │
        │   BETS        │   WINS        │  ← Start here
        │  (Plan for)   │  (Do first)   │
        │               │               │
LOW ────┼───────────────┼───────────────┼──── HIGH
EASE    │               │               │    EASE
        │   DEPRIORI-   │   LOW-HANGING │
        │   TIZE        │   FRUIT       │
        │  (Probably     │  (Do if easy) │
        │   don't)      │               │
        │               │               │
        └───────────────┼───────────────┘
                        │
                    LOW IMPACT
```

**Scoring each use case (1-5 scale):**

**Impact factors:**
- Revenue potential or cost savings (quantified, not hand-wavy)
- Number of people or processes affected
- Strategic alignment with top 3 business priorities (from Day 01)
- Competitive differentiation potential

**Feasibility factors:**
- Data availability and quality (from Day 03 assessment)
- Technical complexity (off-the-shelf vs. custom research)
- Internal talent and skills match
- Organizational readiness and stakeholder buy-in
- Regulatory and compliance constraints

**Hot take:** Your first AI use case should almost never be customer-facing. Internal operations use cases have lower stakes, more forgiving error tolerances, and faster feedback loops. Get a win internally, build organizational confidence, then go external. McKinsey's data backs this up — the highest-ROI early AI initiatives are overwhelmingly in operations, not customer experience.

## Your Move

List your top 5 candidate AI use cases. Score each on impact (1-5) and feasibility (1-5) using the factors above. Plot them on the matrix. If your organization's current top priority isn't in the "Quick Wins" quadrant, have an honest conversation about why — and whether that's a strategic choice or organizational politics.

Use the [Use Case Canvas template](../templates/use-case-canvas.md) to flesh out the top candidate.

## Go Deeper

- [McKinsey, "The AI-Powered Enterprise"](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-ai-powered-enterprise) — Data on where AI use cases generate the most value by industry.
- [Deloitte AI Institute, "State of AI in the Enterprise"](https://www2.deloitte.com/us/en/pages/deloitte-analytics/articles/state-of-ai-in-the-enterprise.html) — Survey data on which use case categories have the highest success rates.
