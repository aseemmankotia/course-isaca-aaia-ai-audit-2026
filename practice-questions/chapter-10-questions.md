## Chapter 10: Scoping and Planning AI Audits: Control Testing Strategy — Practice Questions

**Q1.** An internal audit team is planning an audit of a company's AI model inventory that includes 40 models ranging from a low-risk internal FAQ chatbot to a high-risk automated loan-underwriting model. Given limited audit resources, which approach BEST reflects a risk-based audit scoping strategy?

A) Prioritize audit depth and resources on the loan-underwriting model based on inherent risk tiering, applying lighter-touch procedures to low-risk models
B) Audit all 40 models with the same depth of testing to ensure consistency
C) Audit only the most recently deployed models regardless of risk classification
D) Exclude the loan-underwriting model from scope because it is owned by the credit risk (second-line) function

<details>
<summary>Answer</summary>

**Correct: A**

Risk-based scoping allocates audit depth in proportion to inherent risk and impact, concentrating resources where potential harm is greatest.

**Why the others are wrong:**
- Equal-depth testing wastes limited resources on low-risk systems and is not a risk-based approach.
- Recency of deployment is not a valid risk driver for scoping decisions.
- Ownership by a second-line function does not exclude a high-risk system from Internal Audit's independent assurance scope.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** During fieldwork, the audit team must verify that the model risk team performed monthly drift-monitoring reviews and took corrective action when thresholds were breached over the past year. Which combination of testing techniques provides the STRONGEST audit evidence?

A) Inquiry of the model risk team lead only
B) Inspection of monitoring reports and reperformance of the drift calculation for a sample of breach instances
C) Observation of a live monitoring dashboard demo
D) Review of the policy document describing the monitoring procedure

<details>
<summary>Answer</summary>

**Correct: B**

Inspection of historical evidence combined with independent reperformance provides the highest-reliability, corroborated evidence of operating effectiveness over the period.

**Why the others are wrong:**
- Inquiry alone is the weakest form of evidence and unverifiable for a key control.
- Observation only confirms a point-in-time demonstration, not historical compliance or corrective action over the year.
- Reviewing the policy confirms control design, not that it actually operated effectively.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q3.** The AI audit lead wants to leverage work already performed by the second-line Model Risk Management (MRM) function that validated a model's fairness testing. Per IIA standards, what must the audit team do before relying on this work as audit evidence?

A) Assess the competence, objectivity, and quality of MRM's work before relying on it, and corroborate with independent sample testing
B) Automatically accept MRM's conclusions since they are domain experts
C) Disregard MRM's work entirely because Internal Audit must be fully independent
D) Ask the Chief Data Scientist to re-perform the entire MRM validation

<details>
<summary>Answer</summary>

**Correct: A**

Standards on relying on the work of others require evaluating the competence and objectivity of the source and corroborating conclusions with independent testing.

**Why the others are wrong:**
- Blind acceptance without evaluation violates due professional care.
- Fully disregarding existing assurance work is inefficient and not required if the work is properly evaluated.
- Escalating to a first-line role to redo validation is not the correct or required step before assessing reliance.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q4.** Which control testing technique is BEST suited to confirm that segregation of duties is enforced in the model deployment pipeline (no single engineer can both train and deploy a model to production without independent approval)?

A) Reperformance of the model training run
B) Inquiry of the engineering manager only
C) Analytical review of deployment frequency trends
D) Inspection of pipeline access-control configuration/logs combined with observation of enforcement against an unauthorized deployment attempt

<details>
<summary>Answer</summary>

**Correct: D**

Segregation of duties is a preventive access control; inspecting configuration/logs and observing that unauthorized access is blocked provides direct, objective evidence of operating effectiveness.

**Why the others are wrong:**
- Reperforming the training run tests model output, not the approval/segregation control.
- Inquiry alone is insufficient evidence for a preventive, high-risk control.
- Trend analysis of deployment frequency does not test whether SoD is actually enforced.

</details>

---

**Q5.** An auditor conducts a walkthrough of the AI model pipeline from data ingestion through production deployment. What is the PRIMARY purpose of this walkthrough at the planning stage of the audit?

A) To formally conclude on operating effectiveness of controls for the audit report
B) To generate the sample used for later substantive testing
C) To confirm the audit team's understanding of the process flow and identify key controls and risk points to inform the test plan
D) To replace the need for a documented risk assessment

<details>
<summary>Answer</summary>

**Correct: C**

Walkthroughs at planning are used to build process understanding and pinpoint key controls and risks, which then shape the test plan.

**Why the others are wrong:**
- A single walkthrough instance is not sufficient evidence to conclude on operating effectiveness.
- Sample selection follows from the identified controls, not from the walkthrough itself.
- Walkthroughs supplement, but do not substitute for, a formal risk assessment.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q6.** An auditor is testing whether a hiring model's training dataset was reviewed for demographic representativeness before training. The dataset contains protected-class subgroups of very different sizes. Which sampling approach is MOST appropriate to obtain evidence about subgroup-level control performance?

A) Stratified sampling that ensures adequate representation of each subgroup, including smaller minority subgroups
B) Simple random sampling across the entire dataset
C) Judgmental sampling of only the largest subgroup
D) Sampling based solely on the most recently added records

<details>
<summary>Answer</summary>

**Correct: A**

Stratified sampling ensures small subgroups are adequately represented, which is necessary to draw conclusions about subgroup-level representativeness or bias.

**Why the others are wrong:**
- Simple random sampling can underrepresent or entirely miss small subgroups given the size disparity.
- Sampling only the largest subgroup defeats the purpose of assessing minority-subgroup representativeness.
- Recency of records is unrelated to demographic representativeness testing.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q7.** Which of the following is a required element of a properly documented AI audit test plan/program for a control testing step?

A) The auditor's personal opinion of the AI vendor's reputation
B) A summary of unrelated audits performed in prior years
C) The marketing description of the AI tool taken from the vendor's website
D) The control objective being tested, the testing technique applied, the sample size/selection method, and the criteria for a passing result

<details>
<summary>Answer</summary>

**Correct: D**

A defensible test step links objective, method, sample approach, and pass/fail criteria so results are reviewable and reproducible.

**Why the others are wrong:**
- Subjective opinions are not objective, auditable documentation.
- Unrelated prior audits are not relevant to this specific test step.
- Vendor marketing material is not objective audit documentation or criteria.

</details>

---

**Q8.** When planning an AI audit, the team must select 'audit criteria' against which the AI system's controls will be evaluated. Which of the following BEST describes an appropriate source of audit criteria?

A) The auditor's personal judgment of what 'good AI' looks like, without reference to any standard
B) Only the vendor's own internal testing documentation
C) An established framework such as NIST AI RMF or ISO/IEC 42001, tailored to the organization's applicable regulatory requirements and internal policies
D) The most recent AI audit news headline

<details>
<summary>Answer</summary>

**Correct: C**

Recognized frameworks provide objective, defensible audit criteria that can be tailored to the organization's regulatory and policy context.

**Why the others are wrong:**
- Purely subjective judgment lacks the objectivity and defensibility required of audit criteria.
- Vendor self-attestation is not independent and presents a conflict of interest as sole criteria.
- News headlines are not authoritative or stable sources of audit criteria.

</details>

---

