# Feature status and development direction

The table separates implementation evidence from demonstration behavior and planned work. No delivery dates or operational readiness are implied.

| Capability | Status | Next evidence needed |
| --- | --- | --- |
| Mobile screens and backend endpoints | Implemented in prototype | End-to-end execution and usability results |
| Speech output and adjustable text | Implemented in prototype | Device and assistive-technology checks |
| Rules-first chat and response checks | Implemented in prototype | Boundary cases, paraphrases, and false-positive assessment |
| Gemini / Vertex AI integration | Implemented code path | Controlled execution, latency, and failure observations |
| NWS / NOAA connectors | Implemented code paths | HTTP error handling, missing-data behavior, freshness, and interpretation checks |
| Resource directory | Static demo data with flag-derived availability | Authoritative facility status and update process |
| Road map | Schematic scenario display | Actual geospatial data and verified road conditions |
| Address and device-location controls | UI placeholders for localization | Permission handling, geocoding, and location-to-risk mapping |
| Buddy notifications and coordinator check-ins | Simulated local interactions | Real delivery service, consent, receipt handling, and failure reporting |
| Offline operation | Partial static content and backend fallbacks | Device-side logic, cached data, and explicit stale/unavailable states |
| CNN–LSTM flood prediction | Planned integration, absent from this app | Defined model contract, validation, and integration tests |
| Accounts and persistent profiles | Not implemented | Access controls and an appropriate storage design |
| Evaluation logging | Not implemented | A reviewed event schema, consent process, and retention rules |
| Public hosted demo | Not available | Isolated demonstration environment and a walkthrough |

## Priority 1: trustworthy demonstrations

Separate live and simulated fields throughout the backend and interface. Replace reassuring fallback conditions with an unavailable state when information cannot be obtained. Keep facility status, route claims, and simulated notifications visibly labeled. Review the content used in deterministic responses and AI overrides.

## Priority 2: evaluation and presentation

Run the existing regression suite, add targeted cases for observed failure modes, and record a clearly labeled scenario walkthrough. Evaluate accessibility and comprehension with an appropriate participant protocol. Report the evidence and limitations alongside any results.

## Priority 3: operational integrations

Develop authoritative resource and road feeds, model integration, real notification delivery, and offline support as separate increments. Each changes what the product can reliably claim and needs its own acceptance criteria.

[Back to FloodSafe Norfolk](../README.md)
