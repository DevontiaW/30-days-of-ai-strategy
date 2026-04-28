# Day 24: Organizational Design for AI-Native Companies

## The Idea

There are three structural patterns for how AI capability lives inside an organization. Centralized, embedded, and hybrid. Each has tradeoffs. Each fits different organizational stages. None is universally right.

The reason this matters: org design determines what AI work happens, who owns it, and how fast it scales. Get it right and AI becomes a capability the whole org can pull from. Get it wrong and you build a corporate Center of Excellence that produces beautiful slides and ships nothing into production.

Most leaders pick an org structure based on what they've seen work somewhere else, not based on where their organization actually is in its AI maturity. That's the most common failure mode — the right structure for a 50,000-person AI-first tech company is not the right structure for a 1,500-person services firm just shipping its first pilot.

## In Practice

A specialty insurance company spent eighteen months building a centralized AI team. By mid-2025, they had 22 AI engineers, data scientists, and ML ops people in a single org reporting to the CTO. The team was strong, well-paid, and produced a steady stream of internal reports. They had also shipped exactly two systems into business operations in eighteen months.

The structural problem was visible to anyone who'd worked in the business. Every AI initiative had to be funneled through the central team. Underwriting wanted a tool to flag complex cases — they put in a request, got slotted into a roadmap, waited eight months, got a tool that mostly didn't fit their workflow because the central team had never sat in an underwriting meeting. Claims wanted a similar tool — different department, same pattern, same underwhelming output.

Meanwhile, an enterprising senior underwriter had built her own Claude-based tool using publicly available capabilities. She'd done it on weekends. It was already being used by her unit and improving cycle times measurably. The central AI team didn't know about it.

We restructured. The central team shrunk to 8 people focused on platform, governance, and the most technical initiatives. Twelve engineers were redistributed into "AI engineering" roles embedded in business units — one or two per major function. The central team kept ownership of platform decisions (model access, guardrails, evaluation tools) but stopped trying to be the singular source of all AI work.

Eighteen months later, the company had shipped 11 AI systems across underwriting, claims, fraud, customer service, and marketing. The central team was now a platform team that other units pulled from, not a delivery bottleneck. The senior underwriter who'd built her own tool had been promoted to lead AI engineering for underwriting.

The same headcount, restructured, produced 5x the business output. That's not unusual. That's the typical gap between centralized and hybrid models for mid-sized organizations.

## The Three Patterns

**Pattern 1: Centralized AI Team**

```
                ┌────────────────────────┐
                │                        │
                │   Central AI Team      │
                │   (CDO/CTO)            │
                │                        │
                │   • All AI engineers   │
                │   • All data scientists│
                │   • All ML ops          │
                │                        │
                └─────────┬──────────────┘
                          │
                          │ Requests
                          │
        ┌─────────┬───────┴───────┬─────────┐
        │         │               │         │
        ▼         ▼               ▼         ▼
    Business  Business        Business  Business
    Unit A    Unit B          Unit C    Unit D
```

**When it works:** Very early stage (no AI yet — you need a single team to learn together), or very specialized work (research labs, foundational platform work). Also works for organizations where AI is the core product, not a capability supporting other functions.

**When it fails:** When the central team becomes a bottleneck for business unit demand. When the central team lacks domain expertise in the units they're serving. When AI becomes "their thing, over there" rather than something every unit can pull from.

**Pattern 2: Embedded AI Engineering**

```
   ┌─────────────────────────────────────────────────┐
   │                                                 │
   │   Business Unit A         Business Unit B      │
   │   ─────────────────         ─────────────────  │
   │   • Domain experts          • Domain experts   │
   │   • AI engineers (2-3)      • AI engineers     │
   │   • Product/PM              • Product/PM       │
   │                                                 │
   │   ─────────────────         ─────────────────  │
   │                                                 │
   │   Business Unit C         Business Unit D      │
   │   ─────────────────         ─────────────────  │
   │   • Domain experts          • Domain experts   │
   │   • AI engineers (2-3)      • AI engineers     │
   │   • Product/PM              • Product/PM       │
   │                                                 │
   └─────────────────────────────────────────────────┘
```

**When it works:** Mature organizations with established AI practice, where each business unit can sustain its own AI engineering capacity and where coordination across units happens at the platform layer (shared models, shared infrastructure).

**When it fails:** When units don't have the budget or scale for dedicated AI engineering. When each unit reinvents the wheel. When governance, security, and ethical practices fragment because there's no central authority enforcing them.

**Pattern 3: Hybrid (Center of Excellence + Embedded)**

