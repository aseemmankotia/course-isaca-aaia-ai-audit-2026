# Answer Key — Practice Test 1

**Q1. Correct: D**

Data lineage tracking captures the full provenance chain from raw source data through each transformation and feature engineering step to the final dataset version, providing the traceability an audit requires.

---

**Q2. Correct: B**

With severe class imbalance, precision-recall based metrics (F1, AUC-PR) properly reflect the model's ability to detect the minority fraud class, which accuracy cannot capture.

---

**Q3. Correct: B**

Full reproducibility requires linking the model artifact to the exact code version, hyperparameters, and training data version used to produce it, so the model can be rebuilt or rolled back with confidence.

---

**Q4. Correct: C**

Shadow or canary deployment allows the new model's outputs to be compared against the incumbent model on real production traffic at limited exposure, surfacing real-world performance issues before full rollout.

---

**Q5. Correct: B**

Data drift (covariate shift) occurs when the distribution of input features changes over time while the underlying relationship between features and target remains stable.

---

**Q6. Correct: D**

Groundedness/hallucination monitoring specifically evaluates whether generated output is supported by the retrieved context, directly addressing the risk of ungrounded responses in a RAG system.

---

**Q7. Correct: A**

PSI measures shifts in feature distributions (data drift) but cannot detect concept drift — changes in the underlying relationship between features and the target label. A model can have stable inputs yet degrading accuracy if that relationship has shifted, which requires ground-truth/label-based performance monitoring (e.g., rolling F1, precision/recall) to detect. This is a heavily tested gap between data drift and concept drift controls.

---

**Q8. Correct: D**

A model registry's stage-transition log (e.g., Staging→Production) capturing who approved the transition, when, and under what conditions is direct, tamper-evident evidence of a governance gate being enforced — exactly what an auditor needs to test operating effectiveness of an approval control.

---

**Q9. Correct: D**

Documented adversarial/red-team test cases specifically targeting prompt injection, with defined pass/fail criteria enforced as a release gate, is the direct control evidence auditors need to confirm injection resistance was tested and acted upon before go-live.

---

**Q10. Correct: C**

The core risk in canary/challenger rollouts is that once live traffic is exposed, degradation must be caught and reversed quickly. Without automated rollback triggers linked to defined thresholds (accuracy, fairness/disparate impact, latency), harmful decisions can accumulate before anyone notices — this is the specific operational control gap the auditor should flag.

---

**Q11. Correct: C**

This is the standard definitional distinction tested on the AAIA exam: data (covariate) drift is a shift in P(X) — input distributions — while concept drift is a shift in P(Y|X) — the relationship between inputs and the label/outcome. Both require different monitoring approaches (statistical distribution tests vs. ground-truth performance tracking).

---

**Q12. Correct: A**

Data poisoning is a data integrity risk introduced at the ingestion stage. The strongest mitigating control is validating and screening incoming data — statistical anomaly detection, label-consistency checks, and tracking contributor provenance/reputation — before it's incorporated into training, catching malicious or low-quality contributions early.

---

**Q13. Correct: B**

Automated gates that block bad data from entering training and log results are a preventive control with objective, system-generated evidence — exactly what an auditor needs to test operating effectiveness.

---

**Q14. Correct: C**

Stable input distributions with declining performance is the classic signature of concept drift — the underlying relationship between features and target has shifted even though the features themselves look the same.

---

**Q15. Correct: C**

Shadow deployment (champion-challenger) runs the new model in parallel on live data purely for comparison logging, with zero impact on actual decisions — matching the scenario exactly.

---

**Q16. Correct: C**

Common industry convention treats PSI > 0.25 as indicating a significant population shift warranting investigation/action, while 0.10–0.25 is treated as moderate change to monitor and <0.10 as no significant change.

---

**Q17. Correct: B**

Prompt injection and jailbreak resistance testing address an attack surface specific to natural-language, instruction-following generative models, and are not a meaningful control area for traditional structured-data ML models.

---

**Q18. Correct: B**

A formal due-diligence assessment covering data provenance, security posture, update/deprecation SLAs, and incident notification directly evidences that supply-chain risk from the third-party model has been identified and managed.

---

**Q19. Correct: A**

Sustained performance degradation going undetected for six months is a direct symptom of missing continuous monitoring with threshold-based alerting on live model metrics (concept/data drift monitoring) — a core MLOps control the AAIA exam tests as part of the operate/monitor phase of the AI lifecycle.

---

**Q20. Correct: B**

Full reproducibility and traceability of predictions requires linking model version and the exact data/feature snapshot consumed at inference time — this is the specific purpose of lineage and versioning controls in MLOps pipelines, and it directly supports audit evidence and incident investigation as tested under AI Operations.

---

**Q21. Correct: D**

Canary deployment is defined by gradually routing a small percentage of live production traffic to the new version while monitoring for issues, with rapid rollback capability — exactly the pattern described, and it is a key risk-mitigation control the AAIA exam expects auditors to recognize when evaluating deployment controls for high-risk AI systems.

---

**Q22. Correct: B**

Annex III explicitly lists AI systems used for recruitment or selection of natural persons, including CV screening/ranking, as high-risk, triggering Chapter 2 obligations such as risk management, data governance, human oversight, and conformity assessment.

---

**Q23. Correct: A**

