# Evaluation

The current review inspected implementation and test definitions. It did not run the application, invoke cloud services, execute the tests, or validate local emergency information. No performance or user-outcome figures are published here.

## Existing test definitions

The repository includes cases for danger-language routing, refusal handling, direct flag answers, and routing complex requests to the model. Response-check tests cover selected evacuation conflicts, closed-road mentions, dosing statements, and treatment-change language. Directory tests cover categories, availability rules, sorting, and response structure.

These test definitions show intended software behavior. Passing tests would not establish that the underlying local facts are current or that the application is safe for operational use.

## Proposed evaluation

| Area | Method | Evidence to report |
| --- | --- | --- |
| Source integrity | Inspect every displayed fact's source and age | Live, static, simulated, missing, and stale fields |
| Feed failures | Simulate timeouts, HTTP errors, empty responses, and malformed values | Resulting UI state and fallback behavior |
| Routing | Test danger-language paraphrases and ambiguous requests | Missed matches, incorrect bypasses, and unsupported intents |
| Response checks | Test conflicts, negation, paraphrases, and replacement text | False positives, misses, and errors introduced by overrides |
| Context use | Hold conditions fixed and vary functional needs | Whether relevant assistance changes without inventing facts |
| Accessibility | Task-based tests on devices and assistive technologies | Task completion, difficulties, and participant feedback |
| Comprehension | Ask participants to explain what a message means | Understanding of action, uncertainty, and information source |
| Reliability and cost | Controlled synthetic requests | Latency distributions, failure rates, model-call share, and cost |
| Notification extensions | Test delivery, failure, consent, and receipts | Verified outcomes rather than UI acknowledgments |

Future results should identify the system version, scenarios, review criteria, participant or sample count, and limitations. Source-code evidence, test results, user feedback, and operational validation should be reported separately.

[Back to FloodSafe Norfolk](../README.md)
