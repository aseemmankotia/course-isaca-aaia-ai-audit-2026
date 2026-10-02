## Chapter 7: AI Risk Identification and Enterprise Risk Assessment — Practice Questions

**Q1.** A bank deploys an AI system to make automated credit approval decisions for retail loan applicants. Under the EU AI Act risk classification framework, which tier does this use case fall into?

A) Minimal risk — subject only to voluntary codes of conduct
B) Limited risk — subject only to transparency/disclosure obligations
C) Unacceptable risk — the use case is prohibited outright
D) High-risk — subject to conformity assessment, documentation, and human oversight requirements

<details>
<summary>Answer</summary>

**Correct: D**

Creditworthiness evaluation of natural persons is explicitly listed as a high-risk use case under the EU AI Act's Annex III, triggering conformity assessment, technical documentation, risk management system, and human oversight obligations.

**Why the others are wrong:**
- Minimal risk applies to low-impact uses like spam filters or video game AI, not credit decisioning affecting access to essential services.
- Limited risk applies to systems like chatbots that only require disclosure that a user is interacting with AI — credit scoring has stricter binding obligations than disclosure alone.
- Unacceptable risk is reserved for practices like social scoring by governments or real-time biometric identification in public spaces — credit scoring is regulated, not banned.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** A generative AI customer support assistant occasionally fabricates policy details that sound plausible but are factually incorrect, leading customers to receive wrong refund information. Which control is the MOST effective primary mitigation for this specific risk?

A) Increase the model's temperature parameter to produce more varied responses
B) Add a disclaimer at the end of every conversation stating the AI may be wrong
C) Switch to a larger foundation model with more parameters
D) Implement retrieval-augmented generation (RAG) grounded in verified policy documents plus output validation before responses reach customers

<details>
<summary>Answer</summary>

**Correct: D**

Hallucination in generative AI is best mitigated by grounding responses in authoritative source data (RAG) combined with a verification/guardrail layer that checks output against source facts before delivery — this directly addresses the root cause of ungrounded generation.

**Why the others are wrong:**
- Increasing temperature increases response randomness/creativity, which would worsen hallucination risk, not reduce it.
- A disclaimer is a risk acceptance/transfer tactic, not a mitigation — it does not reduce the likelihood or severity of the underlying factual error and does not satisfy control expectations for a customer-facing high-impact use case.
- A larger model does not inherently reduce hallucination rate for domain-specific facts not present in training data; it is not a governance control and does not address the grounding gap.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q3.** During red-team testing of an internal LLM-powered document assistant, testers embed hidden instructions inside an uploaded PDF that cause the model to ignore its system prompt and exfiltrate confidential data in its response. This attack pattern is classified as which risk category in the AI risk taxonomy?

A) Data poisoning
B) Model inversion
C) Prompt injection
D) Membership inference

<details>
<summary>Answer</summary>

**Correct: C**

Prompt injection (including indirect prompt injection via untrusted content such as embedded documents) is the attack where malicious instructions embedded in input content override or manipulate the model's intended behavior — a top-listed LLM security risk (e.g., OWASP LLM Top 10).

**Why the others are wrong:**
- Data poisoning involves corrupting training data to influence model behavior at training time, not manipulating inference-time input.
- Model inversion is an attack aimed at reconstructing training data from model outputs, not injecting instructions via content.
- Membership inference determines whether a specific record was part of the training set — unrelated to instruction manipulation via document content.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q4.** An organization is standing up its AI governance program and needs a framework to structure risk management activities across the AI lifecycle. Which framework's four core functions are Govern, Map, Measure, and Manage?

A) ISO/IEC 42001
B) COBIT 2019
C) SOC 2 Trust Services Criteria
D) NIST AI Risk Management Framework (AI RMF)

<details>
<summary>Answer</summary>

**Correct: D**

NIST AI RMF 1.0 organizes AI risk management into four functions: Govern (culture and accountability), Map (context and risk identification), Measure (analysis and tracking of risks), and Manage (risk response and resource allocation).

**Why the others are wrong:**
- ISO/IEC 42001 is an AI management system standard (certifiable, PDCA-based) but does not use the Govern/Map/Measure/Manage structure.
- COBIT 2019 is an IT governance framework organized around governance/management objectives, not AI-specific risk functions.
- SOC 2 defines Trust Services Criteria (security, availability, processing integrity, confidentiality, privacy) for service organization controls, unrelated to AI RMF structure.

</details>

---

**Q5.** A company is evaluating a third-party vendor that provides an AI-powered resume screening tool. Which assessment activity is MOST critical to include in third-party AI risk due diligence, beyond standard vendor security review?

A) Confirming the vendor's uptime SLA meets 99.9%
B) Reviewing the vendor's bias testing results, training data provenance, and their disclosed model limitations/intended use
C) Verifying the vendor accepts the company's standard payment terms
D) Confirming the vendor uses a well-known cloud provider for hosting

<details>
<summary>Answer</summary>

**Correct: B**

