# Answer Key — Practice Test 2

**Q1. Correct: A**

A staged rollout (canary or shadow deployment) is the primary control that validates a model's behavior against live production data and traffic patterns before full exposure, catching issues offline testing cannot reveal (e.g., data skew, latency, edge cases). Skipping this step is the most significant operational risk here.

---

**Q2. Correct: B**

Reproducibility and audit trail requirements demand traceability from the deployed artifact back to the exact data, code, and configuration used to produce it: dataset version/hash, hyperparameters, code commit reference, and evaluation metrics collectively allow an auditor to reconstruct and validate model lineage.

---

**Q3. Correct: B**

PSI is a widely used data-drift metric where values below ~0.1 indicate no significant shift, 0.1-0.25 indicate moderate shift warranting attention, and above ~0.25 indicates significant population shift requiring investigation. The absence of any triggered review at this threshold is a clear monitoring-control gap.

---

**Q4. Correct: C**

A centralized feature store enforces a single, versioned source of feature logic used identically for both training and serving, directly eliminating training-serving skew, which is the root cause of the degradation described.

---

**Q5. Correct: A**

For high-risk generative AI systems, adversarial/red-team testing is an ongoing control that must be repeated after material changes (model version updates, prompt template changes) since these can introduce new failure modes or vulnerabilities; a single pre-launch exercise is insufficient.

---

**Q6. Correct: A**

Data drift concerns shifts in the statistical distribution of input features over time (e.g., via PSI or KL divergence), whereas concept drift concerns a change in the underlying relationship between inputs and the target label (e.g., detected via degrading model accuracy/label-based metrics). Because they arise from different causes, robust MLOps monitoring implements distinct detection mechanisms for each.

---

**Q7. Correct: C**

Feature-level drift metrics (like PSI) only detect changes in input distributions; they cannot detect concept drift, where the underlying relationship between inputs and the target label changes (e.g., evolving fraud patterns). A deteriorating precision score despite stable inputs is a classic concept drift signature, and a mature monitoring program must include outcome/performance-based drift detection, not just data drift, to catch this.

---

**Q8. Correct: C**

For high-risk decisioning models, direct full cutover without a canary or shadow deployment phase means the model's behavior on real, live production traffic (which can differ from offline validation sets) is never observed before it makes 100% of consequential decisions. This is the deployment control gap most directly tied to unmanaged operational risk and is a core AI Operations audit focus area.

---

**Q9. Correct: A**

Training-serving skew occurs when feature computation logic differs between training and inference pipelines, even when both are 'nominally' the same feature — timing windows, null handling, aggregation logic, or streaming vs batch computation nuances often diverge subtly. This is a well-known and heavily tested AI Operations control gap because it silently degrades model performance without triggering typical distribution-based drift alerts, making a feature store or single-pipeline-of-record control the preferred remediation.

---

**Q10. Correct: B**

Substantive testing — actually executing adversarial/red-team prompts against the live system and reviewing outputs — provides direct evidence of whether guardrails function as intended in the deployed environment. This is stronger than inquiry, design review, or vendor-reported benchmarks, none of which confirm the specific deployed configuration actually resists injection attempts.

---

**Q11. Correct: B**

Since the vendor can silently update the model without notice, the organization cannot rely on vendor disclosure alone. A continuous, internally-controlled evaluation harness (a fixed 'golden set' of test cases run regularly) that detects behavioral drift or regression is the only control that functions independent of vendor cooperation, making it the most critical mitigating control for undisclosed model changes in a high-risk use case.

---

**Q12. Correct: D**

Data drift is an input-side phenomenon (e.g., feature distributions shifting due to changing customer demographics), typically detected via statistical tests like PSI or KL-divergence on features. Concept drift is a relationship-side phenomenon (the mapping from X to Y changes, e.g., fraud patterns evolve), typically requiring outcome/label-based performance monitoring since feature distributions may remain stable while accuracy declines. Auditors must verify both monitoring types exist since one type of monitoring alone leaves a gap.

---

**Q13. Correct: A**

When offline (batch) and online (streaming) feature computation pipelines use different logic or time windows, the features seen at inference time do not match those seen during training, producing training-serving skew — a well-documented root cause of production performance degradation that AAIA audits specifically test via feature store governance controls.

---

**Q14. Correct: A**

PSI is commonly interpreted as: <0.1 = no significant shift, 0.1-0.25 = moderate shift (monitor), >0.25 = significant shift requiring investigation/retraining. A PSI of 0.28 with no automated trigger is a documented control gap that AAIA auditors are expected to flag against the organization's model risk management policy.

---

**Q15. Correct: A**

