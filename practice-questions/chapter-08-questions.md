## Chapter 8: Regulatory Landscape: EU AI Act, NIST AI RMF, ISO/IEC 42001 — Practice Questions

**Q1.** A company deploys an AI system in the EU to score job applicants and automatically reject the bottom 30% before human recruiters review resumes. Under the EU AI Act, how is this system classified?

A) High-risk — it falls under Annex III (employment/worker management) and triggers conformity assessment obligations
B) Minimal risk — hiring tools are exempt from classification
C) Limited risk — only a transparency disclosure is required
D) Unacceptable risk — the system must be banned outright

<details>
<summary>Answer</summary>

**Correct: A**

Annex III explicitly lists AI used for recruitment, screening, or filtering job applications as high-risk. High-risk systems require risk management, technical documentation, human oversight, logging, and conformity assessment before market placement.

**Why the others are wrong:**
- Minimal risk is wrong — hiring is a named Annex III use case, not exempt
- Limited risk applies to systems like chatbots that only need disclosure obligations, not automated candidate rejection
- Unacceptable risk (Article 5) covers practices like social scoring or subliminal manipulation, not standard hiring screening

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** A public transit authority wants to deploy a system that assigns citizens a 'trustworthiness score' based on their behavior across unrelated contexts, then uses that score to deny access to certain services. Which EU AI Act provision applies?

A) Article 50 transparency obligations, since users must be told a score is being generated
B) Article 5 prohibited practice — social scoring by or on behalf of public authorities is banned outright
C) Annex III high-risk classification requiring a notified body conformity assessment
D) No specific obligation — scoring systems are considered minimal risk if accuracy is documented

<details>
<summary>Answer</summary>

**Correct: B**

Article 5 explicitly prohibits AI systems used for social scoring by public authorities that leads to detrimental or unfavorable treatment in unrelated contexts. This is an unacceptable-risk practice with no compliance pathway — it cannot be placed on the market.

**Why the others are wrong:**
- Transparency obligations apply to limited-risk systems, not banned practices — no amount of disclosure makes this legal
- High-risk classification implies the system can be legally deployed via conformity assessment, which is false for prohibited practices
- Minimal risk is incorrect; this scenario matches the exact wording of a Title II Article 5 prohibition

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q3.** An organization wants an internationally recognized, third-party auditable certification proving it operates a formal management system for governing AI risk across its AI lifecycle. Which framework should it adopt?

A) NIST AI RMF, because it is government-endorsed and mandatory
B) ISO/IEC 42001, because it is a certifiable AI management system standard following Annex SL structure
C) EU AI Act Annex IV, because it defines technical documentation content
D) GDPR Article 35, because it covers data protection impact assessments

<details>
<summary>Answer</summary>

**Correct: B**

ISO/IEC 42001:2023 is the first international standard specifying requirements for an AI Management System (AIMS). Following the Annex SL high-level structure shared with ISO 9001/27001, it is auditable and certifiable by accredited third-party bodies.

**Why the others are wrong:**
- NIST AI RMF is voluntary US guidance, not a certifiable standard and not mandatory
- Annex IV is a documentation content list within the EU AI Act, not a management-system certification
- GDPR Article 35 concerns data protection impact assessments, unrelated to AI management system certification

</details>

---

**Q4.** Which NIST AI RMF core function is described as the cross-cutting, foundational function that must be established before Map, Measure, and Manage activities can be effectively implemented?

A) Measure
B) Govern
C) Map
D) Manage

<details>
<summary>Answer</summary>

**Correct: B**

Govern is the foundational, cross-cutting function in the NIST AI RMF that establishes organizational culture, policies, and accountability structures that inform and are infused throughout Map, Measure, and Manage.

**Why the others are wrong:**
- Measure focuses on analyzing and tracking risks quantitatively/qualitatively, applied after context is mapped
- Map focuses on establishing context and identifying risks within a specific use case, which depends on governance structures existing first
- Manage focuses on allocating resources to treat identified risks, occurring downstream of Govern

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q5.** A company deploys a prohibited AI practice under Article 5 of the EU AI Act in an EU member state. What is the maximum administrative fine that can be imposed?

