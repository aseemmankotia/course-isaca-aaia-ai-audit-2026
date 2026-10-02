## Chapter 4: Model Deployment Architectures and Production Controls — Practice Questions

**Q1.** An AI team wants to validate a new fraud-detection model against live production traffic without letting its predictions affect any customer-facing decision. Which deployment pattern BEST meets this requirement?

A) Blue-green deployment
B) Shadow deployment
C) Canary deployment
D) Embedded deployment

<details>
<summary>Answer</summary>

**Correct: B**

Shadow deployment mirrors real production requests to the new model in parallel, logging its outputs for comparison, but never returns those outputs to the end user or downstream system.

**Why the others are wrong:**
- Blue-green cuts traffic entirely to a new environment at switchover — the new model would be making live decisions.
- Canary routes a small percentage of real traffic decisions to the new model, so it does influence outcomes for that slice of users.
- Embedded deployment refers to running inference on-device, not to a testing methodology.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** A canary rollout of an updated recommendation model is at 10% traffic when error rates spike and latency doubles. What is the FIRST action per standard rollback procedure?

A) Increase canary traffic to 50% to gather more diagnostic data
B) Immediately route 100% of traffic back to the previous stable version
C) Open a change request and wait for CAB approval before acting
D) Disable monitoring alerts until the root cause is identified

<details>
<summary>Answer</summary>

**Correct: B**

Automated or manual rollback to the last known-good version is the immediate containment step when a canary shows degraded metrics; the small exposure of canary deployments exists specifically to make this reversal fast and low-impact.

**Why the others are wrong:**
- Increasing exposure during a detected failure increases blast radius — the opposite of correct incident response.
- Emergency rollback is typically pre-approved as part of the release plan; waiting for a full change board defeats the purpose of canary testing.
- Disabling alerts hides the problem instead of resolving it and violates monitoring integrity controls.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q3.** A manufacturer needs a defect-detection model to run inference on a factory-floor camera system with no reliable internet connectivity and sub-100ms latency requirements. Which deployment pattern should be selected?

A) Batch deployment
B) Edge deployment
C) Real-time cloud API deployment
D) Shadow deployment

<details>
<summary>Answer</summary>

**Correct: B**

Edge deployment places the model on local hardware near the data source, enabling low-latency inference without dependency on network connectivity to a central cloud endpoint.

**Why the others are wrong:**
- Batch deployment processes data in scheduled groups, unsuitable for the sub-100ms real-time requirement.
- Real-time cloud API deployment requires reliable connectivity, which this environment does not have.
- Shadow deployment is a testing methodology, not a production inference pattern for disconnected environments.

</details>

---

**Q4.** A model-serving API is being abused by a client sending bursts of requests far above its allotted quota. The API gateway is configured to smooth out bursts while still enforcing an average rate over time. Which rate-limiting approach is being used, and what HTTP status should the gateway return to the offending client?

A) Fixed window counter; HTTP 403
B) Round-robin load balancing; HTTP 500
C) Circuit breaker pattern; HTTP 401
D) Token bucket algorithm; HTTP 429

<details>
<summary>Answer</summary>

**Correct: D**

Token bucket allows short bursts up to a bucket capacity while enforcing a steady refill rate over time, and the standard response for rate-limit violations is HTTP 429 Too Many Requests.

**Why the others are wrong:**
- Fixed window counters do not smooth bursts, and 403 signals authorization failure, not rate limiting.
- Round-robin is a load distribution technique unrelated to rate limiting, and 500 indicates a server error.
- Circuit breakers protect against downstream failures, not client-side quota abuse, and 401 indicates authentication failure.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q5.** An organization is evaluating a third-party vendor to host a generative AI model that will process regulated customer data. Which control provides the STRONGEST assurance of ongoing compliance and operational transparency from the vendor?

A) A signed non-disclosure agreement with the vendor
B) A contractual right-to-audit clause with access to model change logs and incident reports
C) Reliance on the vendor's public marketing materials describing security practices
D) A one-time penetration test performed before contract signing

<details>
<summary>Answer</summary>

**Correct: B**

A right-to-audit clause combined with access to change logs and incident reports gives ongoing, verifiable visibility into vendor operations rather than a point-in-time or unverifiable assurance.

**Why the others are wrong:**
- An NDA protects confidentiality but provides no operational or compliance assurance.
- Marketing materials are not independently verifiable and are not a control.
- A one-time pre-contract pentest does not address ongoing changes to the model or vendor environment over the life of the contract.

</details>

---

**Q6.** Which statement BEST distinguishes blue-green deployment from canary deployment?

A) Blue-green gradually increases traffic to the new version; canary switches all traffic instantly
B) Blue-green maintains two full parallel environments and switches traffic entirely at cutover; canary incrementally shifts a percentage of traffic to validate the new version
C) Blue-green is used only for batch models; canary is used only for real-time models
D) Blue-green and canary are the same pattern with different names

<details>
<summary>Answer</summary>

**Correct: B**

Blue-green keeps two complete environments (old and new) and cuts traffic over all at once with instant rollback capability by switching back; canary exposes a small, growing subset of traffic to the new version to validate behavior before full rollout.

**Why the others are wrong:**
- This reverses the definitions of the two patterns.
- Neither pattern is restricted to batch or real-time model types specifically.
- The two patterns differ meaningfully in traffic-shifting strategy and rollback speed/blast radius.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q7.** A financial services firm's model governance policy requires that any production update to a credit-scoring model pass through a formal approval workflow. Which combination of steps BEST satisfies a defensible change management process for this update?

A) Submit a change request documenting model version, test/validation results including bias and performance metrics, obtain sign-off from risk/compliance and a designated approver, then deploy via canary with defined rollback criteria
B) Deploy directly to production and monitor for issues afterward
C) Have the data science team self-approve the change to save time
D) Only update the model documentation after deployment is complete

<details>
<summary>Answer</summary>

**Correct: A**

A defensible change process requires documented evidence (including fairness/bias and performance validation), independent sign-off separate from the development team, and a controlled rollout with predefined rollback triggers.

**Why the others are wrong:**
- Deploying directly without approval bypasses governance controls required for a regulated model.
- Self-approval by the same team that built the model violates segregation of duties.
- Documenting after deployment fails to provide pre-deployment assurance and violates change control sequencing.

</details>

---

**Q8.** A model-serving cluster autoscaling policy is triggered purely on CPU utilization, but the team observes that inference request queues back up and latency SLAs are violated well before CPU reaches its scaling threshold. What is the MOST likely capacity planning gap?

A) The model is too small to need GPU acceleration
B) The API gateway rate limit is set too high
C) Scaling policy is not accounting for request queue depth/latency-based metrics relevant to inference workloads
D) The vendor SLA guarantees 99.9% availability

<details>
<summary>Answer</summary>

**Correct: C**

Inference workloads often bottleneck on I/O, batching, or queue wait time rather than raw CPU; scaling policies for AI serving should incorporate queue depth, request latency, or GPU/accelerator utilization, not CPU alone.

**Why the others are wrong:**
- GPU need is a separate architectural decision unrelated to why the scaling trigger is late.
- Rate limiting controls client request volume, not the underlying scaling metric mismatch causing the queue backlog.
- SLA percentage is a vendor/contractual measure, not a capacity planning trigger mechanism.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

