# A/B Testing Case Study: E-Commerce Checkout Conversion

## Overview

This project presents an end-to-end statistical analysis of an A/B test conducted to evaluate the effectiveness of a new digital checkout feature. The objective was to determine whether the treatment variant led to a statistically significant improvement in user conversion rates compared to the control version.

---

## Experimental Framework

### Metrics Definition

To ensure a comprehensive evaluation, three categories of metrics were defined prior to analysis:

#### 1. Primary Metric: Conversion Rate

**Definition:**
The proportion of unique users who completed a purchase (`converted = 1`) out of the total users in each group.

**Objective:**
To directly measure the impact of the new feature on the core business goal—successful checkout completion.

#### 2. Secondary Metrics: User Engagement & Retention

These metrics provide supporting insights into user behavior:

* **Engagement Rate:** Measures user interaction with the new feature (if clickstream data is available).
* **Bounce Rate:** Indicates whether users leave the checkout page prematurely, signaling potential friction.

#### 3. Guardrail Metrics: Data Integrity & Performance

These ensure the experiment does not negatively affect user experience or data validity:

* **Sample Ratio Mismatch (SRM):** Verifies whether the intended traffic split (e.g., 50/50) is maintained.
* **Latency:** Ensures the new feature does not increase page load times, which can harm conversion rates.

---

## Statistical Methodology

### Hypothesis Testing

* **Null Hypothesis (H₀):**
  The new checkout feature has no effect on conversion rate
  (p_control = p_treatment)

* **Alternative Hypothesis (Hₐ):**
  The new checkout feature significantly alters conversion rate
  (p_control ≠ p_treatment)

### Confidence Level

A significance level (α) of 0.05 was used, corresponding to a 95% confidence interval.

### Test Used

Two-Proportion Z-Test to compare conversion rates between control and treatment groups.

---

## Technical Workflow

1. **Data Cleaning**

   * Removed mismatched group assignments (control users exposed to new page and vice versa)
   * Eliminated duplicate user IDs to ensure independent observations

2. **Exploratory Data Analysis (EDA)**

   * Visualized overall conversion rates
   * Analyzed time-based trends to detect anomalies or novelty effects

3. **Statistical Inference**

   * Computed Z-statistic and P-value using `statsmodels`

4. **Interval Estimation**

   * Calculated 95% confidence intervals for both groups

---

## Quantitative Results

* **Z-Statistic:** 1.3109

* **P-Value:** 0.1899

* **Control Confidence Interval:** [0.1187, 0.1221]

* **Treatment Confidence Interval:** [0.1171, 0.1205]

---

## Data-Driven Action Plan

The P-value (0.1899) exceeds the significance threshold of 0.05, indicating that the observed difference in conversion rates is not statistically significant. Additionally, the overlapping confidence intervals suggest no meaningful improvement and a potential slight decline in performance for the treatment group.

**Recommendation:**
Do not deploy the new checkout feature. Revert all traffic to the control version to avoid unnecessary engineering and maintenance costs. Conduct further qualitative analysis (e.g., user behavior insights, session recordings, feedback) to inform future iterations.

---

## Data Source

The dataset used for this analysis was obtained from Kaggle: A/B Testing Dataset.

---

## Project Resources

* Colab Notebook: https://colab.research.google.com/drive/1qMB5FTbwlwHawppkmzDgXlp2EL3vIrpB?usp=sharing

---
