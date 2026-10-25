# BioAdvisory

**Disease & Medical Image Intelligence — research prototype v0.2**

BioAdvisory is a browser-based research workspace bringing together medical-image intake preparation, an educational disease reference library, and explainable consistency checks for synthetic microbiology records.

## Product areas

- **Overview:** navigation across the core workflows and explicit capability boundaries.
- **Image workspace:** select and preview a local image, choose an image modality and research task, and check intake completeness.
- **Disease library:** searchable starter references for tuberculosis, dengue and malaria, including causes, typical course, warning signs, treatment principles and links to WHO resources.
- **Lab record review:** deterministic rule checks for missing or conflicting fields in synthetic microbiology records, with explanations and JSON export.
- **Research & safety:** capability summary and roadmap for future evaluation.

## Important capability boundary

**There is no AI image-analysis model or inference service connected.** The image workspace only previews an image in the browser and checks whether intake fields are completed. It does not identify a disease, interpret a scan, classify a microorganism, or provide a diagnostic prediction. Do not describe the current build as an AI diagnostic system.

The image preview uses a browser object URL and does not upload the selected file to a server. Do not upload identifiable patient data, confidential images or real patient records.

This project is not a medical device or clinically validated system and must not be used for patient care, emergency decisions or treatment selection. Disease entries are educational starter summaries, not prescriptions or a comprehensive disease database. Qualified clinicians must use current local guidance.

## Run locally

Open `index.html` in a modern browser. No build step or third-party JavaScript dependency is required.

- Open **Image workspace** to preview a non-identifiable research image and check intake readiness.
- Open **Disease library** to search/filter the starter entries and follow source links.
- Open **Lab record review**, select **Load example**, then **Run consistency review** to see explainable synthetic flags and export JSON.
- Open `tests/rule-engine-tests.html` from a local web server or the deployed site to run browser checks. The harness must be served from the same origin as `index.html`; results have not been independently clinically validated.

## Planned development sequence

1. Define the first intended image use case and target users with clinical domain experts.
2. Choose modality-specific model candidates only after reviewing dataset rights, provenance and evidence.
3. Design a secure backend, privacy/data-governance controls, consent and retention/deletion workflows before processing any sensitive material.
4. Create an expert-adjudicated, appropriately governed evaluation set with external and subgroup testing.
5. Measure sensitivity, specificity, calibration, false positives/negatives and failure modes; display uncertainty and provenance.
6. Conduct usability, safety, ethics and relevant Malaysian/target-market regulatory reviews before any clinical use.

## Research and intellectual property

No novelty, inventiveness, freedom to operate or patentability has been established. Record contributions and dates, preserve technical notes, conduct a prior-art and literature review, and seek qualified advice before asserting or filing IP claims.
