# BioAdvisory browser test suite

## Run the tests
1. Open `tests/rule-engine-tests.html` from the published GitHub Pages site, or serve the repository locally over HTTP.
2. Click **Run all tests**.
3. Review the PASS/FAIL results and investigate every failure before changing rule logic.

Live URL after the test branch is merged and deployed:
`https://terajuciptabina-eng.github.io/bioadvisory/tests/rule-engine-tests.html`

The harness loads `../index.html` in a same-origin iframe and tests the app's actual controls and rendered output. It does not duplicate the rules in a second implementation.

## Coverage
- R00: clean baseline
- R01–R13: one targeted test for each configured rule
- Synthetic values only

## Limits
These are browser-level regression checks, not clinical validation. Passing tests show only that the current implementation emits the expected configured flags for these cases. They do not establish clinical correctness, safety, sensitivity/specificity, or fitness for patient care. Additional tests are still needed for input escaping, export payload integrity, keyboard accessibility, responsive behavior, and rule interactions. Do not enter real patient data.
