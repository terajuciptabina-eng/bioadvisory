# BioAdvisory — Validation Plan v0.1

## Purpose
Evaluate a research prototype that flags missing or internally inconsistent fields in structured microbiology records. This plan does not validate diagnosis, organism identification, antimicrobial susceptibility interpretation, or treatment decisions.

## Stage 1: Software verification (synthetic data only)
- Unit-test each rule against positive, negative, boundary, and contradictory cases.
- Verify deterministic output for identical inputs and rule versions.
- Test empty fields, unexpected values, long text, HTML-like input, special characters, and malformed identifiers.
- Confirm JSON export contains source fields, timestamp, rule IDs, explanations, and limitations.
- Check responsive usability and keyboard accessibility.
- Confirm no form data is transmitted to a server.

## Stage 2: Expert usability study
- Recruit qualified laboratory professionals under an approved protocol.
- Use synthetic cases; randomise case order and interface condition where feasible.
- Compare routine review with review assisted by BioAdvisory.
- Outcomes: task time, flag interpretation accuracy, reviewer confidence, agreement, and false-alert burden.
- Record qualitative feedback and usability issues.

## Stage 3: Retrospective data evaluation (only after approvals)
- Establish lawful access, ethics approval where required, data minimisation, de-identification/pseudonymisation, retention and access controls.
- Define data dictionary and rules with experts before evaluating the held-out set.
- Have two independent experts label each target inconsistency; resolve disagreement through a pre-specified adjudication procedure.
- Split by time/site where feasible. Avoid leakage of the same patient, encounter, or near-duplicate record across partitions.
- Freeze rule catalogue and analysis plan before testing.

## Metrics
For each rule and overall, report sensitivity, specificity, positive and negative predictive values at observed prevalence, confusion matrix and confidence intervals, false flags per 100 records, missed critical inconsistencies, reviewer time and agreement, subgroup/site performance, and failure examples.

No universal acceptance thresholds are asserted. Set thresholds with domain experts and risk analysis before confirmatory testing. Report all deviations.

## Stage 4: Prospective silent-mode evaluation
Only after governance approvals and retrospective results justify proceeding. Outputs must not influence care. Compare flags with expert review; monitor drift, missingness, site variation, alert burden, and software incidents.

## Stop conditions
Pause if data provenance is unreliable, there is an unmitigated privacy risk, critical inconsistencies are systematically missed, alert burden makes the tool unusable, or participants interpret output as a diagnostic or treatment instruction.

## Reporting
Publish protocol version, rule version, dataset construction, exclusions, missing data, confidence intervals, negative results, limitations, and funding/conflict-of-interest information. Follow institutional and relevant reporting guidance.