Third-party AI risk due diligence must extend beyond generic vendor security/operational review to AI-specific concerns: documented bias/fairness testing, training data provenance, and clearly disclosed intended use and limitations — since the acquiring organization inherits accountability for downstream harms (e.g., discriminatory hiring outcomes).

**Why the others are wrong:**
- Uptime SLA is a standard operational resilience metric, not an AI-specific risk indicator relevant to bias or fairness harm.
- Payment terms are a commercial/contracting matter unrelated to risk assessment of the AI system itself.
- Cloud provider reputation speaks to infrastructure security, not to the AI model's fairness, data provenance, or fitness for the screening use case.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q6.** An AI risk is scored as inherent risk = High (likelihood: likely, impact: severe) before any controls. After implementing human-in-the-loop review, output monitoring, and quarterly bias audits, the risk owner recalculates the score. Which statement correctly describes residual risk in this context?

A) Residual risk equals inherent risk because AI risks cannot be reduced by controls, only accepted
B) Residual risk is the risk remaining after controls are applied, and should be re-scored on likelihood and/or impact reflecting control effectiveness
C) Residual risk is always zero once any control is implemented
D) Residual risk is calculated by adding the inherent risk score to the number of controls implemented

<details>
<summary>Answer</summary>

**Correct: B**

Residual risk is the risk that remains after mitigating controls are applied to the inherent (uncontrolled) risk. Effective controls typically reduce likelihood (e.g., human review catching errors) and/or impact (e.g., faster detection limiting exposure), and the risk owner should re-score accordingly rather than treating the score as static.

**Why the others are wrong:**
- This ignores the entire purpose of risk treatment; controls are specifically intended to reduce likelihood/impact, so inherent and residual scores diverge in a functioning risk program.
- Controls reduce but rarely eliminate risk entirely — treating residual risk as automatically zero ignores control failure rates, coverage gaps, and residual exposure.
- Risk scoring is not additive with a raw control count; a single strong control can reduce risk more than multiple weak ones, and scoring must reflect qualitative/quantitative likelihood-impact reassessment, not arithmetic on control counts.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q7.** When integrating AI-specific risks into the enterprise risk register, which set of fields should be added or adapted to distinguish AI risks from traditional operational risks?

A) Only the risk owner and risk ID fields, since AI risks use the same fields as all other enterprise risks
B) Model/use-case ID, AI risk taxonomy category (e.g., bias, robustness, security), lifecycle stage, and human oversight control reference
C) Only the financial loss estimate field, since AI risk is purely a financial risk category
D) A single free-text field describing the AI system, with no structured taxonomy

<details>
<summary>Answer</summary>

**Correct: B**

To roll AI risks up meaningfully into enterprise risk aggregation and reporting, the register needs structured fields tying the risk to the specific model/use case, its taxonomy category (bias, robustness, security, privacy, explainability, third-party), its lifecycle stage (development, validation, deployment, monitoring), and the human oversight/control reference — enabling consistent tiering and executive reporting across AI risks.

**Why the others are wrong:**
- Standard owner/ID fields alone don't capture AI-specific dimensions like model lineage or taxonomy category needed for regulatory reporting (e.g., EU AI Act high-risk inventories).
- AI risk spans operational, reputational, legal, and safety dimensions — reducing it to a financial loss estimate loses critical non-financial impact categories like discrimination harm or safety incidents.
- Free-text fields prevent aggregation, filtering, and trend analysis across the risk register, undermining enterprise-wide risk reporting and dashboarding.

</details>

---

**Q8.** Model Risk Management (MRM) principles originally developed for traditional statistical/financial models (e.g., under SR 11-7 guidance) are being extended to AI/ML systems. Which adaptation is MOST necessary when applying traditional MRM to modern AI/ML models?

A) No adaptation is needed; AI/ML models should be validated using exactly the same procedures as linear regression credit models
B) Removing the independent validation requirement entirely since AI models are self-validating
C) Expanding validation scope to include training data quality/bias testing, explainability assessment, and ongoing drift monitoring, given AI/ML models' opacity and dynamic behavior
D) Applying MRM only to generative AI models, since traditional ML models do not carry model risk

<details>
<summary>Answer</summary>

**Correct: C**

Traditional MRM (conceptual soundness review, ongoing monitoring, outcomes analysis) must be extended for AI/ML to address unique characteristics: data quality and bias in training sets, model opacity requiring explainability techniques, and higher rates of performance drift requiring continuous monitoring — because these models are harder to interpret and can degrade or behave unpredictably in production.

**Why the others are wrong:**
- AI/ML models (especially deep learning and LLMs) exhibit opacity, non-linearity, and drift not present in traditional statistical models, requiring expanded validation techniques beyond standard regression diagnostics.
- Independent validation remains a core MRM tenet; AI models still require independent challenge and testing — removing it would violate governance principles, not adapt them.
- All ML models, including traditional supervised learning models used in credit scoring or fraud detection, carry model risk and are within MRM scope, not just generative AI.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

