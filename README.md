# BioAdvisory

**Clinical Microbiology Intelligence — research prototype v0.1**

BioAdvisory is an early browser-based research prototype exploring transparent software checks for completeness and consistency review of clinical microbiology records.

## Current prototype
- Static single-page application in index.html; no build step or dependencies.
- Runs locally in the browser.
- Uses synthetic/manual test records only.
- Applies deterministic, explicit rules to flag missing or conflicting statuses.
- Shows a plain-language explanation for each flag.
- Exports a JSON research review record.
- Responsive desktop/mobile layout.

## Safety and scope
This is **not a medical device, diagnostic system, or clinically validated tool**. It does not identify organisms, determine infection, interpret antimicrobial susceptibility for treatment, or recommend therapy. Do not use it for patient care or enter patient-identifiable or real clinical data. Outputs require human review and are limited to the configured demonstration rules.

## Run
Open index.html in a modern browser. Click **Load synthetic example**, then **Run consistency review**. The demo does not send form data to a server.

## Proposed research question
Can a transparent, rule-based consistency layer improve detection of incomplete or internally conflicting microbiology record fields compared with routine manual review, without increasing reviewer workload unacceptably?

## Next steps
1. Co-design workflow and intended use with clinical microbiologists and laboratory quality personnel.
2. Conduct a documented prior-art and literature review before asserting novelty.
3. Define intended use, data dictionary, rule catalogue, risk analysis and evaluation protocol.
4. Obtain institutional approvals, ethics review and data governance approval before any clinical-data study.
5. Build a de-identified, adjudicated test set; split by site/time to prevent leakage.
6. Measure sensitivity and specificity for predefined data-quality flags, false-alert rate, reviewer time, inter-rater agreement, and usability.
7. Independently validate before clinical deployment; assess Malaysian and target-market regulatory requirements.

## IP
No novelty, inventiveness, freedom to operate, or patentability has been established. The concept overlaps broadly with existing clinical decision support, laboratory information systems, and AI microbiology research. Record contributions and dates, preserve technical notes, conduct a search of patent and non-patent literature, and seek qualified patent advice before public disclosure or filing.
