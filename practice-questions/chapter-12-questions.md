## Chapter 12: Full AAIA Exam Simulation and Time-Management Strategy — Practice Questions

**Q1.** A production credit-scoring AI model's audit log shows a 15% drop in prediction accuracy over the past 30 days on live traffic compared to the validation baseline, but no code or data schema changes were deployed. Which action should the AI auditor recommend FIRST?

A) Immediately retrain the model with the latest production data
B) Escalate to disable the model and revert to manual underwriting decisions
C) Investigate for data or concept drift by comparing input feature distributions against the training baseline
D) Recommend increasing the model's confidence threshold to reduce false positives

<details>
<summary>Answer</summary>

**Correct: C**

Drift investigation is the standard first diagnostic step to establish root cause before any remediation is chosen.

**Why the others are wrong:**
- Retraining without knowing the cause risks reinforcing or masking the same underlying issue
- Disabling a production system is a disruptive overreaction before root cause is confirmed
- Adjusting the confidence threshold treats a symptom, not the underlying cause

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** An organization plans to integrate a third-party generative AI vendor's API into its customer service platform. The vendor refuses to disclose training data sources or provide a model card. From an AI governance perspective, what is the auditor's BEST recommendation?

A) Require the business unit to document accepted residual risk and implement compensating controls such as output monitoring and human review before approval
B) Approve the vendor since API-level integration does not require model transparency
C) Reject the vendor outright regardless of business need
D) Delegate the approval decision entirely to the vendor's own AI ethics certification

<details>
<summary>Answer</summary>

**Correct: A**

A risk-based governance approach requires documented residual risk acceptance plus compensating controls when full transparency is unavailable, rather than an all-or-nothing decision.

**Why the others are wrong:**
- Approving without any controls ignores legitimate third-party AI risk
- Outright rejection is not risk-based and ignores the business need
- Delegating oversight to the vendor's self-certification abdicates independent governance accountability

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q3.** An auditor is evaluating a hiring-screening AI model for potential discriminatory outcomes across protected demographic groups. Which testing approach provides the MOST direct evidence of disparate impact?

A) Performing disparate impact analysis comparing selection rates across demographic groups against the four-fifths rule
B) Reviewing the model's feature importance rankings
C) Conducting a code review of the training pipeline
D) Interviewing the data science team about their intent

<details>
<summary>Answer</summary>

**Correct: A**

Outcome-based statistical testing, such as disparate impact analysis using the four-fifths rule, is the standard method that provides direct evidence on actual selection outcomes.

**Why the others are wrong:**
- Feature importance is indirect and does not measure real-world outcomes
- A code review assesses process, not whether discriminatory outcomes actually occurred
- Interviews reflect stated intent, which is subjective and not verifiable evidence

</details>

---

**Q4.** Midway through the AAIA exam, a candidate is halfway through the allotted time but has completed only 35% of the 90 questions, having answered several difficult scenario questions in full detail. What is the BEST pacing adjustment?

A) Continue at the same pace to ensure maximum accuracy on every remaining question
B) Skip all remaining scenario-based questions and only answer conceptual ones
C) Guess on all remaining questions to finish early, then reread flagged items from the first half
D) Flag remaining difficult questions after a brief read, answer the straightforward ones quickly, and return to flagged items in the final review pass

<details>
<summary>Answer</summary>

**Correct: D**

Flagging difficult items and answering easier ones first preserves time for a dedicated final review pass while securing achievable points immediately.

**Why the others are wrong:**
- Maintaining the same pace on every question all but guarantees running out of time before finishing
- Skipping entire scenario-based questions discards points that may be easily earned on first read
- Guessing on remaining questions forfeits achievable points instead of applying quick, focused reasoning

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q5.** An AI governance program needs a framework the organization can use to pursue third-party certification of its AI management system. Which is the BEST fit?

A) NIST AI Risk Management Framework
B) ISO/IEC 42001 AI Management System standard
C) EU AI Act
D) COBIT

<details>
<summary>Answer</summary>

**Correct: B**

ISO/IEC 42001 is the international standard purpose-built for AI management systems and is designed to support third-party certification.

**Why the others are wrong:**
- NIST AI RMF is voluntary risk-management guidance and is not a certifiable management system standard
- The EU AI Act is binding legal regulation, not a certifiable management framework an organization implements for certification
- COBIT is a general IT governance framework and lacks AI-specific certification scope

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q6.** An auditor needs to explain individual denied-loan predictions from a gradient-boosted tabular model to a non-technical compliance reviewer, showing which features drove each specific decision. Which technique is MOST appropriate?

A) Global feature importance from the model's built-in gain metric
B) SHAP (SHapley Additive exPlanations) values for the individual prediction
C) A simplified linear regression proxy model trained on the same data
D) Partial dependence plots for the top three features

<details>
<summary>Answer</summary>

**Correct: B**

SHAP provides per-instance, additive feature attribution, making it suited to explaining a single specific decision rather than aggregate behavior.

**Why the others are wrong:**
- Global feature importance reflects overall model behavior, not the specific decision in question
- A surrogate linear model explains a different, simplified model, not the actual decision path of the original model
- Partial dependence plots show average marginal effects, not case-specific reasoning

</details>

---

**Q7.** An AI operations team is configuring automated drift-detection alerts for a fraud-detection model. Setting the population stability index (PSI) alert threshold too low (e.g., 0.05) primarily results in which outcome?

A) Missed detection of significant drift events
B) Reduced model latency in production
C) Excessive alert fatigue from frequent false-positive drift alerts on normal variation
D) Automatic model retraining without any human review

<details>
<summary>Answer</summary>

**Correct: C**

An overly sensitive (low) PSI threshold flags minor, normal population variation as drift, generating frequent false alerts and alert fatigue.

**Why the others are wrong:**
- Missed detection describes the effect of a threshold set too high, the opposite scenario
- PSI threshold configuration has no relationship to inference latency
- Threshold configuration alone does not trigger automated retraining unless a separate pipeline is configured to act on it

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q8.** On the AAIA exam's 200-800 scaled scoring system with a minimum passing score of approximately 450, what does the scaled score primarily account for that a raw percentage-correct score does not?

A) The candidate's years of professional experience
B) Statistical difficulty variance across different exam forms/versions
C) The number of questions the candidate flagged for review
D) Whether the candidate finished the exam within the time limit

<details>
<summary>Answer</summary>

**Correct: B**

Scaled scoring normalizes for difficulty differences between exam forms so that scores remain comparable regardless of which specific question set a candidate received. Verify the current passing score value on ISACA's official site before exam day.

**Why the others are wrong:**
- Professional experience is not a scoring input; it may be a prerequisite for certification but not for the scaled score itself
- Flagging is a personal review tool during the exam and does not factor into scoring
- The scaled score reflects correctness of responses, not completion speed

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

