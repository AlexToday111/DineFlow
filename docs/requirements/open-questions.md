# Open Stakeholder Questions

Status: **Unanswered**. These questions are preserved from the source; no stakeholder answers have been supplied.

## Business goals

1. What is the main problem the system should solve first?
2. How many restaurants are expected to use the system?
3. What is the timeline for this project?

## Boundaries & Constraints

1. Is the system an independent platform with its own order and payment processing, or does it act as an intermediate layer that integrates with existing restaurant automation systems (iiko, R‑Keeper) and external payment providers?
2. Which existing restaurant automation systems need to be integrated, and how diverse are the options available from potential partners?
3. What is the budget and timeframe for the project — is a phased launch possible, and if so, what functionality is mandatory for the first release (MVP)?

## Functionality

1. Should customers be able to order additional dishes through the application while they are already sitting in the restaurant?
2. What other functionality users must have after visiting a restaurant? (add to favorites/like/dislike etc.)
3. Should customers be allowed to modify their table reservation or pre-ordered dishes after the order has been confirmed?
4. If yes, until what time?
5. What functionality restaurant staff must have? For example, move a customer to the black list or some form of contact between waiter and customer.

## Quality attributes

1. What is the maximum acceptable response time when searching for restaurants, loading the menu, or booking a table?
2. What level of system availability is required?
3. Should customers be able to book and pay at any time of day?
4. How quickly should a waiter receive a customer's call notification after the customer presses the button?

## Source ambiguities and overlaps

- The narrative describes several capabilities without priorities. The explicit requirement lists assign current occupancy, profiles, and recommendations to Should Have; average occupancy and dish advice to Could Have. Those listed priorities are retained.
- Questions about 24/7 booking and payment, staff functionality, and changes after confirmation remain unanswered even though related requirements are listed. Their presence is not evidence of stakeholder approval.
- Adaptive multimedia menus appear in both FR-016 (Should Have) and NFR-012 (Could Have), with related but different wording. Both entries and priorities are retained pending clarification.
- The platform-versus-integration question remains open. AC-001 and AC-005 establish integration capabilities without identifying specific partners. iiko and R-Keeper are examples in a question, not selected technologies.
- Payment-provider delegation and integration isolation are recommendations (AC-002 and AC-006), not mandatory technology decisions.
- Customer blacklist management is excluded from the initial release (FR-027), while the broader question about staff functionality remains open.
- Existing diagrams are preserved as source artifacts. They do not establish a complete use-case specification or a formally specified architecture. Diagram elements have not been promoted into additional requirements.
- The source uses the descriptive project name “Restaurant Service System”; the repository uses DineFlow. The methodology label “Scru” is corrected to “Scrum”, as confirmed throughout the source text.
