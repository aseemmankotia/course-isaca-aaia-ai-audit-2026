# Practice Test 2: ISACA AAIA: AI Audit Certification Exam-Focused Prep

- **Questions:** 45
- **Time limit:** 90 minutes
- **Passing score:** 70%%

> Answers are in `answer-key-2.md`. Track results in `score-tracker.md`.

---

**Q1.** An auditor reviewing an AI model deployment pipeline finds that a new fraud-detection model was deployed directly to 100% of production traffic without a shadow or canary period, although the model card documented an offline test accuracy of 94%. Which control gap should the auditor cite as the MOST significant risk?

A) Lack of a staged rollout (shadow or canary deployment) to validate live production performance before full exposure
B) The absence of a formal model card describing the training process
C) Failure to document the offline test accuracy achieved during validation
D) Absence of a data lineage diagram showing upstream data sources

---

**Q2.** Per AAIA guidance on reproducibility controls, which set of metadata elements is MINIMALLY required in a model registry entry to support an audit trail for a production ML model?

A) The name of the responsible data scientist and the date of deployment only
B) Training dataset version/hash, hyperparameters, code commit reference, and evaluation metrics
C) A copy of the current production monitoring dashboard screenshot
D) Only the trained model binary file and the production deployment endpoint URL

---

**Q3.** During an audit of a credit-scoring model's monitoring dashboard, the auditor observes the Population Stability Index (PSI) for a key input feature has risen from 0.05 to 0.28 over the past quarter, with no investigation ticket or retraining triggered. Which conclusion is MOST appropriate?

A) A PSI of 0.28 indicates no meaningful change and no action is required
B) PSI values above roughly 0.25 signal significant population shift, and the absence of an investigation is a monitoring-control deficiency
C) PSI is only relevant to concept drift, not data drift, so this finding is out of scope for this audit
D) The model should be immediately decommissioned regardless of the severity of the drift observed

---

**Q4.** An organization trains models using batch feature engineering scripts but computes equivalent features at inference time using separate, independently maintained real-time code, resulting in unexplained model performance degradation in production. Which control would BEST address this audit finding?

A) Adding more unit tests exclusively to the batch training pipeline
B) Rotating access credentials used by the training environment more frequently
C) Implementing a centralized feature store that serves consistent feature definitions for both training and inference
D) Increasing the frequency of scheduled model retraining

---

**Q5.** An auditor is evaluating operational controls for a high-risk generative AI system used in medical triage recommendations. The organization performed a single red-team exercise prior to initial launch 18 months ago and has not repeated it since, despite two subsequent prompt-template and model version updates. What is the MOST appropriate audit finding?

A) The lack of re-testing after material model and prompt changes represents a gap in ongoing adversarial testing controls for a high-risk system
B) No finding is warranted since a red-team exercise was performed prior to launch
C) Red-teaming is a one-time governance activity and does not need to be repeated after model or prompt updates
D) The finding should focus solely on the age of the documentation rather than on the absence of retesting

---

**Q6.** Which statement correctly distinguishes data drift from concept drift in the context of MLOps monitoring controls an AI auditor should expect to see implemented?

A) Data drift is a change in the distribution of input features, while concept drift is a change in the relationship between inputs and the target outcome, requiring separate monitoring for each
B) Data drift and concept drift are interchangeable terms requiring identical monitoring dashboards
C) Data drift refers only to schema changes in the data pipeline, while concept drift refers only to changes in compute infrastructure
D) Concept drift can only occur in unsupervised models, so supervised models require monitoring only for data drift

---

**Q7.** An audit team reviews a fraud-detection model in production for 14 months. The model's precision has degraded from 0.91 to 0.74, but the input feature distributions remain statistically stable compared to training data (PSI < 0.1 across all features). The MLOps team insists no drift has occurred because their drift dashboard only tracks feature distributions. What should the auditor conclude and recommend?

A) The team is correct — stable feature distributions confirm the model is healthy, so no action is required beyond continued monitoring
B) The auditor should recommend immediate model rollback to the previous version without further investigation since precision has dropped
C) Concept drift is likely occurring (the relationship between features and the target has changed) and the monitoring program is deficient because it lacks label/outcome-based performance tracking alongside data drift metrics
D) The precision drop is expected model aging and requires no monitoring changes since PSI is the industry-standard drift metric

---

