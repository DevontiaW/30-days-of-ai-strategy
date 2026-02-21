# Day 05: Governance Basics

## The Idea

AI governance has a branding problem. Most leaders hear "governance" and think compliance overhead — another layer of bureaucracy slowing things down. That framing is exactly wrong.

Good AI governance is a competitive advantage. It's what lets you move fast without breaking things that matter. It's risk management that enables innovation instead of blocking it. And increasingly, it's what your customers, regulators, and partners will require before they trust your AI systems.

The organizations that treat governance as an afterthought end up either moving too slowly (because every AI decision becomes a committee meeting) or too recklessly (because nobody's thinking about what happens when the model is wrong).

## In Practice

A B2B SaaS company launched an AI-powered lead scoring system without any governance framework. It worked great for six months. Then a major client asked three questions: "How does the model make decisions? What data does it use? How do you handle bias?"

The team couldn't answer any of them. The model was a black box — nobody had documented the training data, the feature importance, or the decision logic. The client paused their contract renewal pending answers.

That fire drill cost them eight weeks of engineering time to retrofit explainability, two weeks of legal review, and nearly a $2M annual contract. A basic governance framework upfront — documentation, testing protocols, an approval process — would have taken days, not weeks.

**Hot take:** Governance isn't the enemy of speed. Lack of governance is. The companies that move fastest with AI are the ones that have clear guardrails, because they spend zero time debating "should we do this?" on every project. The framework answers that question once, and then teams execute with confidence.

## Framework

**The Minimum Viable AI Governance Framework:**

```
┌──────────────────────────────────────────────┐
│  1. INVENTORY                                │
│  What AI systems do we have? Who owns them?  │
├──────────────────────────────────────────────┤
│  2. RISK CLASSIFICATION                      │
│  Low / Medium / High risk per use case       │
├──────────────────────────────────────────────┤
│  3. DOCUMENTATION STANDARD                   │
│  Model cards for every production system     │
├──────────────────────────────────────────────┤
│  4. REVIEW PROCESS                           │
│  Who approves what? (Scaled to risk level)   │
├──────────────────────────────────────────────┤
│  5. MONITORING + INCIDENT RESPONSE           │
│  How do we know when something goes wrong?   │
└──────────────────────────────────────────────┘
```

**Risk classification (keep it simple):**

- **Low risk:** Internal tools, efficiency improvements, no PII, human in the loop. Example: document classification for internal routing. Approval: team lead sign-off.
- **Medium risk:** Customer-affecting, uses PII, financial impact. Example: lead scoring, content recommendations. Approval: cross-functional review (product + legal + data science).
- **High risk:** Autonomous decisions, regulated domains, significant financial or safety impact. Example: credit scoring, clinical decision support. Approval: governance board + external audit.

Scale your process to the risk level. Low-risk use cases should have a lightweight checklist, not a committee. High-risk use cases deserve deep review. This gradient is what makes governance sustainable.

## Your Move

Take inventory. List every AI system or model currently in use at your organization — including the ones "someone on the team built" that aren't officially sanctioned. For each one, classify it as low, medium, or high risk. If you find high-risk systems with no documentation or review process, that's your governance priority #1.

Use the [Governance Checklist template](../templates/governance-checklist.md) as a starting point.

## Go Deeper

- [NIST AI Risk Management Framework](https://www.nist.gov/artificial-intelligence/ai-risk-management-framework) — The gold standard for AI risk management. Dense but thorough.
- [Google's Model Cards paper](https://arxiv.org/abs/1810.03993) — The original framework for documenting ML models. Simple, practical, widely adopted.
