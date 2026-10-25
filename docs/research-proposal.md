# BioAdvisory Clinical Microbiology Intelligence Engine
## Research and Invention Proposal — v1.0
**Date:** 25 October 2026  
**Status:** Concept and working software prototype; not clinically validated

## 1. Executive summary
BioAdvisory is proposed as an explainable clinical microbiology data-review system. Its initial research scope is intentionally narrow: detect missing, inconsistent, or insufficiently documented fields in a structured microbiology case record, explain why each flag was raised, and generate an auditable review artefact. The first working prototype implements a small deterministic ruleset on synthetic data in a browser.

The research does not establish that this approach is novel, clinically useful, or patentable. Any defensible contribution must emerge from prior-art review and evidence that a specific technical method solves a defined problem better than existing approaches.

## 2. Problem statement
Microbiology workflows can involve specimen metadata, microscopy, culture, organism identification, antimicrobial susceptibility testing (AST), quality control, and review documentation. Inconsistent status fields and incomplete linkage can impede auditability and require manual reconciliation. The initial project investigates a narrow data-quality problem rather than autonomous diagnosis or treatment recommendation.

## 3. Intended use and exclusions
**Intended research use:** evaluate transparent checks for completeness and internal consistency of synthetic or appropriately governed, de-identified microbiology records.
**Not intended for:** patient-facing use, diagnosis, organism identification, AST interpretation, antimicrobial selection, triage, time-critical alerts, or replacement of laboratory professional judgement. Any change to intended use requires fresh risk and regulatory assessment.

## 4. Proposed workflow
1. Input a structured record: case identifier, specimen type, microscopy status, culture status, organism-identification status, AST status, QC status, provenance, and reviewer notes.
2. Validate allowed values and required fields.
3. Run a versioned deterministic consistency ruleset.
4. For every flag, display triggering fields, rule identifier, explanation, and limitation.
5. Let a human reviewer reconcile the source record; do not silently change results.
6. Export a timestamped JSON review record with rule-set version and limitations.
7. In a future study, compare flags with independent expert adjudication.

## 5. Technical architecture
### Prototype implemented
- Presentation: static HTML/CSS/JavaScript.
- Logic: deterministic local rule engine.
- Data: browser memory; no network submission or persistent clinical data store.
- Output: readable flags and downloadable JSON.
- Model: no trained machine-learning model in v0.1.

### Research-grade target architecture (not implemented)
- Authenticated, role-based web client.
- API/service layer with schema validation and versioned rule execution.
- Approved mock/LIS data-ingestion adapters (CSV/JSON; later evaluate standards such as HL7/FHIR with institutional partners).
- Rules registry with owner, rationale, version, effective date, and verification test.
- Audit service recording input provenance, software/rules version, reviewer action, and output.
- Evaluation pipeline isolated from operational records, with pseudonymisation, access controls, retention policies, and dataset lineage.
- Optional ML module only after a specific task, representative labelled data, reference standard, and evaluation plan are approved.
- Monitoring for data drift, rule performance, alert burden, and site variation before deployment.

## 6. Potential distinguishing research directions (hypotheses, not novelty claims)
A. **Evidence-linked consistency graph:** model dependencies between record fields and show the minimal set of fields causing each inconsistency rather than an opaque global score.
B. **Uncertainty and abstention:** distinguish missing evidence, conflicting evidence, and non-applicable rules; refrain from flagging when prerequisites are absent.
C. **Versioned provenance bundle:** bind each finding to input values, rule version, explanation, timestamp, and human disposition so an independent reviewer can reproduce the result.
D. **Workflow-calibrated alert burden:** evaluate rules against expert adjudication and reduce low-value alerts without hiding high-priority data-integrity problems.
E. **Cross-site generalisation study:** determine whether the rule catalogue and schema transfer across laboratory systems without assuming workflows are identical.
These directions may already exist in laboratory systems, data-quality software, decision support, or published research. A targeted prior-art search is required.

## 7. Prototype scope
Implemented in index.html: synthetic case-entry form; missing-field and status-consistency checks; rule IDs and explanations; synthetic example loader; JSON export; research-only warning; responsive layout.
Not implemented: ML inference; image processing or pathogen identification; AST interpretation or treatment advice; accounts/backend/security assessment; LIS/EHR connection; validated clinical rule catalogue; clinical/regulatory validation.

## 8. Research questions and hypotheses
**RQ1:** Can the prototype detect predefined record completeness/consistency problems against expert-adjudicated labels?
**RQ2:** Does explanation-by-rule improve reviewer agreement and time to resolve a flagged record?
**RQ3:** How often do flags produce false alarms, and do these vary by specimen type, laboratory site, or workflow?
**H1:** On a pre-specified test set, the tool can achieve a sensitivity target for selected data-integrity conditions while keeping false-alert rate below a threshold agreed with laboratory partners.
**H2:** Showing triggering fields and rationale improves reviewer agreement versus a flags-only interface.
Document or pre-register hypotheses before confirmatory testing. Set targets with domain experts; no performance results are claimed here.

