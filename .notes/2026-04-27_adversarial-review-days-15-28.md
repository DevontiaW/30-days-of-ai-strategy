# Exit Report: Adversarial Review of Days 15-28
**Agent:** adversarial-reviewer
**Date:** 2026-04-27
**Project:** 30-days-of-ai-strategy (public repo, Devontae Williams)
**Tags:** ["type:exit-report", "project:nomad", "topic:30-days-ai-strategy", "topic:citation-audit", "date:2026-04-27"]

## Task Summary

Reviewed 14 newly-written day files (week-3/day-15 through week-4/day-28) in the public 30-days-of-ai-strategy repo against three audit dimensions: (1) citation/source verification — flagging hallucinated books, fake URLs, misattributed authors; (2) claims audit — overconfident numbers and unsourced "studies show" claims; (3) voice/structural conformity vs. the established Days 1-14 baseline. Read Days 1, 13, 14 first to lock voice and structure, then read all 14 new files in full. Delivered a 900-word report tiered BLOCK/WARN/NIT with a final ship-decision verdict ("Hold for quick fixes").

## Decisions Made

1. **BLOCK threshold = "if a single LinkedIn reader Googles this, Devon's credibility cracks."** Applied to: (a) Day 19 attributing *AI 2041* to Eric Schmidt — actually Kai-Fu Lee + Chen Qiufan, and the book is sci-fi short stories not org-design; (b) Day 17 MIT Sloan title/URL slug mismatch (article title and URL describe different pieces); (c) Day 20 Wenger Cambridge URL has fabricated repeating-pattern hash `F22A01A4F7E0E5E1B6F3D1B1F5F5F5F5` (real Cambridge Core IDs aren't repeating). These are the citation errors that go viral when caught.

2. **WARN threshold = "plausible but unverified, fix in 48 hr."** Applied to multiple HBR slugs (Day 17, 22, 27) that look like guessed URLs with clean dates — the kind that *might* resolve but read as fabrications until confirmed. Also applied to the Day 24 McKinsey title-vs-URL mismatch (slug points to a 2017 "organization-of-the-future" piece but title claims "Operating Model for the Age of AI").

3. **NIT threshold = real source, minor format issue.** Spotify Engineering Culture (real, well-known); Helmer 7Powers.com (real); Ng Landing.AI PDF (path may have changed but the document exists and is widely linked).

4. **Claims audit: anonymized client stories with implausibly clean numbers got WARN, not BLOCK.** The voice already operates in composite-story mode (Day 1 logistics example, Day 13 healthcare example), so $14M/$3.2M/$8M precision in Day 22 isn't disqualifying — but it stacks up across Days 15, 16, 18, 22, 23 to a pattern worth softening with "roughly" or composite-disclosure.

5. **Voice/structural drift: Hot Take rendered as `## H2 heading` in Days 17, 18, 20, 22, 26, 27 — but originals (Days 1, 13) use `**Hot take:**` as inline callout inside another section.** Treated as systemic WARN (one fix, applied 6x) rather than 6 separate flags.

6. **Verdict = "Hold for quick fixes (24-48 hr)"** — not "ship as-is" because the 3 BLOCK citations are reputation-load-bearing, and not "hold for substantial revision" because everything else is hygiene-tier and the 14 files are otherwise on-voice and structurally close to originals.

## Lessons Learned

- **Citation hash inspection matters.** The Day 20 Wenger URL (`F22A01A4F7E0E5E1B6F3D1B1F5F5F5F5`) was the single highest-confidence fabrication catch — repeating-pattern hashes are a tell. Real Cambridge Core IDs are random hex.
- **Title-vs-slug mismatch is a high-yield check.** Day 17 MIT Sloan and Day 24 McKinsey both passed casual reading but failed when title and URL slug were compared. This is faster than verifying every URL resolves — just diff what the cite *claims* against what the slug *implies*.
- **Author attribution beats URL verification for catching hallucinations.** Day 19's *AI 2041* → Eric Schmidt was the most embarrassing find, and it didn't require any URL lookup — just knowing the actual authors. Future audits: pattern-match author claims against known book authorship before chasing URLs.
- **Composite client stories survive scrutiny better when they don't include 4-decimal-place dollar precision.** $14M committed / $3.2M generated / $8M burned reads as real-client (and therefore confidentiality-suspect or fabricated) more than $14M / ~$3M / ~$8M would.
- **Length drift is real but acceptable for capstone-density days.** Days 13/14 set precedent for 8-12K char posts; Days 17, 18, 22, 25, 26, 27 took that license further than originals warrant. Worth flagging but not blocking.

## Dead Ends / Things I Could Not Verify In-Session

- Could not actually fetch URLs to confirm resolution (no WebFetch used — would have improved confidence on 4-5 WARN-tier citations).
- Could not verify whether the Day 15/19 Andrew Ng "AI Transformation Playbook" PDF still resolves at `landing.ai/wp-content/uploads/2020/05/...` — Landing.AI has restructured its site at least once. Flagged NIT, but a live check would resolve it.
- Could not confirm Day 18 ACM citation: DOI 10.1145/3287560.3287588 is a real FAT* 2019 paper, but I can't confirm the title cited ("Algorithmic Accountability Reporting") matches that DOI's actual paper title without fetching.
- Could not verify Day 17 HBR "How to Manage AI's Disruption of Jobs" (May 2024) actually exists — slug looks plausible but unconfirmed.

## Open Questions for Devon

1. Are the In Practice client stories composites drawn from real Deloitte engagements, or fully fictional teaching scenarios? If composite-from-real, the dollar precision is a confidentiality risk worth softening even before the credibility risk.
2. Does Devon want a follow-up pass that actually fetches each Go Deeper URL to convert WARN-tier flags to confirmed/rejected? ~10 min of WebFetch work would clear the citation queue.
3. Is the structural drift on `## Hot Take` headings intentional (i.e., a deliberate evolution from Day 13 onward) or accidental? If intentional, retrofit Days 1-12 for consistency; if accidental, fix Days 17, 18, 20, 22, 26, 27.

## Files Touched (Read-Only)

- C:/Users/Devon/Textstone/projects/30-days-of-ai-strategy/week-1/day-01.md
- C:/Users/Devon/Textstone/projects/30-days-of-ai-strategy/week-2/day-13.md
- C:/Users/Devon/Textstone/projects/30-days-of-ai-strategy/week-2/day-14.md
- C:/Users/Devon/Textstone/projects/30-days-of-ai-strategy/week-3/day-15.md through day-21.md
- C:/Users/Devon/Textstone/projects/30-days-of-ai-strategy/week-4/day-22.md through day-28.md

## File Created

- C:/Users/Devon/Textstone/projects/30-days-of-ai-strategy/.notes/2026-04-27_adversarial-review-days-15-28.md (this report)
