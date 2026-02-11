# AISE26 W20D4: Experiment Design & Statistical Power

> "Shipping is not the finish line. We don't 'feel' improvements—we prove them."

## 📚 Overview

In Day 1 and Day 2 (Mini Project 2), we focused on **Code Quality**: shipping maintainable, bug-free code into an existing repository. Today, we shift to **Product Quality**. In a production ML environment, merging a PR is just the beginning. To verify that a model or feature actually adds value, we must design rigorous experiments, calculate statistical power, and choose the right deployment strategy.

## 🛠️ Essential Tools

- [Evan Miller Sample Size Calculator](https://www.evanmiller.org/ab-testing/sample-size.html) (Primary tool for Breakout 2)
- [Wikipedia: A/B Testing](https://en.wikipedia.org/wiki/A/B_testing)
- [Multi-Armed Bandits (Google Analytics)](https://analytics.googleblog.com/2013/01/multi-armed-bandit-experiments.html)

---

## 🚀 Quick Start

### 1. Clone Repository

```bash
git clone https://github.com/Justice-Through-Code/AISE26_w20_d4.git
cd AISE26_w20_d4/aise26-w20d4-inclassmaterial-TYLARCAMPBELL
```

### 2. Set Up Environment

This session focuses on design and calculation, but we use Python for power analysis simulations.

**For Mac/Linux:**

```bash
# Create and activate virtual environment
python -m venv venv
source venv/bin/activate

# Install dependencies (statsmodels, scipy, numpy, jupyter)
pip install -r requirements.txt
```

**For Windows:**

```powershell
# Create and activate virtual environment
python -m venv venv
venv\Scripts\activate

# Install dependencies (statsmodels, scipy, numpy, jupyter)
pip install -r requirements.txt
```

### 3. Launch Notebooks

```bash
cd notebooks
jupyter notebook
```

---

## 📂 Repository Structure

```
aise26-w20d4-inclassmaterial-TYLARCAMPBELL/
├── README.md                # This file
├── requirements.txt         # Dependencies (statsmodels, scipy, etc.)
├── templates/
│   └── experiment_spec.md   # (Breakout 1) Template for your One-Pager Spec
├── notebooks/
│   └── power_calculator.ipynb # (Breakout 2) Python-based power analysis
├── resources/
│   └── scenario_cards.md    # (Breakout 3) Decision scenarios for A/B vs. Bandits
└── assignment/
    └── homework_template.md # After-class "Experiment Design Doc" template
```

---

## 📅 Session Agenda

| Time     | Topic              | Activity                                                 |
|----------|--------------------|----------------------------------------------------------|
| 6:30 PM  | Experiment Anatomy | Hypothesis, Metrics, Guardrails, & Units                 |
| 7:00 PM  | Breakout 1         | ✍️ Write an Experiment Spec (Template provided)          |
| 7:25 PM  | Statistical Power  | Understanding α, 1−β, and MDE                            |
| 8:05 PM  | Breakout 2         | 🧮 Power & Sample Size Scenarios (Calculator/Notebook)  |
| 8:30 PM  | A/B vs. Bandits    | When to optimize vs. when to learn                       |
| 9:05 PM  | Share-outs         | Go/No-Go Decision Rubric                                |

---

## 🧩 Breakout Instructions

### Breakout 1: The Experiment Spec

**Goal:** Translate an idea into a testable hypothesis.

- **File:** `templates/experiment_spec.md`
- **Key Tasks:**
  - Format Hypothesis: "If [change], then [impact] because [reason]."
  - Define **Primary Metric** (Success) and **Guardrails** (Safety).
  - Define **Randomization Unit** (User? Session?).

### Breakout 2: Power & Sample Size

**Goal:** Determine how much data you need to avoid inconclusive results.

- **Tool:** [Evan Miller Calculator](https://www.evanmiller.org/ab-testing/sample-size.html) or `notebooks/power_calculator.ipynb`
- **Scenario:**
  - **Baseline Conversion:** 5%
  - **MDE:** 10% (relative) vs 5% (relative)
  - **Question:** How does the required sample size change as MDE shrinks?

### Breakout 3: Bandit or Not?

**Goal:** Choose the right deployment strategy for a specific constraint.

- **File:** `resources/scenario_cards.md`
- **Decision:** Fixed A/B Test vs. Multi-Armed Bandit
- **Trade-off:** What are you sacrificing? (Certainty vs. Speed/Revenue)

---

## 📝 After-Class Assignment

**Deliverable:** Experiment Design Doc (1–2 Pages)

- **File:** `assignment/homework_template.md`
- **Instructions:** Pick a real feature or model change (e.g., "New Ranking Model"). Complete a full design doc including your Power Plan (calculated sample size) and your "Go/No-Go" decision rule.

---

## References

- **Course Repo:** https://github.com/Justice-Through-Code/AISE26_w20_d4
- **Concepts:** Statistical Power (1−β), Significance (α), MDE, A/B Testing, Multi-Armed Bandits
