# Breakout 2: Power & Sample Size Scenarios

## Overview

- **Duration**: 25 minutes
- **Format**: Small groups (3–4 fellows)
- **Tools**: [Evan Miller Sample Size Calculator](navigational_search:Evan Miller sample size calculator) (or spreadsheet)
- **Deliverable**: Answers to 3 scenarios + one insight posted in chat

**Objective**: Build intuition for the relationship between statistical power, effect size, and sample size so you can plan realistic experiments. [file:1]

---

## Key Concepts

| Term       | Definition                                                                | Typical Value     |
| ---------- | ------------------------------------------------------------------------- | ----------------- |
| α (alpha) | Probability of false positive (Type I error) [file:1]                     | 0.05 (5%)         |
| β (beta)  | Probability of false negative (Type II error) [file:1]                    | 0.20 (20%)        |
| Power      | Probability of detecting true effect (1 − β) [file:1]                   | 0.80 (80%)        |
| MDE        | Minimum Detectable Effect—smallest lift you can reliably detect [file:1] | Context-dependent |
| Baseline   | Current conversion/metric rate (your data) [file:1]                       | Your data         |

**Tradeoff**: Smaller MDE → Larger sample size → Longer experiment. [file:1]

---

## Scenario 1: The Standard Test

**Context**: You run a SaaS product. Current trial-to-paid conversion is 5%. You want to detect a 10% relative improvement (5% → 5.5% absolute). [file:1]

**Task**

1. Go to the Evan Miller calculator. [file:1]
2. Enter: Baseline = 5%, Minimum Detectable Effect = 10% (relative), α = 0.05, Power = 0.80. [file:1]
3. Record: Sample size per variant = ______. [file:1]
4. Calculate: Total users needed (both variants) = ______. [file:1]

**Question**: If you have 1,000 users per week, how many weeks must you run?

---

## Scenario 2: The Shrinking MDE

**Context**: Same baseline (5%), but now you want to detect a 5% relative improvement (5% → 5.25% absolute). [file:1]

**Task**

1. Recalculate with MDE = 5% relative. [file:1]
2. Record: Sample size per variant = ______. [file:1]
3. Compare to Scenario 1: The sample size is ______ times larger. [file:1]

**Question**: Why does detecting a smaller effect require so much more traffic? Explain in one sentence. [file:1]

---

## Scenario 3: The Power Play

**Context**: Your CEO wants results in 2 weeks (2,000 total users). Baseline is still 5%. [file:1]

**Task**

1. With 2,000 total users (1,000 per variant), determine the smallest relative effect you can detect with 80% power. [file:1]
2. Use the calculator in reverse (or trial and error) to find the MDE. [file:1]

**Question**: If the true effect is 8% relative lift, what is your actual power with n = 1,000 per variant? (Set MDE to 8% relative and read the power.) [file:1]

---

## Scenario 4: The Business Reality Check

**Context**: Your product has low traffic (200 users/week). Your team wants to test a new onboarding flow. [file:1]

**Options**

- A) Run standard A/B with MDE = 20% (will take 8 weeks). [file:1]
- B) Run for 2 weeks with MDE = 40% (high risk of missing small wins). [file:1]
- C) Switch to a bandit approach (explore/exploit dynamically). [file:1]
- D) Do not experiment—just ship and pray. [file:1]

**Discuss**

1. What do you lose with each option? [file:1]
2. What would you recommend to your PM? [file:1]
3. What guardrails would you add for your chosen approach? [file:1]

---

## Deliverable (For Fellows)

Post in chat:

1. Your answers for Scenarios 1–3 (numbers only). [file:1]
2. One insight that surprised you about sample size planning. [file:1]
3. Your group’s recommendation for Scenario 4 with one reason. [file:1]

---

## Quick Reference: Sample Size Formula (Conceptual)

\[
n \approx 16 \times \sigma^{2} / (\text{MDE})^{2}
\] [file:1]
