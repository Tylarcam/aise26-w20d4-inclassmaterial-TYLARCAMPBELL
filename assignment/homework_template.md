# Experiment Design Document

**Student Name:** [Your name]

**Date:** [Date]

**Course:** AISE26_W20D4 - Experiment Design

---

## Executive Summary

[2-3 sentences summarizing your experiment: what you're testing, why it matters, and what you expect to learn.]

---

## 1. Background & Motivation

### Problem Statement

[What problem are you trying to solve? What business or user need does this address?]

### Current State

[Describe the current state of the system/product. What metrics are you currently seeing?]

### Opportunity

[What opportunity exists? Why is this the right time to experiment?]

---

## 2. Hypothesis

Use the format:

> "If we **[change X]**, then **[metric Y]** will **[increase/decrease]** because **[mechanism Z]**."

**Your Hypothesis:**

> [Fill in your hypothesis here]

**Mechanism Explanation:**
[Explain the causal mechanism. Why do you believe this change will lead to the expected outcome?]

---

## 3. Experimental Design

### 3.1 Variants

| Variant   | Description     | Implementation Notes         |
| --------- | --------------- | ---------------------------- |
| Control   | [Current state] | [Any special considerations] |
| Treatment | [New state]     | [Any special considerations] |

### 3.2 Randomization

- **Randomization Unit:** [User ID / Session ID / Account / Device ID / Request]
- **Rationale:** [Why this unit? What are the tradeoffs?]
- **Assignment Method:** [How will users be assigned? Any stratification?]

### 3.3 Sample Size & Duration

- **Target Sample Size:** [Per variant and total]
- **Minimum Duration:** [e.g., 2 weeks]
- **Rationale:** [Why this duration? What business cycles does it cover?]

**Power Analysis:**

- Baseline rate: [e.g., 5%]
- MDE (relative): [e.g., 10%]
- α (significance level): [e.g., 0.05]
- Power: [e.g., 0.80]
- Calculated sample size: [Use power calculator or web tool]

---

## 4. Metrics

### 4.1 Primary Metric

- **Metric Name:** [e.g., Click-through rate]
- **Definition:** [Precise definition: event, denominator, time window]
- **Why this metric:** [Why is this the right metric to measure success?]
- **Calculation:** [Formula or pseudocode if needed]

### 4.2 Guardrail Metrics

| Metric     | Definition   | Why It Matters   | Threshold for Alarm |
| ---------- | ------------ | ---------------- | ------------------- |
| [Metric 1] | [Definition] | [Why it matters] | [Threshold]         |
| [Metric 2] | [Definition] | [Why it matters] | [Threshold]         |
| [Metric 3] | [Definition] | [Why it matters] | [Threshold]         |

### 4.3 Secondary Metrics

[Optional: Other metrics you'll track for learning, even if not primary or guardrails]

---

## 5. Stopping Rules & Analysis Plan

### 5.1 Stopping Rules

- **Minimum Duration:** [e.g., Must run for at least 2 weeks]
- **Early Stopping Criteria:** [When can you stop early?]
- **No-Peeking Protocol:** [How will you prevent premature decisions?]

### 5.2 Analysis Plan

- **Statistical Test:** [e.g., Two-proportion z-test, t-test, etc.]
- **Significance Level:** [e.g., α = 0.05]
- **Confidence Intervals:** [e.g., 95% CI]
- **Subgroup Analysis:** [Will you analyze any subgroups?]

---

## 6. Risks & Mitigations

| Risk     | Impact            | Likelihood        | Mitigation            |
| -------- | ----------------- | ----------------- | --------------------- |
| [Risk 1] | [High/Medium/Low] | [High/Medium/Low] | [How you'll mitigate] |
| [Risk 2] | [High/Medium/Low] | [High/Medium/Low] | [How you'll mitigate] |
| [Risk 3] | [High/Medium/Low] | [High/Medium/Low] | [How you'll mitigate] |

**Potential Confounders:**

- Seasonality: [How will you account for this?]
- Novelty effects: [How will you detect/account for this?]
- External events: [What external factors could affect results?]
- Network effects: [Could variants affect each other?]

---

## 7. Implementation Plan

### 7.1 Technical Requirements

- **Infrastructure:** [What systems need to be modified?]
- **Data Collection:** [How will you collect metrics?]
- **Monitoring:** [How will you monitor the experiment?]

### 7.2 Rollout Plan

- **Phases:** [Will you roll out gradually or all at once?]
- **Traffic Allocation:** [What % of traffic to each variant?]
- **Geographic Considerations:** [Any geographic restrictions?]

### 7.3 Rollback Plan

[What triggers a rollback? How quickly can you rollback?]

---

## 8. Success Criteria

### 8.1 Definition of Success

[What does success look like? Be specific with numbers if possible.]

### 8.2 Decision Framework

| Outcome                                                | Action                                 |
| ------------------------------------------------------ | -------------------------------------- |
| Primary metric significantly positive, guardrails pass | [e.g., Roll out to 100%]               |
| Primary metric significantly negative                  | [e.g., Rollback]                       |
| Primary metric not significant, guardrails fail        | [e.g., Rollback]                       |
| Primary metric not significant, guardrails pass        | [e.g., Extend experiment or no change] |

---

## 9. Post-Experiment Plan

### 9.1 If Successful

[What happens next? Full rollout? Further experiments?]

### 9.2 If Unsuccessful

[What did you learn? What will you try next?]

### 9.3 Documentation

[How will you document and share learnings?]

---

## 10. References & Resources

- [Any papers, blog posts, or internal docs you referenced]
- [Links to related experiments or analyses]

---

## Appendix

### A. Power Analysis Details

[Detailed calculations or screenshots from power calculator]

### B. Technical Specifications

[Any additional technical details, API specs, etc.]

### C. Additional Notes

[Any other relevant information]