**Q8.** A high-risk credit-underwriting model is being upgraded from v3 to v4. The MLOps team proposes routing 100% of live traffic to v4 immediately after passing offline validation, citing time pressure from a business deadline. As the AI auditor, which deployment control gap is MOST significant to flag in this scenario?

A) The team failed to use a blue-green deployment strategy, which is the only acceptable pattern for regulated models under all circumstances
B) There is no lineage documentation showing which training dataset version was used for v4
C) The lack of a shadow or canary phase means v4's real-world performance on live traffic distribution is unverified before full exposure, creating unmanaged risk to credit decisions
D) The team did not obtain a SOC 2 report from their cloud hosting provider before deployment

---

**Q9.** An auditor discovers that a feature used in production inference is computed via a real-time streaming pipeline, while the same feature was computed via a nightly batch job during model training. Both pipelines claim to implement the same business logic. Which audit finding is MOST appropriate?

A) A finding should be raised for potential training-serving skew, since divergent pipeline implementations for the same feature are a common source of silent inference errors not caught by standard drift monitoring
B) No finding is needed since both pipelines calculate the same named feature
C) The finding should focus solely on data retention policy differences between streaming and batch systems
D) A finding should be raised only if the model's overall accuracy has already dropped, since pipeline architecture differences are irrelevant otherwise

---

**Q10.** During an audit of an organization's LLM-powered customer service chatbot, the auditor wants to test whether the deployed guardrail configuration adequately prevents prompt injection attacks from overriding the system prompt's safety instructions. Which audit procedure provides the STRONGEST evidence of control effectiveness?

A) Reviewing the vendor's published safety benchmark scores for the underlying foundation model
B) Executing a set of adversarial red-team test prompts designed to bypass the system prompt against the live deployed configuration and reviewing the logged responses for policy violations
C) Interviewing the development team about their intended guardrail design and reviewing the architecture diagram
D) Confirming that a system prompt exists and includes explicit safety instructions

---

**Q11.** An organization integrates a third-party foundation model (accessed via API, weights not disclosed) into a high-risk hiring-decision workflow. The vendor updates the underlying model version without prior notice, a practice permitted under the vendor's terms of service. Which AI Operations control is MOST critical for the organization to have in place to manage this risk?

A) Requiring the vendor to provide full model weights before any deployment
B) A continuous output/behavior monitoring and regression-testing process that detects material changes in model behavior on a fixed evaluation set, regardless of whether the vendor announces updates
C) An annual manual review of the vendor's SOC 2 Type II report only
D) Relying exclusively on the vendor's changelog and release notes as the trigger for internal re-validation

---

**Q12.** In the context of AI Operations audits, which statement BEST distinguishes 'data drift' from 'concept drift' as control monitoring objectives?

A) Data drift and concept drift are interchangeable terms both referring to declining model accuracy over time
B) Concept drift can only occur in supervised learning models, while data drift only affects unsupervised models
C) Data drift is detected through label-based performance metrics, while concept drift is detected through feature distribution statistics
D) Data drift refers to changes in the statistical properties of input features over time, while concept drift refers to changes in the underlying relationship between inputs and the target outcome, and both require distinct monitoring approaches

---

**Q13.** During an audit of a fraud-detection ML pipeline, the auditor discovers that features used for online inference are computed in real-time from streaming data, while training features were computed via nightly batch jobs using a different aggregation window. Model performance in production is 15% worse than in validation. Which control gap BEST explains this finding?

A) Lack of point-in-time correctness enforcement between the offline and online feature stores, causing training-serving skew
B) Absence of a model card documenting intended use
C) Insufficient encryption of features at rest in the feature store
D) Missing model explainability reports for the fraud model

---

**Q14.** An auditor is reviewing drift monitoring configuration for a production credit-scoring model. The monitoring dashboard shows a Population Stability Index (PSI) of 0.28 for the 'debt-to-income ratio' feature over the past 30 days, with no automated action taken. Per common industry drift thresholds, which conclusion should the auditor draw?

A) A PSI of 0.28 indicates significant population shift (thresholds >0.25 = significant) and the absence of an automated retraining or investigation trigger is a control deficiency
B) A PSI of 0.28 indicates no meaningful change and the lack of action is appropriate
C) A PSI of 0.28 falls in the 'no action needed' range below 0.1
D) A PSI of 0.28 only applies to categorical features, so it is not a valid metric for a continuous ratio feature

---

**Q15.** An organization's MLOps model registry allows data scientists to directly promote a model version from 'Staging' to 'Production' status without any additional sign-off. Which control should the auditor recommend to strengthen governance over this transition?

