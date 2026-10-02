# Practice Test 1: ISACA AAIA: AI Audit Certification Exam-Focused Prep

- **Questions:** 45
- **Time limit:** 90 minutes
- **Passing score:** 70%%

> Answers are in `answer-key-1.md`. Track results in `score-tracker.md`.

---

**Q1.** An AI audit team is reviewing a credit-scoring model's data pipeline and needs to trace which raw data sources, transformations, and feature engineering steps produced a specific training dataset version used in production. Which control provides the BEST evidence for this?

A) A data dictionary listing schema field names
B) The model's inference API documentation
C) An annual data governance policy statement
D) Data lineage documentation with dataset versioning and transformation logs

---

**Q2.** A model classifies fraudulent transactions where only 0.5% of transactions are fraudulent. Which evaluation metric should the audit team prioritize verifying was used to assess model performance, rather than relying on overall accuracy?

A) Overall classification accuracy
B) Precision-recall based metrics (e.g., F1 score or AUC-PR)
C) Mean squared error
D) R-squared

---

**Q3.** During an audit of an organization's MLOps pipeline, the auditor wants to confirm that a specific production model version can be exactly reproduced if an incident requires rollback. Which artifact set MUST the model registry capture to support this?

A) The production API endpoint URL
B) Model binary/artifact, training code version, hyperparameters, and training dataset version
C) Only the model's final accuracy score
D) The name of the data scientist who built the model

---

**Q4.** A bank plans to deploy a new version of its loan-approval model that shows improved accuracy in offline testing but has not been validated against real-world traffic patterns. Which deployment approach BEST allows the audit team to verify performance risk is minimized before full rollout?

A) Full replacement of the old model with immediate 100% traffic cutover
B) Deploying directly to production without further validation since offline testing passed
C) Shadow deployment or canary release comparing new model outputs against the incumbent model on live traffic before full rollout
D) Skipping deployment validation and relying solely on model documentation

---

**Q5.** An auditor observes that a deployed model's input feature distributions have shifted significantly compared to training data, but the relationship between features and the target outcome remains unchanged. Which type of drift does this represent?

A) Model decay due to code deprecation
B) Data drift (covariate shift)
C) Label drift
D) Concept drift

---

**Q6.** An organization has deployed a retrieval-augmented generation (RAG) chatbot for customer support. During an audit, the team wants to verify controls exist to detect when the LLM generates responses not grounded in the retrieved source documents. Which control should the auditor look for?

A) A quarterly review of the vendor's LLM training data
B) A firewall rule restricting API access to the LLM endpoint
C) Manual review of the chatbot's UI design for accessibility
D) Automated hallucination/groundedness monitoring that compares generated responses against retrieved context

---

**Q7.** An internal auditor is evaluating a fraud-detection model that has been in production for 18 months. The monitoring dashboard shows stable Population Stability Index (PSI) scores for all input features, yet the model's F1 score has quietly declined by 12% over the same period. Which audit finding BEST explains this control gap?

A) Monitoring only tracks input/data drift (PSI) and lacks ground-truth-based concept drift detection to catch degradation in the model-label relationship
B) The organization failed to encrypt model inputs at rest, exposing sensitive data
C) The model lacks a documented retraining schedule in the model card
D) The feature store does not enforce schema validation on incoming features

---

**Q8.** During an AI operations audit, the auditor wants to verify that a model was formally approved by risk and compliance stakeholders before being promoted from staging to production. Which artifact provides the STRONGEST evidence of this control?

A) Git commit history for the model training code
B) Dataset version control logs from the feature store
C) Application performance monitoring (APM) traces from the production environment
D) Model registry stage-transition audit log showing approver identity, timestamp, and sign-off status

---

**Q9.** An auditor reviewing an LLM-based customer service application wants evidence that prompt-injection resistance testing was completed and formally gated the release. Which control configuration provides this evidence?

A) API rate-limiting thresholds configured in the gateway
B) Token usage and cost logs exported to the billing dashboard
C) Temperature and top-p parameter documentation in the model card
D) Adversarial/red-team test suite results mapped to injection test cases, with a pass/fail threshold enforced as a release gate

---