A) Up to €7.5 million or 1% of global annual turnover, whichever is higher
B) Up to €15 million or 3% of global annual turnover, whichever is higher
C) Up to €20 million flat, regardless of turnover
D) Up to €35 million or 7% of global annual turnover, whichever is higher

<details>
<summary>Answer</summary>

**Correct: D**

Violations of Article 5 prohibited practices carry the highest tier of EU AI Act fines: up to €35 million or 7% of total worldwide annual turnover, whichever is higher.

**Why the others are wrong:**
- €7.5M/1% is the lowest tier, reserved for supplying incorrect/incomplete information to authorities
- €15M/3% applies to other violations such as failing high-risk system obligations, not prohibited practices
- €20M flat is not a defined tier under the EU AI Act penalty structure

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q6.** A compliance team must satisfy EU AI Act documentation requirements, NIST AI RMF Map/Measure activities, and ISO/IEC 42001 Annex A controls simultaneously without triplicating effort. Which approach should they use?

A) Implement each framework in a fully separate program with independent evidence and audits
B) Build a single control set mapped (crosswalked) to each framework's specific clauses, reusing one body of evidence across all three
C) Adopt only the EU AI Act since it is legally binding and ignore voluntary frameworks
D) Wait until regulators publish an official unified framework before taking action

<details>
<summary>Answer</summary>

**Correct: B**

The crosswalk approach maps a single internal control set to the specific requirements of multiple frameworks (e.g., a 'risk management process' control satisfies EU AI Act Article 9, NIST AI RMF Map/Measure, and ISO 42001 clause 6.1/Annex A), letting one evidence set support multiple compliance obligations.

**Why the others are wrong:**
- Fully separate programs multiply audit and evidence-collection costs unnecessarily when requirements overlap substantially
- Ignoring voluntary frameworks abandons risk-management maturity benefits and market differentiation (e.g., ISO certification for customer trust)
- No single official unified framework exists or is expected; organizations are expected to build their own crosswalks today

</details>

---

**Q7.** Under the EU AI Act, a high-risk AI system used in critical infrastructure (Annex III) that is NOT a safety component regulated under existing EU product legislation typically undergoes which type of conformity assessment?

A) Mandatory third-party assessment by a notified body in all cases
B) No conformity assessment is required for critical infrastructure systems
C) Only a post-market monitoring plan is required, with no pre-market assessment
D) Internal control (self-assessment) based on Annex VI, unless harmonized standards were not followed

<details>
<summary>Answer</summary>

**Correct: D**

For most standalone Annex III high-risk systems, providers may conduct conformity assessment via internal control (Annex VI) if they applied harmonized standards; only certain cases (e.g., remote biometric identification, or where harmonized standards weren't fully applied) escalate to third-party notified body assessment (Annex VII).

**Why the others are wrong:**
- Mandatory notified-body assessment for all cases overstates the requirement — most Annex III systems qualify for self-assessment
- Conformity assessment is always required before market placement for high-risk systems, not optional
- Post-market monitoring is an additional ongoing obligation but does not replace pre-market conformity assessment

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q8.** Which of the following AI systems triggers only a transparency obligation under Article 50 of the EU AI Act, rather than high-risk requirements?

A) An AI system used to evaluate creditworthiness of loan applicants
B) An AI system used for remote biometric identification of individuals in public spaces by law enforcement
C) A customer service chatbot that must disclose to users that they are interacting with an AI system
D) An AI-based medical device used to diagnose disease

<details>
<summary>Answer</summary>

**Correct: C**

Chatbots and similar systems interacting directly with natural persons fall under limited-risk transparency obligations (Article 50) — users must simply be informed they are interacting with an AI system, unless it is obvious.

**Why the others are wrong:**
- Credit scoring is an Annex III high-risk use case requiring full conformity assessment, not just disclosure
- Remote biometric identification by law enforcement is either prohibited (real-time, public spaces) or high-risk, not merely a transparency case
- AI medical devices are high-risk under Annex I/III with sector-specific conformity assessment requirements, not limited-risk

</details>

---