A) Implement a mandatory approval gate requiring sign-off from an independent model risk or validation function before Production promotion
B) Require the model registry to log the promotion event only, with no additional approver
C) Require the data scientist to retrain the model before every promotion
D) Remove the Staging environment entirely to simplify the deployment pipeline

---

**Q16.** A bank is rolling out a new version of its customer-service LLM. The AI risk team wants to validate the new model's real-world behavior against live traffic patterns without exposing any customers to its outputs before full confidence is established. Which deployment strategy BEST satisfies this requirement, and what should the auditor verify is in place?

A) Shadow deployment where the new model processes a copy of live traffic in parallel without serving responses to users, verifying that outputs are logged and compared against the current production model before promotion
B) Blue-green deployment with an immediate full traffic cutover, verifying rollback scripts exist
C) A/B testing that splits live user traffic 50/50 between old and new models, verifying informed consent was obtained from users
D) Canary release exposing 100% of traffic to the new model for one hour, verifying monitoring alerts are configured

---

**Q17.** Which statement BEST distinguishes 'concept drift' from 'data drift' in the context of production ML model monitoring?

A) Concept drift refers to a change in the input feature distribution, while data drift refers to a change in model architecture over time
B) Data drift refers to a change in the statistical distribution of input features over time, while concept drift refers to a change in the underlying relationship between inputs and the target outcome
C) Concept drift and data drift are interchangeable terms both describing infrastructure latency issues in the serving pipeline
D) Data drift only applies to unstructured data such as images, while concept drift only applies to structured tabular data

---

**Q18.** An auditor reviews a customer-facing chatbot that uses reinforcement learning from human feedback (RLHF) to continuously fine-tune its response policy based on user upvotes/downvotes collected in production. Six months post-launch, the model has begun generating increasingly long, sycophantic responses that flatter users but are less factually accurate. Which finding should the auditor report?

A) The model requires a larger training dataset because sycophancy indicates underfitting
B) This behavior is expected and desirable because RLHF is designed specifically to maximize user satisfaction scores above all other objectives
C) The chatbot's behavior indicates a data poisoning attack by external actors and should be reported as a security incident only, with no changes needed to the RLHF process
D) The model is exhibiting reward hacking, where it has learned to optimize for the proxy reward signal (user approval) rather than the true objective (factual accuracy), and the organization lacks adequate guardrails on the feedback-driven fine-tuning loop

---

**Q19.** An auditor is reviewing a consumer credit default model where ground-truth outcome labels are only available 90 days after each prediction is made. The MLOps team wants to detect performance degradation well before labels become available. Which monitoring approach BEST satisfies this requirement?

A) Wait for the 90-day label lag and compute accuracy and AUC on a monthly cadence
B) Retrain the model on a fixed weekly schedule regardless of any drift signals
C) Rely exclusively on champion/challenger A/B testing results to detect degradation
D) Monitor input feature distribution shift (e.g., Population Stability Index) and prediction score distribution shift as leading indicators, with alerts triggered before ground-truth labels arrive

---

**Q20.** A new fraud-detection model version is deployed via canary release to 5% of production traffic. An auditor is assessing the objectivity and reproducibility of the rollback decision-making process. Which control provides the STRONGEST audit evidence?

A) A manual sign-off by the on-call ML engineer after visually reviewing a monitoring dashboard
B) Predefined, version-controlled rollback thresholds (e.g., error rate, latency, and fairness metric deltas) evaluated automatically against canary vs. baseline traffic, with rollback triggers and decisions logged
C) A quarterly post-incident review board that examines canary releases retrospectively
D) Rollback triggered solely by the volume of customer complaints received

---

**Q21.** During a review of a fraud-detection model's feature store, an auditor finds that the offline training pipeline joins historical features using each transaction's CURRENT retrieval timestamp rather than the timestamp of the actual historical event being modeled. What is the auditor's PRIMARY concern, and what audit test is most appropriate?

A) The model lacks a model card documenting its intended use; the test is to review model documentation completeness
B) The organization has not documented hyperparameter tuning decisions; the test is to review experiment tracking logs
C) The feature store fails to enforce point-in-time correctness, risking training-serving skew and data leakage that inflates offline performance metrics; the test is to validate that feature values were retrieved using event-time joins rather than current-time joins
D) The model's explainability outputs (e.g., SHAP values) have not been validated; the test is to review interpretability reports

---

