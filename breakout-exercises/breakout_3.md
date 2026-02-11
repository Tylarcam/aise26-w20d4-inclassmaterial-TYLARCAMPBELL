# Breakout 3: Bandit or Not?

## Overview

-**Duration**: 35 minutes [file:2]

-**Format**: Small groups (3–4 fellows) [file:2]

-**Materials**: Scenario cards (below) [file:2]

-**Deliverable**: Decision + justification for 2 scenarios posted in chat [file:2]

**Objective**: Learn when multi-armed bandits outperform fixed A/B tests, and what you sacrifice when you choose adaptive experimentation. [file:2]

---

## Quick Primer: Bandits vs. A/B

| Dimension      | Fixed A/B Test                                        | Multi-Armed Bandit                                       |

|---------------|--------------------------------------------------------|----------------------------------------------------------|

| Traffic split | 50/50 (fixed) [file:2]                                 | Dynamic (shifts to winner) [file:2]                      |

| Goal          | Maximize learning (statistical certainty) [file:2]     | Maximize reward (exploit while exploring) [file:2]       |

| Best for      | High stakes, need definitive answer [file:2]           | Low stakes, high opportunity cost of wrong arm [file:2]  |

| Regret        | High (wastes traffic on loser if effect is large) [file:2] | Lower (reduces exposure to suboptimal variant) [file:2]  |

| Interpretability | High (clean p-values, confidence intervals) [file:2] | Lower (harder to report “significance”) [file:2]         |

| Sample size   | Fixed upfront [file:2]                                 | Variable (can stop early) [file:2]                       |

| Complexity    | Simple [file:2]                                        | Requires more sophisticated infrastructure [file:2]      |

**Key insight**: Bandits optimize for the business metric during the experiment, while A/B tests optimize for certainty after the experiment. [file:2]

---

## Scenario Cards

### Card 1: The Homepage Redesign

-**Context**: Major homepage redesign after 6 months of work, CEO is watching; success means 20% engagement lift, failure means rollback and credibility hit. [file:2]

-**Constraints**: 100,000 daily active users. [file:2]

-**Decision**: Bandit or Fixed A/B? [file:2]

**Discuss**

- What happens if the new design is actually −5% worse but you do not detect it quickly? [file:2]
- How will you report results to the board? [file:2]
- What if engagement is up but revenue is down (metric collision)? [file:2]

---

### Card 2: The Pricing Page Tweaks

-**Context**: Testing 4 headline variations on the pricing page, low risk, current conversion 2%, any improvement directly impacts revenue. [file:2]

-**Constraints**: 5,000 visitors per week; showing a suboptimal headline has real monetary opportunity cost. [file:2]

-**Decision**: Bandit or Fixed A/B? [file:2]

**Discuss**

- How much does “regret” (showing worse variants) cost per week? [file:2]
- Do you need to know why one headline wins, or just which one? [file:2]
- What if one variant is 50% better—how long do you want to keep showing the loser? [file:2]

---

### Card 3: The Model Rollback

-**Context**: New ranking model in production; suspected bug causing occasional bad results for a small user segment; you want to validate quality while protecting users. [file:2]

-**Constraints**: Real-time decisioning is required and bad results damage the brand. [file:2]

-**Decision**: Bandit or Fixed A/B? Or something else? [file:2]

**Discuss**

- Is this actually an experiment, or monitoring with automatic rollback? [file:2]
- What is the cost of a bad ranking? [file:2]
- How do you balance exploration vs. user harm? [file:2]

---

### Card 4: The Long-Term Effect

-**Context**: Testing changes to notification frequency with concern about short-term engagement lift vs. long-term fatigue and churn. [file:2]

-**Constraints**: Need to measure 30-day retention; bandits optimize for immediate reward. [file:2]

-**Decision**: Bandit or Fixed A/B? [file:2]

**Discuss**

- Can a bandit optimize for delayed rewards like 30-day retention? [file:2]
- What is the reward at each step if true impact is delayed? [file:2]
- How do you prevent exploiting short-term gains that cause long-term pain? [file:2]

---

### Card 5: The Ethical Dimension

-**Context**: Testing job recommendation algorithms; Variant A shows higher-paying jobs to Group X, Variant B is balanced across groups, and “better” is unknown. [file:2]

-**Constraints**: Fairness is a legal and ethical requirement, and variants differ in fairness properties. [file:2]

-**Decision**: Bandit or Fixed A/B? [file:2]

**Discuss**

- Is it ethical to dynamically allocate users to a variant that may systematically disadvantage them? [file:2]
- How do you measure reward when engagement and equity both matter? [file:2]
- What does “optimal” mean in this context? [file:2]

---

## Deliverable Format

For two scenarios of your choice, post: [file:2]

- Scenario: [Card #]
- Decision: [Bandit / Fixed A/B / Hybrid / No Experiment]
- Why: [2–3 sentences]
- What We Lose: [If we chose the other option, what would we sacrifice?]

**Example**: [file:2]

- Scenario: Card 2 (Pricing Headlines)
- Decision: Thompson Sampling Bandit
- Why: Low risk, high opportunity cost of suboptimal headline; focus is on revenue now, not statistical purity; 4 variants make fixed A/B slow. [file:2]
- What We Lose: With fixed A/B, you would get clean confidence intervals for each headline for future copy decisions, but a bandit obscures “loser” performance. [file:2]

---

## Further Reading

- [Google Analytics Multi-Armed Bandit Experiments](navigational_search:Google Analytics bandit experiments) [file:2]
- Contextual bandits (personalized assignment) vs. simple bandits [file:2]
- Bayesian A/B testing as a middle ground [file:2]
