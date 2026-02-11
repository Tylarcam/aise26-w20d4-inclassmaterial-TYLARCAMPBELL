# Breakout 1: Experiment Spec One-Pager

## Overview

* **Duration:** 25 minutes
* **Format:** Small groups (3–4 fellows)
* **Deliverable:** One-page experiment specification (paste in chat)

## Objective

Practice translating a product or ML idea into a rigorous, testable experiment plan that could be deployed in production.

## Instructions

### Step 1: Choose Your Scenario (5 min)

Pick one of the following or propose your own:

* Product Feature: Add a "recommended for you" carousel to the homepage
* Model Change: Increase diversity in ranking using an MMR penalty
* UX Tweak: Change the primary CTA button color from blue to green
* Prompt Engineering: Switch to a new system prompt to reduce hallucinations
* Your own idea

### Step 2: Draft Your Spec (15 min)

Complete all sections below with enough specificity for engineering implementation.

---

## 1. Hypothesis

Use the format:

> "If we  **[change X]** , then **[metric Y]** will **[increase/decrease]** because  **[mechanism Z]** ."

**Example:**

> "If we add a 'recommended for you' carousel above the fold, then click-through rate will increase 15% because users will see relevant items without scrolling."

---

## 2. Primary Metric (1 only)

* What single metric determines success?
* Why this metric and not others?
* How is it calculated? (event definition, denominator, time window)

---

## 3. Guardrail Metrics (2–3)

Metrics that must not degrade:

| Guardrail        | Why It Matters                        | Threshold for Alarm |
| ---------------- | ------------------------------------- | ------------------- |
| Revenue per user | We can't sacrifice revenue for clicks | Drop > 2%           |
| Page load time   | UX degradation                        | Increase > 100ms    |
| Support tickets  | Don't break things                    | Increase > 10%      |

---

## 4. Randomization Unit

Options:

* User ID
* Session ID
* Account/Organization
* Device ID
* Request/Impression

Explain your choice and tradeoffs.

---

## 5. Duration & Stopping Rule

* Minimum duration (e.g., 2 full business cycles)
* Target sample size (if calculated)
* Stopping rule (e.g., primary metric significant at α = 0.05 with 2-week minimum)
* No-peeking promise: How do you prevent premature decisions?

---

## 6. Risk Notes

Potential confounders:

* Seasonality
* Novelty effects
* External events (marketing campaigns, holidays)
* Network effects across variants

---

## Step 3: Share & Get Feedback (5 min)

Paste your spec in the main chat. Others should ask one clarifying question or identify one missed risk.

---

## Quality Checklist

* [ ] Hypothesis includes mechanism
* [ ] Primary metric is singular and measurable
* [ ] Guardrails cover business risks
* [ ] Randomization unit matches the hypothesis
* [ ] Duration accounts for business cycles
* [ ] At least one confounding risk acknowledged
