# Experiment: Pattern Implementation for Reservation Creation

## Goal
Evaluate whether an AI assistant can implement the reservation creation feature using a classical design pattern without creating spaghetti code.

## Selected Pattern
Strategy pattern.

## Prompt Used
Implement the reservation creation logic for a C# Hotel Management System using the Strategy pattern.

The module must:
- validate guest existence
- validate room existence
- validate date range
- validate room availability
- keep each validation rule in a separate class
- avoid side effects
- return a predictable result object
- follow clean OOP principles
- follow the project AGENTS.md instructions
- refer to the /docs folder for project context

## Result
The AI produced a modular implementation where each validation rule was separated into its own class.

The Strategy pattern helped make the logic easier to understand because each rule had one clear responsibility.

## Did the AI apply the pattern accurately?
Mostly yes.

The structure matched the Strategy pattern:
- common interface
- multiple interchangeable rule implementations
- service class coordinating the rules

## Problems Observed
The pattern added more files and classes than a simple if-statement solution.

For a very small application, this may look like overengineering. However, it is useful because reservation validation is a critical feature and may grow later.

## Evaluation
The Strategy pattern improved:
- readability
- maintainability
- extensibility
- testability

It also helped guide the AI toward modular code and reduced the risk of spaghetti code.

## Conclusion
The pattern was appropriate for this feature because reservation validation consists of multiple independent business rules.
The AI performed better when the requested pattern and constraints were stated explicitly.
