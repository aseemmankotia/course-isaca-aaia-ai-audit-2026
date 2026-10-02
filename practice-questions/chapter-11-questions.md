## Chapter 11: Bias, Fairness, Explainability Testing, and Third-Party/Model Provenance Assurance — Practice Questions

**Q1.** An auditor is testing a hiring-recommendation model. Regulatory guidance requires checking whether the selection rate for a protected group is at least 80% of the selection rate for the highest-selected group. Which metric is the auditor applying?

A) Equalized odds
B) Demographic parity difference
C) Disparate impact ratio (four-fifths rule)
D) SHAP feature attribution

<details>
<summary>Answer</summary>

**Correct: C**

The disparate impact ratio compares selection rates between groups and is the basis of the EEOC four-fifths (80%) rule used in employment auditing.

**Why the others are wrong:**
- Equalized odds compares true/false positive rates conditioned on actual outcome, not raw selection rate ratios.
- Demographic parity checks if selection rates are equal (difference or ratio near 1) but the specific '80% of the max group' legal threshold is the disparate impact ratio test.
- SHAP is an explainability technique for individual predictions, not a group fairness metric.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** A loan approval model is audited for fairness. The auditor wants to confirm that among applicants who would actually repay the loan, the true positive rate is equal across racial groups, and that the false positive rate is also equal. Which fairness criterion is being tested?

A) Demographic parity
B) Disparate impact ratio
C) Individual fairness
D) Equalized odds

<details>
<summary>Answer</summary>

**Correct: D**

Equalized odds requires that TPR and FPR be equal across groups, conditioning fairness on the actual (ground truth) outcome rather than raw approval rate.

**Why the others are wrong:**
- Demographic parity ignores ground truth outcomes and only compares overall approval rates.
- Disparate impact ratio is a specific ratio-based test of demographic parity, not conditioned on TPR/FPR.
- Individual fairness compares similar individuals to each other, not group-level error rates.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q3.** During a third-party AI vendor assessment, the vendor supplies its own internally generated fairness report showing no significant bias. What should the auditor do?

A) Accept the vendor's report as sufficient evidence and close the finding
B) Reject the engagement because vendor-provided evidence is never admissible
C) Treat the vendor report as supporting evidence but perform independent bias testing on a representative sample before concluding
D) Ask the vendor to increase the model's accuracy score instead

<details>
<summary>Answer</summary>

**Correct: C**

Auditing best practice treats vendor self-attestations as one input but requires independent verification (e.g., re-running fairness metrics on holdout/representative data) due to inherent conflict of interest.

**Why the others are wrong:**
- Accepting solely vendor evidence violates independence principles central to third-party assurance auditing.
- Vendor evidence isn't inadmissible — it's useful context, just not sufficient alone.
- Accuracy is unrelated to fairness testing and doesn't address the bias concern.

</details>

---

**Q4.** An auditor needs to understand which individual features most influenced a specific loan denial for one applicant, with theoretically consistent and locally accurate attributions. Which technique is BEST suited?

A) Global feature importance from a random forest
B) SHAP (SHapley Additive exPlanations)
C) Disparate impact ratio
D) SOC 2 Type II report review

<details>
<summary>Answer</summary>

**Correct: B**

SHAP provides per-instance (local) additive attributions grounded in Shapley values from game theory, satisfying consistency and local accuracy properties valued in audits.

**Why the others are wrong:**
- Global feature importance explains overall model behavior, not one applicant's specific decision.
- Disparate impact ratio is a group fairness metric, not an explainability technique.
- SOC 2 reports assess vendor controls, not model decision logic.

</details>

---

**Q5.** A cloud AI vendor provides a SOC 2 Type II report to a customer conducting AI vendor due diligence. What does this report specifically attest to?

A) The model's fairness metrics across protected classes
B) The design of controls at a single point in time only
C) The design and operating effectiveness of the vendor's controls over a defined period of time
D) The accuracy and explainability of the AI model's predictions

<details>
<summary>Answer</summary>

**Correct: C**

SOC 2 Type II evaluates both the design AND operating effectiveness of controls over a review period (typically 6-12 months), unlike Type I which is a point-in-time design assessment.

**Why the others are wrong:**
- SOC 2 reports address security/availability/confidentiality controls, not model fairness metrics.
- That description matches SOC 2 Type I, not Type II.
- SOC 2 does not assess model accuracy or explainability — that requires separate technical audit evidence.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q6.** An auditor is calculating the disparate impact ratio for a model's approval decisions. Group A has a 60% approval rate; Group B has a 40% approval rate. What is the disparate impact ratio, and does it pass the common regulatory threshold?

A) 0.67; fails the four-fifths (0.8) threshold
B) 1.5; passes because it is above 1.0
C) 0.4; fails because it must equal 1.0 exactly
D) 20%; passes because the difference is small

<details>
<summary>Answer</summary>

**Correct: A**

Ratio = lower rate / higher rate = 40/60 = 0.67, which is below the 0.8 (four-fifths) threshold, indicating potential disparate impact.

**Why the others are wrong:**
- The ratio must be calculated as lower/higher, not higher/lower, and ratios above 1 are not meaningful in this formula.
- 0.4 is the raw approval rate of Group B, not the ratio between groups, and a ratio of 1.0 is not a strict compliance requirement, only a target.
- 20% is the raw percentage-point difference, not the disparate impact ratio calculation.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q7.** An audit finding states: 'The vendor could not provide documentation on the source, licensing terms, or filtering methodology of data used to pretrain its foundation model.' Which audit area does this finding most directly relate to?

A) Explainability technique selection
B) Equalized odds calculation
C) SHAP value consistency
D) Model provenance and data lineage

<details>
<summary>Answer</summary>

**Correct: D**

Model provenance covers the traceability of training data sources, licensing, and lineage — critical for foundation models where original training data is often opaque.

**Why the others are wrong:**
- Explainability concerns how predictions are interpreted, not where training data originated.
- Equalized odds is a fairness metric unrelated to data sourcing documentation.
- SHAP values relate to feature attribution, not data lineage.

</details>

---

**Q8.** What is the primary conceptual difference between SHAP and LIME as explainability techniques used in AI audits?

A) SHAP computes attributions using Shapley values with theoretical guarantees of consistency; LIME builds a local linear surrogate model that approximates behavior near a single prediction
B) SHAP only works on image models while LIME only works on tabular data
C) LIME is a fairness metric while SHAP is an explainability technique
D) SHAP requires access to training data while LIME cannot be used on any black-box model

<details>
<summary>Answer</summary>

**Correct: A**

SHAP is grounded in cooperative game theory (Shapley values), offering consistency and additivity guarantees; LIME perturbs inputs and fits an interpretable local surrogate model, which is faster but lacks SHAP's theoretical guarantees.

**Why the others are wrong:**
- Both techniques are model-agnostic and can be applied to tabular, text, or image models.
- LIME is an explainability technique, not a fairness metric.
- Both are explicitly designed to work on black-box models without needing internal model structure; SHAP does not strictly require raw training data, though background data helps.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

