## Chapter 5: AI Monitoring, Drift Detection, and Model Performance Assurance — Practice Questions

**Q1.** A retail company's fraud detection model shows input feature distributions have shifted significantly after a new customer segment was onboarded, but model accuracy and precision remain within acceptable thresholds. What is this scenario an example of?

A) Data drift
B) Concept drift
C) Model decay
D) Label leakage

<details>
<summary>Answer</summary>

**Correct: A**

Input distribution changed (P(X)) while the relationship between inputs and target (P(Y|X)) remained intact — accuracy stayed stable. This is the textbook definition of data drift.

**Why the others are wrong:**
- Concept drift requires a change in the input-output relationship, which would show up as accuracy degradation — not the case here.
- Model decay describes performance degradation over time, but performance is stable in this scenario.
- Label leakage is a training-time data integrity issue, unrelated to post-deployment distribution shifts.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** A credit scoring model's accuracy has steadily declined over six months even though PSI values for all input features remain below 0.1 (indicating stable distributions). What is the MOST likely cause?

A) Data drift
B) Concept drift
C) Training-serving skew
D) Sampling bias

<details>
<summary>Answer</summary>

**Correct: B**

Stable input distributions combined with declining accuracy indicates the relationship between features and the target variable has changed — the definition of concept drift.

**Why the others are wrong:**
- Data drift requires a distributional shift, which is explicitly ruled out by the low PSI values.
- Training-serving skew is a pipeline/feature engineering mismatch typically detected immediately at deployment, not as a gradual six-month decline.
- Sampling bias is a data collection defect, not an explanation for gradual real-time performance decline.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q3.** Which statistical method is MOST commonly used to detect distributional drift for a continuous numerical feature by comparing binned population proportions between a baseline and current dataset?

A) Chi-squared test
B) Population Stability Index (PSI)
C) F1 score comparison
D) Pearson correlation coefficient

<details>
<summary>Answer</summary>

**Correct: B**

PSI is the standard operational metric for measuring distribution shift by comparing binned population proportions across two time periods.

**Why the others are wrong:**
- Chi-squared is typically applied to categorical (discrete frequency count) feature comparisons, not binned continuous distributions.
- F1 score measures classifier predictive performance, not input distribution shift.
- Pearson correlation measures the linear relationship between two variables, not distribution drift over time.

</details>

---

**Q4.** An AI operations team uses a PSI threshold of 0.25 to trigger automated retraining review. A monitored feature's PSI value is calculated at 0.18. Per standard PSI interpretation, what is the correct action classification?

A) No significant change — no action needed
B) Significant change — immediate retraining required
C) Critical failure — take the model offline immediately
D) Moderate population change — investigate, but no automatic retrain

<details>
<summary>Answer</summary>

**Correct: D**

A PSI of 0.1–0.25 is conventionally classified as a moderate shift warranting investigation, not automatic retraining or shutdown.

**Why the others are wrong:**
- PSI below 0.1 is considered negligible; 0.18 exceeds that band, so this classification is incorrect.
- The significant-change threshold is conventionally set above 0.25, which 0.18 does not reach.
- There is no basis in standard PSI interpretation for classifying a moderate score as a critical failure requiring shutdown.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q5.** A generative AI system used for medical diagnosis support automatically routes low-confidence outputs to a clinician for review before any decision is finalized. This control is BEST described as:

A) Continuous monitoring
B) Concept drift detection
C) Human-in-the-loop override
D) Canary deployment

<details>
<summary>Answer</summary>

**Correct: C**

Routing low-confidence outputs to a human for a final decision is the defining characteristic of a human-in-the-loop override control.

**Why the others are wrong:**
- Continuous monitoring tracks metrics over time but does not itself insert a human decision point.
- This scenario has no connection to drift measurement between input and target relationships.
- Canary deployment is a phased rollout strategy for releasing new model versions, not a review/override control.

</details>

---

**Q6.** A customer-facing chatbot generates a factually incorrect and potentially harmful response (a hallucination) that a user reports. What should be the FIRST step in the AI incident management process?

A) Immediately retrain the model on corrected data
B) Shut down the entire AI system permanently
C) Log and triage the incident, assessing severity and scope of impact
D) Ignore the report since it is a single occurrence

<details>
<summary>Answer</summary>

**Correct: C**

Incident management processes require logging, triage, and a severity/impact assessment before any remediation action is decided upon.

**Why the others are wrong:**
- Retraining is a downstream remediation step that follows root-cause analysis, not the first response.
- Permanent shutdown is a disproportionate response to a single, unverified report before triage has occurred.
- Governance and audit requirements mandate that even single reports be logged and assessed, not dismissed.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q7.** What is the KEY difference between continuous monitoring and periodic model validation in an AI operations context?

A) Continuous monitoring evaluates real-time metrics and alerts on an ongoing basis, while periodic validation involves scheduled, in-depth review against a full test/holdout dataset
B) Continuous monitoring only checks infrastructure uptime, while periodic validation checks model accuracy
C) Periodic validation is only used for regulatory compliance, while continuous monitoring is optional
D) Continuous monitoring and periodic validation are interchangeable terms for the same process

<details>
<summary>Answer</summary>

**Correct: A**

Continuous monitoring is always-on, lightweight metric tracking with alerting, while periodic validation is a scheduled, deeper analysis against curated holdout data — the two are complementary, not identical.

**Why the others are wrong:**
- Continuous monitoring in AI operations includes model performance metrics, not just infrastructure uptime.
- Periodic validation is a best practice for deeper analysis, not solely a regulatory requirement.
- The two processes serve distinct purposes and are not interchangeable.

</details>

---

**Q8.** A demand forecasting model's monitoring shows accuracy consistently within acceptable thresholds, with no drift detected in the last 12 months. However, organizational AI governance policy mandates retraining every 6 months regardless of monitoring results. This is an example of:

A) Performance-triggered retraining
B) Scheduled (calendar-based) retraining
C) Drift-triggered retraining
D) Ad hoc retraining

<details>
<summary>Answer</summary>

**Correct: B**

Retraining that occurs on a fixed calendar interval regardless of detected performance or drift is scheduled (calendar-based) retraining.

**Why the others are wrong:**
- Performance-triggered retraining is initiated by threshold breaches, which are absent here since accuracy is stable.
- Drift-triggered retraining requires detected drift, which the scenario explicitly states did not occur.
- Ad hoc retraining implies an unplanned, one-off event, not a mandated recurring cadence.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

