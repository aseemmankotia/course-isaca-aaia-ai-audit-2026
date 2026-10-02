## Chapter 3: MLOps and LLMOps Pipelines: CI/CD, Versioning, and Reproducibility — Practice Questions

**Q1.** A financial services company deployed an updated fraud-detection model to production. Within 24 hours, the false-positive rate spiked 15%. Which control should have been in place to allow immediate reversal without rebuilding or retraining?

A) An automated nightly retraining pipeline
B) Manual code review of the training script prior to merge
C) An A/B testing framework with no rollback capability
D) A model registry with versioned artifacts and one-click rollback to the previous approved version

<details>
<summary>Answer</summary>

**Correct: D**

A model registry that tracks approved versions enables instant reversion to a known-good state without waiting for a new training cycle.

**Why the others are wrong:**
- Retraining takes hours/days and does not solve an immediate production incident
- Code review prevents some defects pre-merge but provides no runtime reversal capability
- A/B testing without rollback still leaves the bad variant partially serving traffic with no safe exit

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** An organization's data scientists have direct write access to the production model registry and can promote their own models without any second-party review. Which control gap does this represent?

A) Missing infrastructure-as-code templates
B) Missing champion/challenger testing
C) Missing prompt versioning
D) Missing segregation of duties between build and deploy roles, allowing self-approval

<details>
<summary>Answer</summary>

**Correct: D**

Segregation of duties requires that the person/role building a model is not also the sole approver promoting it to production.

**Why the others are wrong:**
- IaC concerns environment reproducibility, not who can approve promotion
- Champion/challenger is a deployment testing strategy, unrelated to approval rights
- Prompt versioning applies to LLM artifacts, not the general promotion-authority issue described

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q3.** A company wants to test a new LLM prompt template against the current production prompt without disrupting all users. What is the BEST approach?

A) Replace the production prompt immediately for all users
B) Test the new prompt only in an isolated dev environment with no production traffic
C) Deploy the new prompt as a challenger to a small percentage of traffic while the champion prompt serves the majority, then compare metrics before full rollout
D) Store the new prompt version in git without deploying it anywhere

<details>
<summary>Answer</summary>

**Correct: C**

Champion/challenger deployment limits blast radius by exposing a controlled subset of traffic to the new prompt while comparing quality/safety metrics before full cutover.

**Why the others are wrong:**
- Immediate full replacement removes any safety net if the new prompt underperforms
- Dev-only testing cannot validate real user behavior and traffic patterns
- Version control alone does not test real-world performance

</details>

---

**Q4.** Which artifact bundle must be versioned together to ensure an LLM deployment is fully reproducible?

A) Only the model weights
B) The model weights, tokenizer, and prompt template as a single reproducible bundle
C) Only the training dataset
D) Only the inference server source code

<details>
<summary>Answer</summary>

**Correct: B**

Changing any one of weights, tokenizer, or prompt template changes model behavior, so all must be versioned and released together as one traceable unit.

**Why the others are wrong:**
- Weights alone omit the prompt logic that shapes output behavior
- Training data version matters for lineage but not for reproducing a specific served response
- Server code alone does not capture the model or prompt behavior

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q5.** Which CI/CD gate is specifically designed to detect fairness or bias regressions before a model reaches production?

A) Unit test gate
B) Integration test gate
C) Bias/fairness test gate comparing protected-class metrics against defined thresholds
D) Load/performance test gate

<details>
<summary>Answer</summary>

**Correct: C**

Bias/fairness gates explicitly evaluate outcome disparities across protected groups against pass/fail thresholds before promotion.

**Why the others are wrong:**
- Unit tests validate code correctness, not fairness outcomes
- Integration tests validate pipeline/data flow, not disparity metrics
- Load testing validates performance under traffic, not fairness

</details>

---

**Q6.** In the standard MLOps pipeline stages (build, test, release, deploy), at which stage should automated bias and fairness tests execute?

A) Test stage, gating promotion to release
B) Build stage only, before any other testing occurs
C) Deploy stage, after the model is already live
D) They should only be run manually after a production incident

<details>
<summary>Answer</summary>

**Correct: A**

Fairness gates belong in the Test stage so a failing model is blocked from advancing to Release/Deploy.

**Why the others are wrong:**
- Build stage is too early — the model artifact to test may not yet exist in final form
- Running checks after deploy allows a biased model to already be serving users
- Manual-only, reactive testing is not an automated control and fails audit requirements

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q7.** For reproducibility, infrastructure-as-code (IaC) definitions for the training and serving environment should be:

A) Documented in a wiki page updated periodically
B) Stored only in the cloud provider's console configuration
C) Recreated manually each time from institutional memory
D) Version-controlled alongside model code with the same commit/tag traceability

<details>
<summary>Answer</summary>

**Correct: D**

IaC must be tracked in version control and tied to the same release tag as the model so the exact environment can be reproduced on demand.

**Why the others are wrong:**
- Wikis drift out of sync and are not enforceable or auditable
- Console-only configuration is not version-controlled and is prone to configuration drift
- Manual recreation is not reproducible and is error-prone

</details>

---

**Q8.** What is the primary purpose of a model registry with an approval workflow in MLOps?

A) To provide a governed, auditable gate that tracks model lineage, versions, and approvals before promotion to production
B) To store training datasets only
C) To automatically retrain models on a fixed schedule
D) To replace the need for unit testing

<details>
<summary>Answer</summary>

**Correct: A**

The registry's core function is governance: recording lineage, version history, and required sign-offs before a model can be promoted.

**Why the others are wrong:**
- Data storage is a separate concern from model governance
- Retraining scheduling is a pipeline automation task, not the registry's purpose
- Unit testing is a distinct CI gate that the registry does not replace

</details>

---