**Q10.** A financial services firm runs a challenger credit-scoring model in shadow mode alongside the production champion model for 90 days, then begins a canary rollout to a small percentage of live traffic. An auditor finds no automated rollback trigger is configured once the challenger begins serving live decisions. Which risk is the auditor CORRECT to flag as the MOST significant control gap?

A) The shadow mode testing period of 90 days is inherently too short to be statistically valid
B) The champion model was not retrained during the shadow-mode evaluation window
C) Absence of automated rollback triggers tied to real-time performance/fairness thresholds means a degraded or biased challenger could continue serving live credit decisions before human intervention
D) The credit-scoring model does not use explainability (e.g., SHAP) tooling

---

**Q11.** In the context of AI model monitoring, which statement BEST distinguishes 'concept drift' from 'data drift'?

A) Data drift only occurs in structured/tabular models, while concept drift only occurs in large language models
B) Data drift is detected through manual review, while concept drift is always detected automatically by the model itself
C) Data drift refers to changes in the statistical distribution of input features over time, while concept drift refers to a change in the underlying relationship between inputs and the target outcome
D) Data drift and concept drift are two names for the same phenomenon and are used interchangeably in AI audit standards

---

**Q12.** An AI audit team is reviewing a training data pipeline that ingests crowd-sourced labeled data from an external annotation marketplace. The team is concerned about the risk of data poisoning, where malicious contributors intentionally submit mislabeled or adversarial samples to corrupt the model. Which control BEST mitigates this risk?

A) Automated data validation, anomaly detection, and provenance/reputation tracking applied to incoming labeled samples before they enter the training set
B) End-to-end encryption of data in transit from the annotation marketplace
C) Role-based access control (RBAC) restricting who can query the production model's API
D) A data retention policy defining how long training datasets are archived

---

**Q13.** A financial services firm trains a credit-risk ML model quarterly. The audit team wants to confirm that data quality issues are caught BEFORE they can affect the model, not just reviewed after deployment. Which control provides the STRONGEST audit evidence of this?

A) A quarterly manual review of training data by the data science team, documented in meeting minutes
B) Automated data validation gates in the pipeline that block promotion to training when schema/statistical checks fail, with logged pass/fail results
C) A data dictionary maintained in a wiki describing expected data formats
D) Post-deployment model performance dashboards that flag accuracy drops

---

**Q14.** A production fraud-detection model's precision has steadily declined over three months, while the statistical distribution of input transaction features has remained stable compared to the training baseline. Which type of drift is MOST likely occurring, and what should the audit recommend?

A) Data drift; recommend retraining on updated feature distributions
B) Label leakage; recommend removing the offending feature immediately
C) Concept drift; recommend investigating whether the relationship between fraud patterns and features has changed, and evaluate retraining with updated labels
D) Model drift is not possible if inputs are stable, so the decline must be a data pipeline failure

---

**Q15.** A bank wants to compare a new loan-scoring model's decisions against the current production model using live traffic, without the new model's outputs affecting any actual customer decisions. Which deployment pattern does this describe, and what should auditors verify is documented?

A) Blue-green deployment; verify rollback time SLAs are met
B) Canary release; verify the percentage of traffic routed to the new model is capped
C) Shadow deployment (champion-challenger); verify that challenger outputs are logged for comparison but never used for customer-facing decisions
D) A/B testing; verify statistical significance thresholds for the test

---

**Q16.** An organization's model risk policy requires that a production model be automatically flagged for mandatory retraining review when input data shift is 'significant,' per industry-standard Population Stability Index (PSI) interpretation. What PSI value is conventionally used as the threshold for 'significant shift requiring action'?

A) PSI > 0.01
B) PSI > 0.10
C) PSI > 0.25
D) PSI > 0.50

---

**Q17.** From an AI audit perspective, which of the following BEST describes an audit focus area that is UNIQUE to LLMOps (large language model operations) compared to traditional MLOps for structured-data models?

A) Version control of training code and reproducibility of experiments
B) Prompt injection and jailbreak testing as part of pre-release evaluation
C) Monitoring for data drift in production inputs
D) Access controls over the model registry

---

**Q18.** A company integrates a third-party foundation model API into its customer service chatbot. During the AI operations audit, which piece of evidence is MOST important to verify the organization's AI supply-chain risk management?