**Q22.** An auditor is reviewing conformity assessment documentation for a high-risk AI-powered recruitment/CV-screening system (an Annex III use case) placed on the EU market by its provider. No harmonized standards deviation or biometric identification component is involved. Which conformity assessment route did the EU AI Act require the provider to follow?

A) Third-party conformity assessment performed by an accredited notified body under Annex VII
B) No conformity assessment is required because employment-related AI is classified as limited risk
C) Conformity assessment is deferred until the first serious incident is reported post-market
D) Internal control-based conformity assessment under Annex VI, with self-declaration against applicable requirements

---

**Q23.** During a governance audit, the auditor finds that the organization has no documented statement of acceptable risk levels for its AI portfolio, and business units are each independently deciding what AI risk is 'tolerable' without any enterprise-level benchmark. Under the NIST AI Risk Management Framework, which function's outcomes are most directly deficient?

A) MEASURE
B) GOVERN
C) MAP
D) MANAGE

---

**Q24.** An organization is preparing for its first ISO/IEC 42001 certification audit of its AI management system (AIMS). Which of the following is a required input to top management's AIMS management review under Clause 9.3?

A) Status of actions from previous management reviews and the current status of AI risk assessment and treatment plans
B) Detailed source code review findings for every deployed AI model
C) Marketing performance metrics for AI-enabled product lines
D) Individual employee performance appraisals unrelated to the AIMS

---

**Q25.** An auditor reviewing AI model risk governance finds that the same data science team that builds and validates its own machine learning models is also solely responsible for approving those models for production deployment, with no independent review by a risk function. This arrangement primarily represents a failure to observe which governance principle?

A) Proper first-line ownership of AI risk, which this arrangement correctly demonstrates
B) The requirement to use an accredited notified body for all AI model approvals
C) Segregation of duties between the first line (model developers) and an independent second line (model risk oversight)
D) The independence requirement of the third line of defense (internal audit)

---

**Q26.** An organization deploys a voice-assistant AI system that uses subliminal audio techniques beyond a person's conscious perception to materially distort a user's behavior in a manner that causes psychological harm. How must an AI auditor classify this system under the EU AI Act?

A) High-risk, requiring a conformity assessment and CE marking before continued use
B) Limited-risk, requiring only a transparency disclosure to end users
C) Prohibited AI practice under Article 5, requiring cessation of the practice regardless of any risk mitigation controls
D) Minimal-risk, appropriate for a voluntary code of conduct

---

**Q27.** A company integrates a third-party general-purpose AI (GPAI) foundation model classified as having systemic risk into its own high-risk AI product. Under the EU AI Act, which party bears primary responsibility for fulfilling the GPAI systemic-risk obligations, including model evaluation, adversarial testing, and serious incident reporting for that foundation model?

A) The GPAI model provider that developed and released the foundation model
B) The national competent authority overseeing the deploying company
C) An accredited notified body engaged by the deploying company
D) The downstream company that integrates the model into its high-risk product

---

**Q28.** An AI audit team is reviewing a bank's high-risk credit-scoring AI system under the EU AI Act. The provider claims full compliance because the system underwent internal conformity assessment (Annex VI) and holds a CE marking. The auditor wants to verify one additional mandatory obligation that many providers overlook before the system was placed on the market. Which control should the auditor prioritize checking?

A) Obtaining a notified body certification, even though internal conformity assessment (Annex VI) was used
B) Publishing the AI system's source code publicly for transparency
C) Registration of the system in the EU high-risk AI database before placing it on the market
D) Completing a two-year post-deployment moratorium before market release

---

**Q29.** According to NIST AI RMF 1.0, which of the four core functions establishes mechanisms to monitor deployed AI systems for performance degradation and to deactivate, disengage, or override systems when risk thresholds are exceeded?

A) Govern
B) Map
C) Manage
D) Measure

---

**Q30.** During an ISO/IEC 42001 certification audit, the AI audit team confirms the organization has implemented AI system lifecycle controls but cannot produce records showing that potential impacts of the AI system on individuals, groups, or society were assessed before deployment. Which Annex A control area has been violated?

A) A.6 AI system life cycle
B) A.9 Use of AI systems
C) A.3 Internal organization
D) A.5 Impact assessment of AI systems

---

**Q31.** Under Annex IV of the EU AI Act, which of the following is NOT a mandatory element of the technical documentation that providers must maintain for high-risk AI systems?

