# Experiment Specification One-Pager

**Experiment Name:** [Your experiment name]

**Date:** [Date]

**Team:** [Your team/name]

---

## 1. Hypothesis

Use the format:

> "If we **[change X]**, then **[metric Y]** will **[increase/decrease]** because **[mechanism Z]**."

**Your Hypothesis:**

> [Fill in your hypothesis here]

---

## 2. Primary Metric (1 only)

* What single metric determines success?
* Why this metric and not others?
* How is it calculated? (event definition, denominator, time window)

**Primary Metric:**

- **Metric Name:** [e.g., Click-through rate]
- **Why this metric:** [Explain why this is the right metric]
- **Calculation:** [Define how it's calculated]
  - Event definition: [What event counts?]
  - Denominator: [What's the base?]
  - Time window: [Over what period?]

---

## 3. Guardrail Metrics (2–3)

Metrics that must not degrade:

| Guardrail        | Why It Matters                        | Threshold for Alarm |
| ---------------- | ------------------------------------- | ------------------- |
| [Metric 1]       | [Why it matters]                      | [Threshold]         |
| [Metric 2]       | [Why it matters]                      | [Threshold]         |
| [Metric 3]       | [Why it matters]                      | [Threshold]         |

---

## 4. Randomization Unit

Options:
* User ID
* Session ID
* Account/Organization
* Device ID
* Request/Impression

**Your Choice:** [Select one]

**Explanation:** [Explain your choice and tradeoffs]

---

## 5. Duration & Stopping Rule

* Minimum duration (e.g., 2 full business cycles)
* Target sample size (if calculated)
* Stopping rule (e.g., primary metric significant at α = 0.05 with 2-week minimum)
* No-peeking promise: How do you prevent premature decisions?

**Duration Plan:**

- **Minimum Duration:** [e.g., 2 weeks]
- **Target Sample Size:** [If calculated, include per variant and total]
- **Stopping Rule:** [Define when to stop]
- **No-Peeking Protocol:** [How you'll prevent premature decisions]

---

## 6. Risk Notes

Potential confounders:

* Seasonality
* Novelty effects
* External events (marketing campaigns, holidays)
* Network effects across variants

**Identified Risks:**

1. [Risk 1 and mitigation]
2. [Risk 2 and mitigation]
3. [Risk 3 and mitigation]

---

## Quality Checklist

* [ ] Hypothesis includes mechanism
* [ ] Primary metric is singular and measurable
* [ ] Guardrails cover business risks
* [ ] Randomization unit matches the hypothesis
* [ ] Duration accounts for business cycles
* [ ] At least one confounding risk acknowledged