```
                ┌─────────────────────────────┐
                │                             │
                │   Center of Excellence      │
                │                             │
                │   • Platform engineering    │
                │   • ML governance           │
                │   • Foundation models       │
                │   • Cross-unit standards    │
                │   • Specialized expertise   │
                │     (research, etc.)        │
                │                             │
                └────────┬──────────┬─────────┘
                         │          │
                         │ Standards│ Platform
                         │ Support  │ Tools
                         ▼          ▼
        ┌──────────┬────────────────┬──────────┐
        │          │                │          │
   Business    Business         Business    Business
   Unit A      Unit B           Unit C      Unit D
   ─────────   ─────────        ─────────   ─────────
   AI Eng (2)  AI Eng (3)       AI Eng (1)  AI Eng (2)
   embedded    embedded         embedded    embedded
```

**When it works:** Mid-to-large organizations (1,000+ employees) past their first AI win. The CoE provides scale economies on platform, governance, and specialized capabilities. The embedded engineers provide domain depth and shipping velocity inside business units.

**When it fails:** When the CoE becomes a centralized bottleneck instead of a platform provider. When embedded engineers are organizationally isolated and lose technical depth without peer collaboration. When the CoE and embedded sides develop competing power structures.

This is the structure that fits most mid-sized organizations once they're past the first pilot. It's also the hardest to set up correctly.

## Choosing Your Pattern

**The decision matrix:**

```
   ORGANIZATION STAGE                      RECOMMENDED PATTERN
   ────────────────────────────────────────────────────────────
   No AI in production yet                Centralized (small)
   1-2 AI systems in production           Centralized → Hybrid
   3-10 AI systems in production          Hybrid (CoE + Embed)
   AI as core product/capability          Embedded (with platform)
   AI-first company                       Embedded (default)
```

Most mid-sized companies should be in the Hybrid model. Most are not — they're stuck in centralized because that's how they started, or they've fragmented into pure-embedded without a strong platform layer.

**Three signals you have the wrong structure:**

1. **Central team has a 6+ month backlog.** You're constraining demand from the business artificially. Move toward Hybrid.
2. **Multiple business units are independently buying the same AI vendor product.** You have no platform layer. Build a CoE.
3. **AI work is invisible to executives — they don't know what's running where.** You have an organizational visibility problem, often a sign of fragmented embedded model without coordination.

## Hot Take

**Hot take:** "Chief AI Officer" reporting to the CEO is usually the wrong call for non-tech companies. The role becomes either (a) a strategist disconnected from delivery, producing slide decks and external speaking engagements, or (b) a senior IC engineer awkwardly elevated into an executive role they don't have the political skills for. Both fail.

The pattern that works is a senior AI/ML lead reporting into the CTO or CDO, with a clear remit, real authority, and an explicit charter that includes platform building. That role becomes the platform spine for embedded engineering across the business. They don't need a C-suite title. They need budget authority and the ability to set standards.

Tech companies are different — there, "CAIO" can be a real role because AI is core product. For everyone else, beware title inflation.

## Your Move

Map your current AI org structure against the three patterns. Where are you?

Then ask: where *should* you be, given your stage? Use the decision matrix above as a starting point.

If there's a gap, the question becomes: what's the lowest-disruption path to the right structure? Restructuring is expensive and politically charged — but staying in the wrong structure is more expensive over time.

For most mid-sized organizations reading this, the right answer is some version of Hybrid. The path there from a centralized team is to redistribute some engineers into business units while preserving (and clarifying) the platform role of the central team. That's a 3-6 month restructure, not a one-week reorg.

Document the proposed structure. Share it with the CTO/CDO and the heads of the business units that would receive embedded engineers. Their reaction tells you what's politically possible.

## Go Deeper

- [Spotify Engineering Culture](https://engineering.atspotify.com/2014/03/27/spotify-engineering-culture-part-1/) — The "Spotify model" for embedded squads with platform-level guilds. Not specific to AI but the structural pattern translates directly.
- [BCG, "AI at Scale: How Successful Organizations Cross the Implementation Gap"](https://www.bcg.com/publications/2024/ai-at-scale-implementation) — Survey data on which org structures correlate with AI success. The Hybrid pattern wins on every metric they track for mid-to-large companies.
- [McKinsey, "The Operating Model for the Age of AI"](https://www.mckinsey.com/capabilities/people-and-organizational-performance/our-insights/the-organization-of-the-future-arriving-now) — The research behind centralized vs. embedded vs. hybrid structures, with case studies showing how organizations transitioned from one to the next.