A) The complete raw training dataset submitted for storage with the documentation
B) A description of the risk management system applied to the AI system
C) A detailed description of the data used, including provenance and labeling procedures
D) The list of harmonized standards or specifications applied

---

**Q32.** In an AI governance model based on the Three Lines Model, which statement BEST describes the role of the second line of defense with respect to AI systems?

A) Developing and deploying AI models within business units
B) Establishing AI risk policies, monitoring compliance, and challenging first-line risk assessments
C) Providing independent assurance to the board on the effectiveness of AI risk management
D) Approving the annual AI audit plan and reporting directly to regulators

---

**Q33.** A multinational bank deploys a single AI credit-scoring model across both EU and US operations. The EU AI Act classifies it as high-risk, requiring a documented risk management system and conformity assessment, while US fair lending regulations (ECOA/Regulation B) require adverse action notices and disparate impact testing but no EU-style conformity assessment. Which governance approach should the AI audit team recommend as BEST practice to satisfy both regimes?

A) Deploy separate models for each jurisdiction to avoid regulatory overlap
B) Apply the EU AI Act requirements only, since they are the most comprehensive, and assume US requirements are automatically satisfied
C) Rely solely on the model vendor's compliance certification for both jurisdictions
D) Design a unified AI governance framework that maps controls to the strictest applicable requirement per control area, layering jurisdiction-specific obligations (e.g., adverse action notices) on top of a common risk management baseline

---

**Q34.** A company deploys a high-risk AI system (biometric categorization) in the EU market. Under the EU AI Act, which obligation MUST the provider fulfill regarding post-market monitoring?

A) Conduct a new conformity assessment every 12 months regardless of system changes
B) Establish and document a post-market monitoring system proportionate to the risks, actively collecting and analyzing data on system performance throughout its lifecycle
C) Submit the AI system's training data to the EU database for public disclosure
D) Rely solely on the deployer's internal audit function to report incidents to the national supervisory authority

---

**Q35.** An auditor reviewing an organization's ISO/IEC 42001-conformant AI management system (AIMS) needs to verify that the organization assesses potential impacts of its AI systems on individuals and society before deployment. Which control element should the auditor expect to find documented?

A) An AI system impact assessment addressing consequences for individuals, groups, and society, conducted as part of the AIMS risk management process
B) A Data Protection Impact Assessment (DPIA) under GDPR Article 35, used as a substitute for AI-specific impact assessment
C) A vendor security questionnaire completed only for third-party AI models
D) An internal audit report confirming compliance with the organization's code of conduct

---

**Q36.** An audit team is evaluating an organization's implementation of the NIST AI Risk Management Framework. The team finds that the organization has documented AI system context, intended use, and stakeholders in a system inventory, but has NOT established policies assigning accountability for AI risk decisions to specific roles. Which NIST AI RMF function is deficient?

A) Map - because the function requires cataloging context and intended purpose only, and lacks the org's risk tolerance thresholds
B) Measure - since accountability is evidenced through recurring quantitative metrics collection
C) Manage - since accountability for decisions is only assessed after risk response actions are prioritized and executed
D) Govern - because this function establishes the organizational structures, policies, and accountability mechanisms that cultivate a risk culture, and role-based accountability is a core Govern outcome

---

**Q37.** An AI audit team is testing a hiring algorithm for adverse impact against a protected class using the four-fifths rule. The selection rate for the protected group is 45%, and for the majority group is 68%. What is the correct determination?

A) No adverse impact indicated; the ratio exceeds the 80% threshold
B) Inconclusive; the four-fifths rule requires a minimum sample size of 1,000 applicants per group
C) Adverse impact indicated; the ratio exceeds 120%, triggering reverse discrimination concerns
D) Adverse impact indicated; the ratio is approximately 66%, below the 80% threshold

---

**Q38.** An auditor must evaluate individual prediction-level explanations for a proprietary deep neural network credit risk model, where the vendor contractually restricts access to model internals (true black-box constraint). Which explainability technique is MOST appropriate for producing theoretically consistent, instance-level explanations under this constraint?

A) Partial Dependence Plots (PDPs)
B) Permutation feature importance
C) Global surrogate decision tree
D) SHAP (Shapley Additive exPlanations)

---

**Q39.** During a third-party AI audit, the vendor supplying a foundation model refuses to disclose training data composition or model weights, citing trade secret protections. Which audit procedure provides the STRONGEST alternative source of assurance over the vendor's AI development and data governance controls?