A) The vendor's marketing materials describing the model's capabilities
B) A documented due-diligence assessment covering the vendor's data sourcing practices, security certifications, SLA for model updates/deprecation, and incident notification process
C) A signed non-disclosure agreement (NDA) with the vendor
D) The number of parameters in the vendor's foundation model

---

**Q19.** An auditor reviewing a fraud-detection ML system finds that the model's precision has degraded from 92% to 71% over six months, but no alerts were triggered and the model continued serving production traffic unchanged. Which control gap does this finding MOST directly indicate?

A) No production model performance monitoring with defined degradation thresholds and alerting was implemented
B) The model was not retrained frequently enough according to a fixed quarterly schedule
C) The training dataset was not encrypted at rest during the initial development phase
D) The model card did not document the original training hyperparameters

---

**Q20.** A financial institution's ML pipeline retrains a credit-scoring model weekly using data pulled from an upstream feature store that is updated continuously by multiple teams. An auditor wants to verify that any given production prediction can be traced back to the exact model version and exact feature values used at inference time. Which control provides this capability?

A) Encrypting the feature store data in transit between services
B) End-to-end lineage and versioning that logs the model version ID together with the specific feature snapshot used for each inference request
C) Applying role-based access control to restrict who can query the feature store
D) Requiring data scientists to peer-review feature engineering code before merging to the main branch

---

**Q21.** An organization is rolling out a new version of a high-risk AI model that makes automated loan-denial decisions. To limit the blast radius if the new version behaves unexpectedly, the operations team routes only 5% of live traffic to the new model version while monitoring its outputs, with the ability to instantly revert all traffic to the prior version. Which deployment pattern is being used?

A) Shadow deployment
B) Blue-green deployment
C) A/B testing deployment
D) Canary deployment

---

**Q22.** A company deploys an AI system that automatically screens and ranks candidate CVs to shortlist applicants for interviews. Under the EU AI Act, how is this system classified?

A) Unacceptable risk – the system is prohibited outright
B) High-risk – it falls under Annex III as it evaluates individuals for employment decisions
C) Limited risk – only transparency obligations apply
D) Minimal risk – no specific obligations beyond voluntary codes

---

**Q23.** Which NIST AI RMF core function is primarily concerned with cultivating organizational culture, policies, and processes for managing AI risk, and cuts across the other three functions throughout the AI lifecycle?

A) Govern
B) Measure
C) Manage
D) Map

---

**Q24.** An organization wants an internationally recognized, third-party certifiable management system standard to demonstrate systematic governance of its AI systems to auditors and customers. Which standard should it adopt?

A) NIST AI RMF 1.0
B) ISO/IEC 23894
C) ISO/IEC 38507
D) ISO/IEC 42001

---

**Q25.** Applying the Three Lines Model to AI governance, which party holds primary accountability for the day-to-day identification and management of risk in a specific production AI model?

A) The business unit that owns and operates the AI system
B) The internal audit function
C) The enterprise risk management / model risk oversight function
D) The board of directors or AI governance committee

---

**Q26.** Under the EU AI Act, a general-purpose AI model is presumed to present 'systemic risk' and becomes subject to additional Article 51 obligations when the cumulative compute used for its training exceeds which threshold?

A) 10^25 floating point operations (FLOPs)
B) 10^20 floating point operations (FLOPs)
C) 10^23 floating point operations (FLOPs)
D) 10^15 floating point operations (FLOPs)

---

**Q27.** An AAIA auditor is testing whether an organization's AI governance policy requiring 'human accountability for high-risk model decisions' is operating effectively, not merely documented. Which audit evidence BEST supports this test?

A) A copy of the signed AI ethics policy stored in the document management system
B) Marketing materials describing the organization's commitment to responsible AI
C) A RACI matrix defining decision rights plus governance committee minutes showing overridden or escalated model decisions
D) A cloud vendor's SOC 2 report covering the underlying infrastructure

---

**Q28.** A financial institution deploys an AI system to make automated credit approval decisions for retail loan applications. Under the EU AI Act, how should this system be classified, and what is the PRIMARY obligation that follows?

A) High risk - the institution must complete a conformity assessment and register the system in the EU database before deployment
B) Limited risk - the institution must implement transparency measures informing applicants that AI is used
C) Minimal risk - no specific obligations apply beyond voluntary codes of conduct
D) Unacceptable risk - the system must be banned from use in the EU market