## 9. Validation plan
1. Define intended use, field dictionary, rule catalogue, and unit tests with clinical microbiologists.
2. Create synthetic edge cases for software verification; do not treat them as clinical validation.
3. Obtain ethics, institutional, privacy, and data-access approvals before using retrospective records.
4. Build an adjudicated dataset with independent reviewers and a resolution process for disagreement.
5. Separate development and test data by time and/or institution to reduce leakage.
6. Evaluate each rule: sensitivity, specificity, PPV, NPV, false alerts per 100 records, and confidence intervals.
7. Measure usability: task completion time, reviewer agreement, override rate, and a suitable usability scale.
8. Perform subgroup/site analyses and failure-mode review.
9. Run silent-mode prospective evaluation only after approvals; outputs must not affect care.
10. Publish negative as well as positive findings, limitations, rule versions, and reproducible methods.

## 10. Risks and mitigation
- **False reassurance:** no flags does not mean a record is correct; display this limitation.
- **False alerts:** measure alert burden and allow documented disposition.
- **Automation bias:** show rule basis and require independent verification.
- **Privacy:** use synthetic data in prototype; future data requires lawful basis, minimisation, security controls, and approvals.
- **Workflow variation:** verify rules at each site.
- **Model drift:** if ML is added, monitor distribution shifts and validate material updates.
- **Regulatory risk:** intended purpose and functionality determine applicable requirements; obtain Malaysian regulatory advice before clinical use.

## 11. Feasibility assessment
**Software feasibility:** high for narrow rule-checking; browser demo is implemented.
**Scientific feasibility:** moderate, conditional on laboratory collaborators, agreed inconsistency definitions, and an adjudicated dataset.
**Clinical feasibility:** unproven. A working interface or synthetic tests do not establish usefulness or safety.
**ML feasibility:** undetermined until a bounded task and representative labelled data are identified.
**Integration feasibility:** moderate to difficult because LIS interfaces, codes, workflows, privacy, and cybersecurity vary.
**IP feasibility:** unknown pending prior-art search, inventorship analysis, and assessment of eligibility/inventive step in relevant jurisdictions.

## 12. IP and publication strategy
1. Keep dated technical specifications, code, diagrams, design decisions, and experimental results.
2. Identify contributors and actual inventive contributions; ownership depends on agreements, employment, funding, and applicable law.
3. Search patent databases and non-patent literature before public disclosure. Include terms for laboratory data quality, microbiology decision support, specimen/result consistency, rule provenance, clinical laboratory audit, and explainable clinical AI.
4. Review patent families, claims, legal status, jurisdictions, and citations. A keyword search alone is insufficient.
5. Separate novelty, inventive step/non-obviousness, eligibility, and freedom-to-operate analyses.
6. Consult a registered patent professional in intended filing jurisdictions.
7. If plausible protectable subject matter is identified, discuss filing timing before public disclosure or publication.
8. Follow institutional, funder, and publication policies.
No patentability, novelty, ownership, or freedom-to-operate conclusion is made.

## 13. Milestones
- Phase 0 — Definition: intended use, stakeholder interviews, workflow map, prior-art search plan.
- Phase 1 — Prototype verification: schema tests, rule unit tests, edge-case coverage, export checks.
- Phase 2 — Expert review: usability sessions with synthetic cases; refine rule definitions.
- Phase 3 — Retrospective study: approvals, governed dataset, blinded adjudication, pre-specified metrics.
- Phase 4 — Independent validation: separate site/time period, failure analysis, publication.
- Phase 5 — Translation decision: regulatory, cybersecurity, quality management, clinical utility, and IP review before clinical deployment.

## 14. Next-milestone success criteria
Deliver a reproducible prototype with documented rules, tests, and protocol. Each flag should be traceable, deterministic, testable, and understandable; limitations should be visible; and an independent laboratory expert should be able to assess the protocol without unsupported claims.

## 15. Reference starting points
- FDA, Clinical Decision Support Software Guidance (January 2026): https://www.fda.gov/regulatory-information/search-fda-guidance-documents/clinical-decision-support-software
- FDA, Digital Health Policy Navigator — Clinical Decision Support: https://www.fda.gov/medical-devices/digital-health-center-excellence/step-6-software-function-intended-provide-clinical-decision-support
- WHO, Ethics and Governance of Artificial Intelligence for Health (2021): https://www.who.int/publications-detail-redirect/9789240029200
- Example AI microbiology decision-support study: https://www.sciencedirect.com/science/article/pii/S1876034124002752
These are starting points, not a complete prior-art search. Regulatory applicability must be assessed for each intended market and exact product function.