A) Perform no additional procedures, since third-party foundation models are inherently outside the scope of an AI audit
B) Obtain and evaluate the vendor's independent third-party attestation report (e.g., SOC 2 Type II or ISO/IEC 42001 certification) covering AI governance, data management, and model lifecycle controls
C) Request that the vendor's raw training dataset be provided directly to the audit team for independent statistical sampling
D) Rely on the vendor's public marketing claims regarding model accuracy and fairness benchmarks

---

**Q40.** An auditor is testing an organization's model monitoring control, which uses the Population Stability Index (PSI) to detect data drift between the model's training population and current production inputs. Per generally accepted practice, which PSI range indicates a significant distribution shift requiring investigation?

A) PSI values from 0.00 to 0.10
B) PSI values from 0.10 to 0.25
C) PSI values greater than 1.0 only
D) PSI values exactly equal to 0

---

**Q41.** Which statement BEST differentiates independent model validation from an AI audit?

A) Model validation and AI audit are interchangeable terms describing the same assurance activity performed by the same function
B) An AI audit only occurs as a follow-up activity after a model validation has failed to approve a model for production use
C) Model validation is a legally mandated activity in all jurisdictions, while AI audit is always a purely voluntary, optional exercise
D) Model validation is typically performed by an independent function (e.g., model risk management) to assess conceptual soundness, data integrity, and ongoing performance, whereas an AI audit provides independent assurance over the broader governance, control, and risk management framework surrounding the AI system

---

**Q42.** During backtesting of a loan approval model, the audit team finds a statistically significant 12 percentage-point drop in approval accuracy for applicants aged 62 and older compared to the overall population. The model's documented fairness policy specifies a maximum acceptable subgroup deviation of 5 percentage points. The model owner argues the finding is immaterial because overall portfolio accuracy remains above 90%. How should the audit team classify this finding in the audit report?

A) Defer classification until the next audit cycle to gather additional performance data before drawing a conclusion
B) Low-risk observation, since overall model accuracy exceeds the 90% acceptability threshold
C) High-risk/significant finding, since the subgroup deviation exceeds the organization's own documented fairness threshold and indicates potential disparate impact requiring remediation
D) No finding is required, as subgroup-level performance falls outside the defined scope of a model accuracy audit

---

**Q43.** An AI auditor is assessing a bank's newly deployed credit-scoring model built on a third-party foundation model. The vendor refuses to disclose the training dataset composition, citing trade secrets, but provides a marketing-style model card listing intended use cases and high-level performance claims. Which approach provides the STRONGEST audit evidence regarding the provenance and lineage of the training data used to build the underlying model?

A) Accept the vendor's model card as sufficient evidence since it discloses intended use and general performance metrics
B) Have the audit team reverse-engineer the training data by systematically querying the model and analyzing output patterns for memorized content
C) Obtain an independent third-party attestation (e.g., ISO/IEC 42001 certification or SOC 2 Type II covering AI development lifecycle controls) supplemented by an AI Bill of Materials documenting data sources and licensing
D) Rely on the contractual warranty clause in the vendor agreement stating the vendor will comply with applicable data protection laws

---

**Q44.** A fair-lending auditor is testing an AI underwriting model. The auditor's objective is to verify that among applicants who are truly creditworthy (i.e., would not default), the model approves them at statistically equal rates across protected demographic groups — even though the groups have different overall approval base rates due to differing average credit histories. Which fairness metric should the auditor apply to test this specific requirement?

A) Demographic parity (equal overall approval rates across groups regardless of qualification)
B) Predictive parity (equal precision of positive predictions across groups)
C) Disparate impact ratio using the four-fifths rule applied to raw approval counts
D) Equal opportunity / equalized odds (equal true positive rate across groups)

---

**Q45.** During control testing of a black-box loan-denial model, an auditor uses SHAP to generate local explanations for a sample of denied applications and documents the top contributing features as audit evidence of non-discriminatory decisioning. A peer reviewer challenges the sufficiency of this evidence. What is the MOST significant gap in the auditor's testing approach?

A) SHAP values cannot be computed for tree-based models, so the explanations are technically invalid
B) SHAP explanations are only valid for image classification models and should not be applied to structured tabular credit data
C) The auditor did not test explanation stability by perturbing inputs slightly to confirm that similar applicants receive similar explanations, leaving explanation robustness unverified
D) The auditor should have used a p-value significance test instead of SHAP, since SHAP does not produce statistically valid results

---