---

**Q29.** An auditor is evaluating an organization's AI risk management program against the NIST AI Risk Management Framework (AI RMF 1.0). The organization has documented risk tolerance, defined roles and responsibilities, and cultivated a culture of risk awareness for AI systems, but has not yet begun risk measurement activities. Which NIST AI RMF function has the organization primarily addressed?

A) Manage
B) Govern
C) Map
D) Measure

---

**Q30.** How does ISO/IEC 42001:2023 differ from ISO/IEC 23894:2023 in the context of AI governance?

A) ISO/IEC 42001 addresses only data privacy controls for AI, while ISO/IEC 23894 covers full AI lifecycle governance
B) ISO/IEC 42001 is a certifiable management system standard establishing requirements for an AI management system (AIMS), while ISO/IEC 23894 provides risk management guidance and is not certifiable
C) ISO/IEC 23894 is a certifiable standard for AI management systems, while ISO/IEC 42001 provides only non-binding risk guidance
D) Both standards are identical in scope but ISO/IEC 42001 applies only to generative AI systems

---

**Q31.** During an audit of an organization's AI governance framework, the auditor finds that the AI ethics board approves all model deployments, but no single role is accountable for ongoing monitoring of model drift and post-deployment performance. Which control gap should the auditor cite?

A) Absence of a defined model risk owner accountable for the AI system throughout its post-deployment lifecycle
B) Lack of segregation of duties between model developers and testers
C) Failure to obtain informed consent from data subjects prior to deployment
D) Insufficient encryption controls for data used in model training

---

**Q32.** An organization procures a third-party generative AI service to summarize customer support tickets. The vendor discloses only that the model is 'built on a leading foundation model' but will not provide details on training data sources or evaluation results. What is the MOST significant governance risk the auditor should highlight?

A) The organization lacks sufficient information to assess and attest to the AI system's risk profile, bias, and compliance posture, creating an accountability gap
B) The organization cannot achieve cost savings compared to building an in-house model
C) The vendor's model will underperform compared to open-source alternatives
D) The organization will be unable to fine-tune the model for domain-specific terminology

---

**Q33.** An AI governance policy states that 'all high-risk AI models must undergo independent bias testing before production release.' Which artifact provides the STRONGEST audit evidence that this control is operating effectively?

A) A signed policy document referencing the bias testing requirement
B) An email from the model owner confirming testing was likely performed
C) A statement in the model's user documentation that the model was 'tested for fairness'
D) Documented bias test results, reviewed by an independent party, with sign-off retained prior to the production release date

---

**Q34.** A financial institution deploys an AI system to conduct automated credit scoring for consumer loan applications, determining loan eligibility and interest rates entirely without human review. Under the EU AI Act, how should this AI system be classified, and what is the PRIMARY compliance obligation triggered?

A) Limited risk — the only obligation is a transparency notice informing applicants that an AI system is used
B) Minimal risk — no specific regulatory obligations beyond general product safety law
C) High risk under Annex III, requiring a conformity assessment, a risk management system, and human oversight before deployment
D) Unacceptable risk — a prohibited practice requiring immediate cessation of the system

---

**Q35.** An audit team is reviewing whether an organization's AI risk management program includes processes to continuously track AI system performance degradation and emergent unanticipated behaviors after the system is placed into production. Which NIST AI RMF core function is PRIMARILY designed to address this ongoing tracking activity?

A) Manage
B) Govern
C) Measure
D) Map

---

**Q36.** According to ISO/IEC 42001, the standard for AI management systems, which of the following describes the required accountability of top management with respect to the AI management system (AIMS)?

A) Top management must personally review and approve the source code of every AI model prior to deployment
B) Top management must delegate all AI risk decisions entirely to the data science team without any oversight mechanism
C) Top management must personally certify each individual AI system annually through an external audit body
D) Top management must demonstrate leadership and commitment by ensuring the AI policy and objectives are established, communicated, and integrated into business processes, and by assigning relevant responsibilities and authorities

---

**Q37.** An AI audit team is planning an audit of a fraud-detection system that calls a third-party foundation model API for real-time anomaly scoring. Which approach BEST defines the audit scope for the third-party component?

