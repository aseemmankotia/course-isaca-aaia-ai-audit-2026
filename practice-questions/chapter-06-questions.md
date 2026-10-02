## Chapter 6: AI Governance Structures, Roles, and Accountability — Practice Questions

**Q1.** A financial institution deploys a credit-scoring AI model. The model owner identifies data drift causing biased outputs against a protected demographic group. Under the three-lines-of-defense model applied to AI, who holds PRIMARY responsibility for identifying and remediating this control failure at the first line?

A) Internal audit, through its periodic testing program
B) The AI ethics board, during its quarterly review
C) The board of directors, upon receiving the incident report
D) The business unit/model owner that developed and operates the model

<details>
<summary>Answer</summary>

**Correct: D**

The first line of defense consists of the operational owners who build and run the model; they own day-to-day risk identification and control remediation.

**Why the others are wrong:**
- Internal audit is the third line — it provides periodic independent assurance, not operational remediation.
- The AI ethics board is a second-line oversight/challenge function, not the operational owner of daily controls.
- The board provides strategic oversight and receives reporting; it does not perform operational remediation.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** An AI incident occurs where a high-risk AI system produces a harmful output affecting customers, classified as 'high severity' per the escalation policy. To whom should the model risk owner escalate this IMMEDIATELY?

A) Directly to the external regulator
B) The IT help desk ticketing queue
C) The AI governance committee/ethics board for cross-functional risk assessment
D) Hold the issue until the next scheduled quarterly governance review

<details>
<summary>Answer</summary>

**Correct: C**

High-severity incidents require immediate escalation to the second-line oversight body (AI governance committee/ethics board) for cross-functional risk assessment before further action, such as regulatory notification, is determined.

**Why the others are wrong:**
- Regulatory notification is typically decided after internal risk assessment and legal/compliance input, not as the first escalation step.
- IT help desk is an operational support channel, not a governance escalation path for AI risk incidents.
- Waiting for a scheduled review contradicts severity-based escalation, which requires immediate action for high-severity incidents.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q3.** A company's AI governance committee wants its three-lines-of-defense structure to cover AI risk without duplicating existing enterprise risk functions. Which approach BEST aligns AI risk oversight with the enterprise risk management (ERM) framework?

A) Create a fully separate AI risk taxonomy independent of ERM
B) Assign all AI risk oversight exclusively to the IT department
C) Integrate AI risk categories into the existing enterprise risk register and reporting hierarchy
D) Defer AI risk oversight entirely to external auditors

<details>
<summary>Answer</summary>

**Correct: C**

Best practice integrates AI risk into the existing ERM taxonomy and reporting structure to ensure consistent risk appetite application and avoid siloed, duplicative oversight.

**Why the others are wrong:**
- A fully separate taxonomy creates duplication and inconsistent risk appetite application across the enterprise.
- IT ownership alone ignores business, legal, and ethical risk dimensions that AI governance must cover.
- External auditors provide independent assurance (third line) but are not responsible for ongoing risk ownership or ERM integration.

</details>

---

**Q4.** Which role is PRIMARILY accountable for ensuring data quality, lineage, and access controls used in AI model training pipelines?

A) Chief AI Officer
B) AI ethics board chair
C) Data steward
D) Internal audit lead

<details>
<summary>Answer</summary>

**Correct: C**

The data steward owns data governance responsibilities, including quality, lineage, and access controls feeding AI pipelines.

**Why the others are wrong:**
- The Chief AI Officer holds enterprise-wide strategic accountability for AI, not day-to-day data governance.
- The AI ethics board reviews ethical implications and high-risk use cases, not data quality operations.
- Internal audit provides independent assurance on governance effectiveness, not operational data stewardship.

</details>

---

**Q5.** Which body serves as the cross-functional oversight function reviewing ethical implications and approving high-risk AI use cases, typically positioned within the second line of defense?

A) The model development team
B) Internal audit
C) An external regulator
D) The AI ethics board

<details>
<summary>Answer</summary>

**Correct: D**

The AI ethics board is a second-line, cross-functional oversight body that reviews ethical risk and approves or challenges high-risk AI use cases.

**Why the others are wrong:**
- The model development team is first-line, responsible for building and operating models, not independent ethical review.
- Internal audit is third-line, providing periodic independent assurance rather than ongoing ethical use-case approval.
- External regulators set legal requirements but are not part of the internal three-lines-of-defense structure.

</details>

---

**Q6.** In a RACI matrix for AI risk ownership, the model risk owner is designated 'Accountable' while the AI ethics board is designated 'Consulted.' What does this assignment indicate about handling a high-risk model issue?

A) The ethics board makes the final decision and the owner simply executes it
B) Both parties share equal accountability with no single clear owner
C) The ethics board has no involvement in the decision
D) The model risk owner retains ultimate accountability for the outcome but must seek the ethics board's input before finalizing the decision

<details>
<summary>Answer</summary>

**Correct: D**

In RACI, 'Accountable' means ultimate ownership and sign-off authority (only one party), while 'Consulted' means providing expert input that must be sought before the decision is finalized.

**Why the others are wrong:**
- This reverses the RACI roles — 'Consulted' parties provide input, they do not hold final decision authority.
- RACI explicitly assigns only ONE 'Accountable' party per task to avoid ambiguity in ownership.
- 'Consulted' means the ethics board IS involved and must be engaged before the decision is finalized.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q7.** An organization's AI acceptable use policy was last reviewed 18 months ago and has not been updated to address newly emerged generative AI use cases. What is the MOST appropriate corrective action per policy lifecycle management best practice?

A) Leave the policy unchanged since it has no formal expiration date
B) Delete the formal policy and rely on informal team guidance instead
C) Trigger an out-of-cycle policy review and update given the material change in AI capabilities, followed by governance committee re-approval
D) Wait until the next scheduled annual review regardless of current risk exposure

<details>
<summary>Answer</summary>

**Correct: C**

Policy lifecycle management requires trigger-based reviews when material changes (such as new AI capabilities) occur, in addition to scheduled reviews, followed by formal re-approval by the governance body.

**Why the others are wrong:**
- Policies must have defined review cadences and owners; absence of a hard expiration date does not exempt them from timely updates.
- Removing formal policy in favor of informal guidance eliminates accountability and auditability, violating governance principles.
- Waiting for the next scheduled cycle ignores the material risk introduced by unaddressed generative AI use cases, which warrants an out-of-cycle review.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q8.** What is the PRIMARY distinction between the second line and third line of defense in an AI governance three-lines-of-defense model?

A) The second line designs and executes AI models, while the third line only audits data quality
B) The second line and third line perform identical functions in AI governance
C) The third line reports to the model owner while the second line reports directly to the board
D) The second line provides independent risk oversight, policy-setting, and ongoing monitoring embedded in operations, while the third line provides periodic independent assurance on the overall governance framework's effectiveness

<details>
<summary>Answer</summary>

**Correct: D**

Second line functions (e.g., model risk management, AI ethics board) provide ongoing, embedded oversight and policy-setting, whereas third line (internal audit) provides periodic, independent assurance testing on the effectiveness of the entire governance framework.

**Why the others are wrong:**
- Designing and executing models is a first-line function, not second-line; the third line does not limit itself to data quality only.
- The two lines have distinct purposes — ongoing oversight vs. periodic independent assurance — and are not identical.
- Internal audit typically reports to the Audit Committee/Board for independence, not to the model owner; this reverses correct reporting lines.

</details>

---

