# Engineering decisions

## Translate resident needs into application context

Demo profiles use functional needs such as mobility assistance, transportation, powered equipment, caregiving, communication format, and language. This supports contextual explanations without requiring a diagnosis as the profile's organizing principle.

Profiles are demonstration inputs, not evidence of a completed onboarding, personalization, or user-validation study. Language fields alone do not establish a fully localized product.

## Use deterministic handling where the behavior should be explicit

The rules router handles selected danger language and simple intents before model invocation. These branches have inspectable outputs and avoid a model call for matched questions. More complex questions are passed to Gemini.

The emergency detector is pattern-based and needs coverage testing. No model call for a matched request does not mean the phone can execute the backend rules without connectivity.

## Separate generation from targeted checks

The model receives structured context and instructions on educational scope and response style. Separate checks examine generated output for selected conflicts with evacuation and road-status context, dosing statements, and treatment-change advice.

This decomposition makes individual controls testable. Pattern checks are not a comprehensive safety proof, and replacement text must be held to the same data-quality standard as the original generation.

## Keep community resources separate from individual profiles

The resource endpoint returns a shared directory organized by service category. A facility can appear under multiple categories, such as shelter and equipment charging. Open entries are sorted before closed entries.

The endpoint does not require a persona. In the current prototype, availability is scenario logic, not a live operational status feed.

## Make explanations accessible in more than one form

The mobile interface includes read-aloud controls, adjustable text sizes, visual status labels, and accessibility properties on controls. These are implemented affordances. Usability with assistive technologies and residents with different access needs remains an evaluation task.

## Make uncertainty visible

External feeds, model services, and the mobile-backend connection can fail independently. A production design needs distinct states for unavailable, stale, simulated, and current data. The current fallback behavior needs revision before public operational use.

This is a product requirement as well as a reliability requirement: a resident must be able to tell whether the application knows the current conditions.

[Back to FloodSafe Norfolk](../README.md)