A) Exclude the third-party model entirely from the audit since it is outside the organization's direct operational control
B) Rely solely on the vendor's public marketing materials describing model accuracy and reliability
C) Include contractual right-to-audit clauses, request the vendor's model documentation and independent assurance reports (e.g., SOC 2, ISO/IEC 42001), and test the integration controls
D) Scope the audit only to the front-end application interface since the underlying model is proprietary

---

**Q38.** An auditor must test a credit-scoring model for disparate impact across protected classes but has no access to the model's internal architecture (black-box constraint). Which technique is MOST appropriate?

A) Calculating outcome-based fairness metrics, such as disparate impact ratio and equal opportunity difference, using labeled test data across protected groups
B) Line-by-line review of the model's source code
C) Interviewing the data science team about their intentions during model development
D) Auditing only the ETL logs of the training data pipeline

---

**Q39.** During an AI audit, the auditor requests evidence of model provenance, including training data sources, intended use, limitations, and performance across demographic subgroups. Which artifact provides the MOST direct evidence of this?

A) A network architecture diagram
B) A change management ticket log
C) A vendor sales brochure
D) A model card

---

**Q40.** An auditor is evaluating a deep neural network used for medical diagnosis recommendations. The architecture is too complex to interpret directly. Which technique would BEST provide auditable evidence of which input features drove a specific prediction?

A) Confirming that the model passed unit tests during development
B) Checking that the model's uptime SLA meets 99.9%
C) Reviewing the vendor's end-user license agreement
D) SHAP (SHapley Additive exPlanations) value analysis on sample predictions

---

**Q41.** In AI audit terminology, what is the KEY distinction between 'interpretability' and 'explainability' of an AI model?

A) Interpretability applies only to models trained on structured data, while explainability applies only to models trained on unstructured data
B) They are synonymous terms used interchangeably in all audit contexts
C) Explainability refers to legal compliance obligations, while interpretability refers strictly to technical documentation requirements
D) Interpretability refers to a model's inherent transparency in how it derives outputs (e.g., decision trees), while explainability refers to post-hoc techniques used to describe outputs of complex, less transparent models

---

**Q42.** A company deploys an AI-powered chatbot from a SaaS vendor. During reporting of audit findings, the auditor notes the vendor could not provide evidence of adversarial robustness testing or a valid AI management system certification. What is the MOST appropriate finding classification and recommendation?

A) No finding is warranted, since AI-specific assurance certifications are not referenced by any recognized framework
B) A control gap finding recommending the organization obtain independent assurance (e.g., ISO/IEC 42001 certification or a third-party audit report) and pursue contractual remediation or reassess the vendor's risk tier
C) A low-risk observation with no recommendation needed, since the vendor is well-established in the market
D) A critical finding requiring immediate contract termination regardless of business impact or risk context

---

**Q43.** A bank has integrated a third-party foundation model via API into a customer-facing chatbot. The AI audit team is reviewing the vendor's documentation to verify model provenance. Which of the following provides the STRONGEST audit evidence that the vendor's training data does not contain unauthorized copyrighted material or PII contamination?

A) An independent third-party data provenance attestation with documented data lineage and sourcing audit trail
B) Vendor's marketing materials stating the model was 'trained on ethically sourced data'
C) A SOC 2 Type II report covering the vendor's general IT and security controls
D) The vendor's publicly published model card listing high-level training data categories

---

**Q44.** An auditor is testing an AI model used for loan approval decisions and must explain to a regulator why one SPECIFIC applicant was denied credit, not just how the model behaves in general. Which explainability technique is MOST appropriate to generate this audit evidence?

A) Local explanation methods such as LIME or SHAP applied to the individual prediction
B) Global feature importance ranking computed across the entire training dataset
C) Partial dependence plots showing the average feature effect across the population
D) Overall model accuracy and F1-score metrics from the validation dataset

---

**Q45.** Between quarterly audit cycles, which of the following pieces of evidence is MOST effective for detecting concept drift in a production AI model?

A) A vendor SLA guaranteeing 99.9% API uptime for the model service
B) A static copy of the original model validation report from initial deployment
C) Continuous monitoring logs showing statistical distribution shifts in input features and output predictions over time, compared against a baseline
D) A single point-in-time accuracy rerun performed on the original training dataset

---

