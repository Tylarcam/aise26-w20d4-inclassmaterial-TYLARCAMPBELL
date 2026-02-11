# Scenario Cards: Bandit or Not?

These scenario cards are used in **Breakout 3** to practice deciding between multi-armed bandits and fixed A/B tests.

---

## Scenario Cards

### Card 1: The Homepage Redesign

**Context**: Major homepage redesign after 6 months of work, CEO is watching; success means 20% engagement lift, failure means rollback and credibility hit.

**Constraints**: 100,000 daily active users.

**Decision**: Bandit or Fixed A/B?

**Discussion Questions**:
- What happens if the new design is actually −5% worse but you do not detect it quickly?
- How will you report results to the board?
- What if engagement is up but revenue is down (metric collision)?

---

### Card 2: The Pricing Page Tweaks

**Context**: Testing 4 headline variations on the pricing page, low risk, current conversion 2%, any improvement directly impacts revenue.

**Constraints**: 5,000 visitors per week; showing a suboptimal headline has real monetary opportunity cost.

**Decision**: Bandit or Fixed A/B?

**Discussion Questions**:
- How much does "regret" (showing worse variants) cost per week?
- Do you need to know why one headline wins, or just which one?
- What if one variant is 50% better—how long do you want to keep showing the loser?

---

### Card 3: The Model Rollback

**Context**: New ranking model in production; suspected bug causing occasional bad results for a small user segment; you want to validate quality while protecting users.

**Constraints**: Real-time decisioning is required and bad results damage the brand.

**Decision**: Bandit or Fixed A/B? Or something else?

**Discussion Questions**:
- Is this actually an experiment, or monitoring with automatic rollback?
- What is the cost of a bad ranking?
- How do you balance exploration vs. user harm?

---

### Card 4: The Long-Term Effect

**Context**: Testing changes to notification frequency with concern about short-term engagement lift vs. long-term fatigue and churn.

**Constraints**: Need to measure 30-day retention; bandits optimize for immediate reward.

**Decision**: Bandit or Fixed A/B?

**Discussion Questions**:
- Can a bandit optimize for delayed rewards like 30-day retention?
- What is the reward at each step if true impact is delayed?
- How do you prevent exploiting short-term gains that cause long-term pain?

---

### Card 5: The Ethical Dimension

**Context**: Testing job recommendation algorithms; Variant A shows higher-paying jobs to Group X, Variant B is balanced across groups, and "better" is unknown.

**Constraints**: Fairness is a legal and ethical requirement, and variants differ in fairness properties.

**Decision**: Bandit or Fixed A/B?

**Discussion Questions**:
- Is it ethical to dynamically allocate users to a variant that may systematically disadvantage them?
- How do you measure reward when engagement and equity both matter?
- What does "optimal" mean in this context?

---

## Quick Reference: Bandits vs. A/B

| Dimension      | Fixed A/B Test                                        | Multi-Armed Bandit                                       |
|---------------|--------------------------------------------------------|----------------------------------------------------------|
| Traffic split | 50/50 (fixed)                                         | Dynamic (shifts to winner)                               |
| Goal          | Maximize learning (statistical certainty)             | Maximize reward (exploit while exploring)                |
| Best for      | High stakes, need definitive answer                   | Low stakes, high opportunity cost of wrong arm           |
| Regret        | High (wastes traffic on loser if effect is large)     | Lower (reduces exposure to suboptimal variant)           |
| Interpretability | High (clean p-values, confidence intervals)         | Lower (harder to report "significance")                  |
| Sample size   | Fixed upfront                                         | Variable (can stop early)                                |
| Complexity    | Simple                                                | Requires more sophisticated infrastructure                |

**Key insight**: Bandits optimize for the business metric during the experiment, while A/B tests optimize for certainty after the experiment.

