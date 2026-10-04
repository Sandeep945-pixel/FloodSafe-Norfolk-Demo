# Architecture

## Components and responsibilities

| Component | Responsibility |
| --- | --- |
| Expo / React Native client | Screens, local interaction state, speech controls, and requests to the backend |
| FastAPI backend | Conditions, persona, resource, and chat endpoints |
| Conditions adapter | Read simulated scenarios or fetch NWS alerts and NOAA tide predictions |
| Functional-needs profiles | Supply demo context about assistance, transport, equipment, caregiving, communication, and language |
| Local knowledge | Supply a static collection of demonstration facts |
| Rules router | Handle selected emergencies, refusal language, and simple questions without model generation |
| Gemini adapter | Assemble context and call Vertex AI for other questions |
| Response checker | Modify generated replies matching selected conflict or medical-advice patterns |

## Request flow

A chat request includes a message, selected demo persona, optional scenario, and conversation history. The backend resolves the profile and conditions before applying the rules router. A matched rule returns immediately. Other questions go to the model with the profile, conditions, local knowledge, and up to eight prior history entries.

Generated replies then pass through targeted pattern checks. The response includes a type and explanatory badges; model failures return a fallback message. Rule-generated and failure responses do not traverse the generated-response checker.

The profile and knowledge are supplied directly in the prompt. This is contextual generation, not a verified vector-RAG implementation.

## Conditions and resource directory

The conditions layer supports four simulated severity flags. It also includes HTTP connectors for NWS alerts and NOAA high/low tide predictions at Sewells Point. Rules map those inputs to a flag.

The current live path reuses a demonstration scenario for other fields. Road closures, shelter information, evacuation details, and parts of the displayed guidance are therefore not verified live information. Resource availability is calculated from flag thresholds in a static directory rather than queried from facilities.

Public demonstrations must expose this distinction. A successful weather API request must not label the entire response as authoritative live information.

## Client and data lifecycle

The mobile client keeps selected persona, scenario, messages, buddy interactions, and entered location labels in component state. The entered location is not used by the inspected backend to calculate risk. The device-location control is a placeholder; no geolocation implementation is present.

The inspected backend has no application account system, persistent user-profile store, or study-logging pipeline. This prototype structure should not be described as a deployed multi-user platform.

## Model and service dependencies

Current model code uses Gemini through Vertex AI. Older setup documentation referring to Claude does not describe this implementation. The mobile client is configured for a development backend on a local network; no production deployment manifest is present in the inspected tree.

[Back to FloodSafe Norfolk](../README.md)
