## Chapter 9: Mapping AI Governance to Auditable Controls — Practice Questions

**Q1.** A company's AI policy states 'All high-risk AI models must undergo bias testing before production deployment.' The AAIA performing a gap analysis finds the ML team runs bias tests only when a data scientist manually remembers to. What is the MOST significant control gap identified?

A) The bias testing methodology is statistically invalid
B) The policy does not define what constitutes 'high-risk'
C) Bias testing results are not stored in a central repository
D) The control lacks a defined trigger, mandatory execution point, and enforcement mechanism, relying on individual memory rather than an embedded process

<details>
<summary>Answer</summary>

**Correct: D**

Gap analysis identifies that policy intent has not been operationalized into an auditable, enforced control — discretionary reliance on memory instead of an embedded execution point is the core design flaw.

**Why the others are wrong:**
- Statistical validity of the test is not stated or being evaluated in the scenario
- Undefined 'high-risk' criteria may be a secondary gap but the scenario centers on lack of enforcement, not scope definition
- Evidence storage location is a downstream evidence-management issue, not the primary control design gap

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** An organization implements an automated CI/CD pipeline gate that blocks deployment of any model failing a fairness threshold test. Which control category does this represent, and why does the classification matter for audit purposes?

A) Preventive — because it stops the deployment from occurring before the risk is realized in production
B) Detective — because it identifies the fairness violation after model training completes
C) Corrective — because it triggers remediation of the biased model
D) Compensating — because it substitutes for a missing governance policy

<details>
<summary>Answer</summary>

**Correct: A**

A preventive control stops an event before harm occurs; blocking deployment prevents production exposure to the risk entirely.

**Why the others are wrong:**
- A detective control would flag the issue without blocking it; here the pipeline actively blocks, which is preventive
- Corrective controls remediate after an issue has already occurred/been accepted into production, which is not the case here
- Compensating controls address the absence of a primary control; this is a fully functioning primary control

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q3.** During gap analysis against ISO/IEC 42001, the AAIA identifies three gaps: (1) no documented AI incident response procedure, (2) inconsistent model card completion for 60% of production models, (3) annual AI risk assessment is two months overdue. Given limited remediation resources, which gap should be prioritized FIRST?

A) Inconsistent model card completion, because it affects the most models
B) Overdue risk assessment, because it is a compliance deadline violation
C) Missing incident response procedure, because it leaves the organization without a defined response capability if an AI-related incident occurs today
D) All three should be remediated in parallel with equal resource allocation

<details>
<summary>Answer</summary>

**Correct: C**

Remediation roadmaps prioritize by risk exposure and severity; an absent incident response capability creates immediate, unmitigated exposure regardless of the number of models affected.

**Why the others are wrong:**
- Breadth of impact (60% of models) does not equal highest severity of risk exposure
- An overdue scheduled deadline is a compliance finding but does not represent an active, unmitigated risk exposure comparable to missing incident response
- Equal parallel allocation ignores risk-based prioritization, a core gap-remediation methodology principle tested on the exam

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q4.** Which evidence type provides the STRONGEST audit support that a continuous AI model drift monitoring control is operating effectively over a 12-month period?

A) A single point-in-time screenshot of the monitoring dashboard taken during the audit
B) A signed attestation from the model owner stating the control is in place
C) The original control design document approved by the AI governance committee
D) Automatically generated monitoring logs with timestamped alerts and evidence of investigation/closure for each period

<details>
<summary>Answer</summary>

**Correct: D**

Operating effectiveness over a period requires evidence spanning that entire period, showing the control fired, was investigated, and was closed — not just design intent or a single moment.

**Why the others are wrong:**
- A point-in-time screenshot only proves the control existed at one moment, not that it operated throughout the period
- Self-reported attestation lacks independent corroboration and is weak audit evidence on its own
- A design document proves the control was designed, not that it actually operated

</details>

---

**Q5.** An AAIA is mapping a regulatory requirement stating models must be 're-validated after any material data drift' to an internal control. Which control frequency designation is MOST appropriate?

A) Annual, aligned with the enterprise risk assessment cycle
B) Continuous, requiring real-time re-validation after every inference
C) Event-driven/triggered, occurring whenever a defined drift threshold is breached
D) Quarterly, to align with existing model risk committee meetings

<details>
<summary>Answer</summary>

**Correct: C**

The regulatory language describes a condition-based requirement ('after any material drift'), which maps to an event-driven control frequency activated by a defined trigger, not a calendar schedule.

**Why the others are wrong:**
- Annual scheduling could leave material drift unaddressed for up to a year, failing the requirement's intent
- Continuous per-inference validation is operationally infeasible and exceeds what 'after material drift' requires
- Quarterly scheduling similarly ignores the condition-based nature of the requirement and could miss drift occurring between cycles

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q6.** For a high-risk AI system under EU AI Act obligations, what is the required nature of post-market monitoring per Article 72, and how should this be reflected in control documentation?

A) A continuous, systematic monitoring activity throughout the system's lifecycle, documented in a post-market monitoring plan
B) A one-time monitoring report submitted at deployment, with no ongoing requirement
C) An annual internal audit performed solely by the compliance department
D) Monitoring is only required if a serious incident has already occurred

<details>
<summary>Answer</summary>

**Correct: A**

Article 72 requires providers to establish a post-market monitoring system that is continuous and proportionate to risk across the AI system's lifecycle, documented in a post-market monitoring plan.

**Why the others are wrong:**
- A one-time report contradicts the continuous, lifecycle-long monitoring obligation
- The obligation is not limited to an annual compliance-department audit; it is an ongoing, cross-functional activity
- Monitoring must occur regardless of whether an incident has occurred; incident reporting is a separate, additional obligation

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q7.** An AI governance program defines a Key Risk Indicator (KRI): 'percentage of production models exceeding drift threshold.' The KRI threshold is set at 5%, with an escalation trigger at 8%. Current measurement shows 9%. What is the CORRECT control action per standard KRI design?

A) Escalate to the defined governance body per the documented escalation procedure, since the measured value exceeds the escalation trigger
B) No action needed since the KRI is a lagging metric only used for reporting
C) Automatically decommission all models exceeding the drift threshold without further review
D) Wait until the next quarterly review cycle to address the breach

<details>
<summary>Answer</summary>

**Correct: A**

KRIs are designed with defined thresholds and escalation procedures; breaching the escalation trigger requires timely escalation to the accountable governance body per the documented procedure.

**Why the others are wrong:**
- KRIs are actionable risk signals with escalation mechanisms, not passive reporting-only metrics
- Automatic decommissioning without governance review bypasses the defined escalation-then-decision process
- Waiting for the next scheduled cycle ignores the trigger-based escalation requirement, defeating the KRI's purpose

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q8.** How does a Key Risk Indicator (KRI) fundamentally differ from a Key Performance Indicator (KPI) in an AI governance program?

A) KRIs measure operational efficiency while KPIs measure control existence
B) KRIs are only used by internal audit while KPIs are only used by business units
C) There is no meaningful difference; the terms are used interchangeably in AI governance frameworks
D) KRIs are forward-looking signals of increasing risk exposure requiring threshold-based escalation, while KPIs measure achievement of performance or process objectives

<details>
<summary>Answer</summary>

**Correct: D**

KRIs signal emerging risk levels tied to defined thresholds and escalation procedures, whereas KPIs track whether a process or control objective is being met against a target.

**Why the others are wrong:**
- This reverses and misstates the actual definitions of each metric type
- Ownership of KRIs and KPIs is not restricted by function in this way; both may be used across audit and business units
- The terms are distinct concepts in governance frameworks and are tested as such

</details>

---

