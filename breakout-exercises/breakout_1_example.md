# Experiment Spec: Homepage Recommendation Carousel

---

## 1. Hypothesis

> "If we add a 'Recommended for You' carousel to the top of the homepage, then the click-through rate (CTR) on products will increase by 15%, because users will immediately see relevant items without needing to scroll or search."

---

## 2. Primary Metric

- **Metric:** Homepage Product CTR (Clicks / Unique Pageviews)
- **Why:** This directly measures whether the carousel captures user attention as predicted by the hypothesis.

---

## 3. Guardrail Metrics

| Guardrail              | Why It Matters                                                                 | Threshold for Alarm                          |
| ---------------------- | ------------------------------------------------------------------------------ | ------------------------------------------- |
| Page Load Time         | Adding the carousel model inference shouldn't slow down the site               | Must not increase by more than 100ms        |
| Revenue Per User       | Ensures we aren't distracting users from higher-value items                     | Must not drop by more than 2%               |
| Customer Support Tickets | Don't introduce navigation confusion                                        | No significant increase in "navigation confusion" tickets |

---

## 4. Randomization Unit

- **Unit:** User ID
- **Why:** We need a consistent experience. If a user refreshes the page, the carousel shouldn't disappear. This ensures the treatment is stable for that person.

---

## 5. Duration & Stopping Rule

- **Duration:** 2 full weeks (to capture both weekday and weekend traffic cycles)
- **Stopping Rule:** Stop only when we reach the calculated sample size (e.g., 50,000 users) **and** the 2-week duration is complete
- **No-Peeking:** We commit to not stopping early even if results look "significant" on Day 3

---

## 6. Risk Notes

- **Novelty Effect:** Users might click the carousel just because it is new. We should monitor whether CTR spikes in Week 1 and drops in Week 2.
- **Cannibalization:** The carousel might steal clicks from the main search bar, potentially hurting users who know exactly what they want.