Segregation of duties is a core control principle: the person developing/promoting a model should not be the sole approver of its production release. A mandatory independent sign-off gate at the Staging-to-Production transition is the standard MLOps governance control tested on AAIA.

---

**Q16. Correct: A**

Shadow deployment (dark launch) runs the new model on real production inputs in parallel to the live model but does not return its outputs to users, allowing risk-free validation of behavior at scale. The auditor should verify output logging and comparison analysis exist to support the promotion decision — this directly satisfies the 'no customer exposure' requirement.

---

**Q17. Correct: B**

Data drift (covariate shift) is a change in P(X) — the distribution of input features — without necessarily changing the input-output relationship. Concept drift is a change in P(Y|X) — the relationship between inputs and target — meaning the same inputs now map to different correct outputs. AAIA tests this distinction because remediation differs: data drift may only require monitoring, while concept drift typically requires retraining or model redesign.

---

**Q18. Correct: D**

Reward hacking (specification gaming) is a well-known failure mode of RLHF where the model optimizes the measurable proxy signal (thumbs up/down) instead of the true intended goal (helpful, accurate answers), producing sycophantic or manipulative outputs. AAIA auditors are expected to identify this as an operational control gap requiring reward model recalibration, human review sampling, and guardrails on continuous feedback loops.

---

**Q19. Correct: D**

Because ground truth is delayed by design, waiting for labeled performance metrics means degradation is caught 90 days late. Distributional monitoring of inputs (PSI/KL divergence) and output score shifts acts as a proxy/leading indicator that can flag drift immediately, which is the standard MLOps control for label-lag environments and a key audit evidence point for AI operations monitoring maturity.

---

**Q20. Correct: B**

Version-controlled, automated thresholds compared objectively between canary and baseline populations, with all trigger events logged, give auditors reproducible, tamper-evident evidence that rollback decisions are consistent and not subject to individual judgment — this is the strongest form of control evidence for AI operations release management.

---

**Q21. Correct: C**

Joining features using the current timestamp instead of the historical event timestamp means the training data can 'see' information that would not have been available at prediction time (future data leakage), producing offline metrics that will not hold in production. The correct audit test directly validates point-in-time correctness of feature joins, which is a core MLOps/data pipeline control tested in the AI Operations domain.

---

**Q22. Correct: D**

For most Annex III high-risk AI systems, including employment/recruitment tools, the EU AI Act permits providers to use the internal control procedure under Annex VI (self-assessment against harmonized standards or common specifications), reserving mandatory notified-body assessment (Annex VII) for specific categories such as remote biometric identification systems.

---

**Q23. Correct: B**

GOVERN establishes the organizational culture, policies, and structures for AI risk management, including defining and documenting organizational risk tolerance (GOVERN 1.2) so that risk decisions are consistent across the enterprise rather than made ad hoc by individual business units.

---

**Q24. Correct: A**

ISO/IEC 42001 Clause 9.3 mirrors the management review structure of other ISO management system standards, requiring inputs such as the status of actions from prior reviews, changes in internal/external issues, AIMS performance data, audit results, and the status of AI risk assessment and treatment plans.

---

**Q25. Correct: C**

In a three lines model applied to AI, the model developers constitute the first line, while an independent model risk management or validation function should serve as the second line, reviewing and challenging models before deployment; allowing developers to self-approve collapses this separation and creates a conflict of interest.

---

**Q26. Correct: C**

Article 5 of the EU AI Act bans AI systems that deploy subliminal, manipulative, or deceptive techniques materially distorting behavior and causing significant harm; this is classified as unacceptable risk, meaning the practice must stop entirely and cannot be remediated through controls, documentation, or conformity assessment.

---

**Q27. Correct: A**

Under the EU AI Act's obligations for general-purpose AI models with systemic risk (Article 55), the upstream GPAI provider is responsible for model-level evaluations, adversarial testing, cybersecurity measures, and reporting serious incidents related to the foundation model itself; the downstream integrator has separate, distinct obligations tied to its own high-risk system.

---

**Q28. Correct: C**

Article 71 of the EU AI Act requires providers of high-risk AI systems (including Annex III use cases like credit scoring) to register the system in the EU database before placing it on the market or putting it into service, regardless of which conformity route was used. This step is frequently skipped or forgotten even when technical compliance work is otherwise complete.

---

**Q29. Correct: C**

The Manage function operationalizes risk response after risks have been identified (Map) and assessed (Measure). It covers allocating resources to treat prioritized risks, implementing mechanisms to supersede, disengage, or deactivate AI systems, and monitoring for effectiveness of risk treatment over time.

---

**Q30. Correct: D**

Annex A.5 of ISO/IEC 42001 specifically addresses AI system impact assessment, requiring organizations to evaluate potential consequences for individuals, groups, and society before and during deployment. The absence of these records is a direct nonconformity against A.5, independent of whether lifecycle controls (A.6) exist.

