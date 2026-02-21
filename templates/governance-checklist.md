# Minimum Viable AI Governance Checklist

*This isn't meant to be comprehensive. It's meant to be practical — the smallest set of governance practices that meaningfully reduce risk without killing momentum. Start here, then expand based on your risk profile and regulatory environment.*

---

## How to Use This

For each AI system or model going to production, work through these sections. Not every item applies to every project — use the risk classification to determine what's required vs. recommended.

**Risk levels:**
- **Low:** Internal tools, human-in-the-loop, no PII. Complete required items only.
- **Medium:** Customer-affecting, uses PII, financial impact. Complete required + recommended.
- **High:** Autonomous decisions, regulated domains, safety-critical. Complete all items + external review.

---

## 1. Data Privacy and Security

| # | Item | Required | Status |
|---|------|----------|--------|
| 1.1 | Data sources documented (where does training/inference data come from?) | All | [ ] |
| 1.2 | PII identified and classified | All | [ ] |
| 1.3 | Data retention and deletion policy defined | Medium+ | [ ] |
| 1.4 | Consent/legal basis for data use confirmed | Medium+ | [ ] |
| 1.5 | Data access controls in place (who can see what?) | All | [ ] |
| 1.6 | Cross-border data transfer requirements checked | Medium+ | [ ] |
| 1.7 | Data anonymization/pseudonymization applied where needed | High | [ ] |

**Notes:**

---

## 2. Model Documentation

| # | Item | Required | Status |
|---|------|----------|--------|
| 2.1 | Model card created (purpose, training data, limitations, intended use) | All | [ ] |
| 2.2 | Training data composition documented (sources, size, time period) | Medium+ | [ ] |
| 2.3 | Performance metrics defined and measured (accuracy, precision, recall, etc.) | All | [ ] |
| 2.4 | Known limitations and failure modes documented | All | [ ] |
| 2.5 | Version control for models and training data | Medium+ | [ ] |
| 2.6 | Decision logic explainable to a non-technical stakeholder | High | [ ] |

**Notes:**

---

## 3. Bias and Fairness Testing

| # | Item | Required | Status |
|---|------|----------|--------|
| 3.1 | Protected attributes identified (race, gender, age, etc.) | Medium+ | [ ] |
| 3.2 | Training data checked for representation bias | Medium+ | [ ] |
| 3.3 | Model outputs tested for disparate impact across groups | High | [ ] |
| 3.4 | Fairness metrics defined and measured | High | [ ] |
| 3.5 | Bias mitigation strategy documented (if bias detected) | High | [ ] |
| 3.6 | Regular re-testing schedule established | High | [ ] |

**Notes:**

---

## 4. Human Oversight

| # | Item | Required | Status |
|---|------|----------|--------|
| 4.1 | Human-in-the-loop or human-on-the-loop defined | All | [ ] |
| 4.2 | Override mechanism exists (humans can correct or stop the system) | All | [ ] |
| 4.3 | Escalation path defined (when does a human review AI decisions?) | Medium+ | [ ] |
| 4.4 | Users informed when interacting with AI (transparency) | Medium+ | [ ] |
| 4.5 | Decision authority clearly assigned (AI recommends vs. AI decides) | All | [ ] |

**Notes:**

---

## 5. Monitoring and Incident Response

| # | Item | Required | Status |
|---|------|----------|--------|
| 5.1 | Performance monitoring in production (model drift, accuracy degradation) | Medium+ | [ ] |
| 5.2 | Alert thresholds defined (when does degradation trigger action?) | Medium+ | [ ] |
| 5.3 | Incident response plan documented (what happens when the model fails?) | All | [ ] |
| 5.4 | Rollback plan exists (can you revert to previous version or manual process?) | All | [ ] |
| 5.5 | Incident log maintained (track issues, root causes, resolutions) | Medium+ | [ ] |
| 5.6 | Regular review schedule established (quarterly minimum) | Medium+ | [ ] |

**Notes:**

---

## Sign-Off

| Role | Name | Date | Approved? |
|------|------|------|-----------|
| Project owner | | | [ ] |
| Data/privacy lead | | | [ ] |
| Technical lead | | | [ ] |
| Legal/compliance (medium+ risk) | | | [ ] |
| Executive sponsor (high risk) | | | [ ] |

**System name:** ___________
**Risk classification:** Low / Medium / High
**Review date:** ___________
**Next review:** ___________
