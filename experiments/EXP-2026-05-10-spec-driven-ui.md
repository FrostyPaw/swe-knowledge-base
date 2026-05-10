# Experiment: Spec-Driven UI for Reservation Creation

## Goal
Evaluate whether an AI assistant can generate a user interface based on a strict design contract and connect it to the existing backend module.

## Design Contract Used
The UI was constrained by `/docs/DESIGN.md`.

The contract defined:
- Windows Forms as the framework
- fixed color palette
- Segoe UI typography
- spacing rules
- button and form rules
- requirement to connect to the ReservationCreation module

## Prompt Used
Generate a C# Windows Forms UI for the Create Reservation feature.

Use the DESIGN.md rules strictly:
- Framework: Windows Forms
- Primary color: #2563EB
- Background: #F8FAFC
- Text: #0F172A
- Success: #16A34A
- Error: #DC2626
- Font: Segoe UI
- Keep spacing consistent
- Buttons must have clear labels

The UI must connect to the existing ReservationCreationService from the ReservationCreation module.
When the user clicks the validation button, the UI must create a ReservationRequest and call the backend validation logic.
Do not bypass the module.
Do not introduce unrelated styles or dependencies.

## Result
The generated UI followed the design contract mostly correctly.

It used the defined colors, simple layout, and connected the button click event to the ReservationCreationService.

## Did the AI follow DESIGN.md strictly?
Mostly yes.

The AI followed the main framework, color, and component rules.
Some minor manual adjustments were needed to keep spacing consistent.

## How many prompts were needed?
Two prompts were needed:
1. Initial UI generation
2. Correction prompt to ensure the UI calls the existing backend service instead of duplicating validation logic

## Was the UI accessible and structurally sound?
Partially.

The UI is simple and understandable.
Labels are visible, buttons are clear, and success/error messages use different colors.
However, accessibility could be improved further with keyboard navigation and better validation feedback.

## Insight
Spec-driven UI generation reduced vague styling and prevented generic UI output.
The most important instruction was to connect the UI to the existing module instead of recreating business logic inside the form.

## Conclusion
The design contract helped control the AI output.
The UI became more consistent and better aligned with the project architecture.