Govern is the cross-cutting function establishing organizational culture, accountability structures, and policies that inform how Map, Measure, and Manage are carried out across the AI lifecycle.

---

**Q24. Correct: D**

ISO/IEC 42001 is the AI Management System (AIMS) standard, structured similarly to ISO/IEC 27001, and is the only option among these that organizations can be certified against by an accredited third party.

---

**Q25. Correct: A**

In the Three Lines Model, first-line operational management — the business unit or model owner — owns and manages risk directly as part of day-to-day operations, including monitoring model performance and control effectiveness.

---

**Q26. Correct: A**

Article 51 and Annex XIII set the presumptive systemic-risk threshold at cumulative training compute greater than 10^25 FLOPs; providers of such GPAI models face added obligations including model evaluation, adversarial testing, incident reporting, and cybersecurity measures.

---

**Q27. Correct: C**

Testing operating effectiveness of an accountability control requires evidence the control was actually exercised. A RACI matrix establishes who is accountable, and committee minutes showing real escalations or overrides demonstrate the control functioned in practice, not just in design.

---

**Q28. Correct: A**

Credit scoring/creditworthiness assessment is explicitly listed as a high-risk use case in Annex III of the EU AI Act, triggering conformity assessment, technical documentation, and EU database registration obligations before market placement.

---

**Q29. Correct: B**

The Govern function is the cross-cutting foundation of the AI RMF, covering policies, risk tolerance, culture, and accountability structures that enable the other functions; these elements match exactly what the organization has documented.

---

**Q30. Correct: B**

ISO/IEC 42001 specifies certifiable requirements for establishing, implementing, and improving an AI management system, similar in structure to ISO/IEC 27001, whereas ISO/IEC 23894 offers non-certifiable guidance on AI-specific risk management, extending ISO 31000 principles.

---

**Q31. Correct: A**

Effective AI governance requires clearly assigned accountability that extends beyond initial approval into ongoing monitoring; the scenario describes a gap in post-deployment ownership, which is a core governance and accountability control weakness.

---

**Q32. Correct: A**

Third-party AI risk management requires sufficient transparency from vendors to evaluate risk, bias, and regulatory compliance; opaque vendor disclosures prevent the acquiring organization from fulfilling its own accountability obligations under frameworks such as NIST AI RMF and the EU AI Act's supply-chain provisions.

---

**Q33. Correct: D**

Auditors require operating effectiveness evidence, not just policy existence; dated, independently reviewed test results with sign-off prior to release directly demonstrate that the control was performed as designed and prior to the relevant event.

---

**Q34. Correct: C**

Annex III of the EU AI Act explicitly lists AI systems used to evaluate creditworthiness or establish credit scores of natural persons as high-risk, triggering obligations such as conformity assessment, risk management systems, data governance, technical documentation, and human oversight prior to market placement.

---

**Q35. Correct: C**

The Measure function of the NIST AI RMF is specifically focused on employing quantitative, qualitative, or mixed methods to analyze, benchmark, and monitor AI risks and impacts, including tracking performance metrics over time to detect drift, degradation, and unanticipated or emergent risks after deployment.

---

**Q36. Correct: D**

ISO/IEC 42001 places clause-level requirements on top management to demonstrate leadership by establishing an AI policy aligned with organizational objectives, ensuring integration of AIMS requirements into business processes, providing resources, and assigning and communicating roles and authorities — mirroring the leadership clause structure common to other ISO management system standards (e.g., ISO 27001, ISO 9001).

---

**Q37. Correct: C**

Proper scoping of third-party AI components requires leveraging contractual audit rights, obtaining vendor assurance artifacts, and testing the controls governing the integration point, consistent with AAIA guidance on third-party and model provenance assurance.

---

**Q38. Correct: A**

Outcome-based fairness metrics computed from input/output test data are the appropriate black-box technique when internal model architecture is unavailable, directly measuring disparate treatment or impact.

---

**Q39. Correct: D**

A model card is the standardized documentation artifact that records training data provenance, intended use, known limitations, and subgroup performance metrics, making it primary audit evidence for model provenance testing.

---

**Q40. Correct: D**

SHAP is a post-hoc, model-agnostic explainability technique that attributes prediction outcomes to specific input features, providing auditable evidence for black-box models where direct interpretation is infeasible.

---

**Q41. Correct: D**

Interpretability describes models that are inherently understandable by design, whereas explainability refers to supplementary methods applied to complex or opaque models to approximate an understanding of their decision logic — a key distinction tested in AI audit contexts.

---

**Q42. Correct: B**

A proportionate, risk-based finding identifies the assurance gap and recommends practical remediation steps — obtaining independent certification, escalating vendor risk tier, or securing contractual commitments — consistent with sound AI audit reporting practice.

---

**Q43. Correct: A**

An independent attestation with a documented lineage and sourcing audit trail is verifiable, traceable third-party evidence specific to data provenance — exactly the assurance the audit objective requires.

---

**Q44. Correct: A**

Local explanation methods like LIME and SHAP decompose a single prediction into per-feature contributions, providing the individual-level rationale a regulator requires for one applicant's denial.

---

**Q45. Correct: C**

Continuous monitoring logs that compare live input/output distributions against an established baseline directly capture the statistical drift a model experiences in production, which is the definition of concept/data drift evidence.

---

