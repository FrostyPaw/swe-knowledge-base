# Experiment: Pure Function for Reservation Creation

## Goal
Test whether an AI assistant can generate reservation logic as a pure function when given structured BDD requirements and a Mermaid flow diagram.

## Prompt Used
I am working on a Hotel Management System.

Here are the requirements:

User Story:
As a hotel administrator, I want to create a reservation for a guest and a room, so that the hotel can manage bookings in a structured and reliable way.

Acceptance Criteria:

1. Successful reservation creation
Given a guest exists in the system
And a room exists in the system
And the room is available for the selected dates
When the administrator creates a reservation with valid guest, room, check-in date, and check-out date
Then the system creates the reservation
And the reservation is saved in the system

2. Reject reservation if room is not available
Given a guest exists in the system
And a room exists in the system
And the room is already reserved for the selected dates
When the administrator tries to create a reservation
Then the system rejects the reservation
And the system shows an availability error message

3. Reject invalid date range
Given a guest exists in the system
And a room exists in the system
When the administrator creates a reservation where the check-out date is earlier than or equal to the check-in date
Then the system rejects the reservation
And the system shows a validation error message

Architecture flow:

Start reservation creation
-> Enter guest, room, check-in, check-out
-> Validate input
-> Check guest existence
-> Check room existence
-> Check date range
-> Check room availability
-> Create reservation object
-> Return success result

Write the logic for this feature as a Pure Function.
It must have no side effects (stateless) and must return a predictable output.
Use C#.

## Result
The AI produced a mostly correct solution on the first try, but the first version mixed business logic with state-changing behavior by assuming direct persistence.

## Did the AI succeed on the first try?
Partially.

It correctly implemented validation and decision logic, but the first response was not fully pure because it included actions that implied saving data.

## Did I need to adjust the requirements or diagram?
Yes.

I had to clarify that the function must not write to JSON files, update global state, or directly modify UI elements.
I also clarified that the function should only return a result object describing success or failure.

## Insight
The AI performs better when requirements are explicit and decomposed.
BDD and Mermaid reduced ambiguity, but the term "pure function" still needed to be reinforced with concrete restrictions about side effects.

## Conclusion
AI can generate useful logic for this feature, but only when the engineering harness is strict enough.
Pure-function constraints need to be stated very explicitly.