---

**Q31. Correct: A**

Annex IV requires a description of datasets used, including provenance, scope, characteristics, and labeling/cleaning methodologies, but does not require providers to submit or store the entire raw training dataset itself as part of the technical documentation.

---

**Q32. Correct: B**

The second line (risk management and compliance functions) sets AI risk policies and standards, monitors adherence, and independently challenges the risk assessments and controls implemented by first-line model owners and developers, without performing the operational work itself.

---

**Q33. Correct: D**

Best practice in cross-border AI governance is to build a common control baseline (e.g., risk management system, documentation, monitoring) that satisfies the strictest requirement per control area, then layer jurisdiction-specific obligations, such as ECOA adverse action notices, on top. This avoids duplicative model deployments while ensuring no regulatory gap is missed.

---

**Q34. Correct: B**

Article 72 of the EU AI Act requires providers of high-risk AI systems to establish a post-market monitoring system proportionate to the nature of the AI technology and risks, documented in a post-market monitoring plan, and to actively collect, document, and analyze relevant data on system performance throughout its lifecycle to identify emerging risks or non-conformities.

---

**Q35. Correct: A**

ISO/IEC 42001 requires organizations to conduct an AI system impact assessment evaluating potential consequences for individuals, groups, and society as part of the AIMS, distinct from and broader than data-protection-focused assessments; this is a core auditable artifact under the standard's risk management and impact assessment requirements.

---

**Q36. Correct: D**

The Govern function is the cross-cutting foundation of the NIST AI RMF, establishing policies, processes, and organizational structures that assign accountability for AI risk decisions to specific roles; the absence of such role-based accountability policies indicates a Govern deficiency, even though Map activities (context, intended use, stakeholders) have already been completed.

---

**Q37. Correct: D**

Dividing the protected group's selection rate (45%) by the majority group's rate (68%) yields approximately 0.66, or 66%. Since this falls below the 80% (four-fifths) threshold established by the Uniform Guidelines on Employee Selection Procedures, adverse impact is indicated and warrants further statistical and practical significance testing.

---

**Q38. Correct: D**

SHAP is model-agnostic, works purely from input-output query access (no internal access needed), and is grounded in cooperative game theory, providing consistency and local accuracy guarantees for individual prediction explanations — properties auditors rely on when documenting explainability testing for a specific applicant's decision.

---

**Q39. Correct: B**

When direct access to proprietary training data or model internals is contractually or legally restricted, independent third-party attestations (SOC 2 Type II, ISO/IEC 42001) provide auditor-recognized evidence that an external, qualified party has tested the vendor's AI governance and control environment, which is the standard alternative assurance mechanism cited in AAIA guidance for third-party AI risk.

---

**Q40. Correct: B**

A PSI between 0.10 and 0.25 is widely recognized as indicating moderate-to-significant population shift warranting investigation, while values above 0.25 indicate major shift requiring immediate action; auditors testing a drift-monitoring control should verify the configured alert thresholds align with these accepted benchmarks.

---

**Q41. Correct: D**

Model validation is a second-line function focused on technical soundness (data quality, methodology, performance) of a specific model, typically performed continuously or at defined intervals, while an AI audit is a third-line, independent assurance activity assessing the adequacy of the entire AI governance, risk, and control ecosystem, including whether validation itself is effective — this distinction is core to AAIA's three-lines-of-defense framing.

---

**Q42. Correct: C**

The finding directly violates the organization's own documented control threshold (5 percentage points) with a deviation more than double that limit, and it correlates with a protected age-based subgroup, indicating potential disparate impact — this combination of control breach, statistical significance, and fairness/compliance risk warrants a high-risk finding regardless of aggregate portfolio performance.

---

**Q43. Correct: C**

Independent third-party attestation combined with an AI Bill of Materials (AI-BOM) provides verifiable, auditable evidence of controls over data sourcing, licensing, and lineage that was validated by an objective party — this is the standard assurance mechanism auditors rely on when direct access to proprietary training data is restricted.

---

**Q44. Correct: D**

Equal opportunity (a component of equalized odds) specifically measures whether qualified individuals — true positives — are identified at equal rates across groups, which directly matches the scenario's requirement to test fairness conditioned on actual creditworthiness rather than raw approval volume.

---

**Q45. Correct: C**

A single set of local explanations does not confirm the explanations are reliable or consistent; auditors must additionally test explanation stability across small input perturbations to confirm the model's decision logic is robust and not arbitrarily sensitive to noise — without this, the SHAP evidence only shows what happened for a snapshot, not whether the reasoning is dependable.

---

