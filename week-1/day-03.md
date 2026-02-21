# Day 03: Data Readiness Assessment

## The Idea

Here's the uncomfortable truth most AI vendors won't tell you: your data probably isn't ready. Not because you don't have enough of it — most organizations are drowning in data. The problem is accessibility, quality, and governance. If you can't find last quarter's customer churn numbers in under five minutes, you're not ready for a machine learning initiative. Full stop.

Data readiness isn't a binary. It's a spectrum, and knowing where you actually sit on that spectrum is the most important diagnostic you can run before investing in AI.

## In Practice

A retail client wanted to build a demand forecasting model. They had "years of sales data." Sounds great on paper.

When we actually tried to assemble a training dataset, here's what we found: sales data lived in three different systems (POS, e-commerce, wholesale) with different product taxonomies. Returns were tracked separately and couldn't be reliably matched to original sales. Promotional pricing was in spreadsheets on a regional manager's laptop. And two years of data from their old POS system had been archived in a format nobody could read.

We spent four months on data engineering before we touched a single model. That's not unusual — it's typical. Gartner estimates organizations spend 60-80% of AI project time on data preparation.

**Hot take:** The best investment most companies can make before any AI initiative is a boring, unglamorous data infrastructure project. Clean pipes before you install fancy fixtures.

## Framework

**The 5-Level Data Maturity Model:**

```
Level 5: Optimized    → Data is a managed product. Cataloged, governed, self-serve.
Level 4: Managed      → Centralized data platform. Quality monitoring. Clear ownership.
Level 3: Defined      → Documented standards. Some integration. Known quality issues.
Level 2: Developing   → Data in silos. Manual reporting. Tribal knowledge.
Level 1: Initial      → Spreadsheets everywhere. No single source of truth.
```

**Quick Readiness Checklist:**

- [ ] Can you access your core business data without asking someone to pull a report?
- [ ] Do you have a data dictionary or catalog that's actually up to date?
- [ ] Is there a single source of truth for your key metrics (revenue, customers, inventory)?
- [ ] Can you join data across your main systems (CRM + ERP + product)?
- [ ] Do you know who owns each major dataset and who's responsible for quality?
- [ ] Is your data retention and privacy policy documented and enforced?
- [ ] Can a new analyst get productive with your data in under a week?

**Scoring:** 0-2 checks = Level 1-2, plan a data foundation project first. 3-4 = Level 3, you can start targeted AI pilots but expect data prep overhead. 5-7 = Level 4-5, you're in good shape to move fast.

## Your Move

Run the checklist above honestly — not how you'd like things to be, but how they actually are right now. If you score below 3, your most strategic AI move isn't an AI project at all. It's a data infrastructure investment that makes every future AI initiative faster and cheaper. Write down the two biggest gaps and who owns fixing them.

## Go Deeper

- [Gartner Data Management Maturity Model](https://www.gartner.com/en/documents/data-management-maturity-model) — More detailed maturity assessment if you want to go deeper.
- [Harvard Business Review, "What AI-Driven Companies Do Differently"](https://hbr.org/2021/12/what-ai-driven-companies-do-differently) — The data infrastructure investments that separate AI leaders from laggards.
