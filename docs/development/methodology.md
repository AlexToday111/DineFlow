# Development Approach and Methodology

Status: **Planned approach.** No completed prototype, Sprint, or production implementation is claimed.

**Project:** DineFlow / Restaurant Service System

**Lifecycle approach:** Iterative prototyping and incremental development within Scrum

**Development methodology:** Scrum, with Rapid Prototyping used for validation inside each relevant Sprint

**Team:** Three developers and one tester, studying in their third year

## Why this approach fits DineFlow

The floor plan, table/time selection, pre-order checkout, and staff call queue need user validation. Booking ownership, payment recovery, and staff permissions remain unresolved. Rapid Prototyping lets the team test those interactions with representative customers, waiters, and managers before implementing integrations.

Scrum will organize this work into proposed two-week Sprints. The team will balance scope with university commitments and use each review to collect evidence, not assume stakeholder acceptance. Sprint length and participation arrangements are planned. Product Owner and Scrum Master accountabilities have not yet been assigned; the tester title does not make testing exclusive to one person.

## Planned prototype validation

| Prototype | Validation task | Evidence and decision |
| --- | --- | --- |
| Discovery and booking | Ask a customer to find a restaurant and select a table/time; simulate two competing booking requests | Observe task completion and comprehension of conflict messages; review P-BOOK and authority decision D-02 |
| Pre-order checkout | Select dishes, review the amount, then simulate confirmation, rejection, timeout, cancellation before payment, and abandoned checkout | Verify that no unknown payment is presented as failed or paid; review P-PAY with stakeholders |
| Staff service queue | Ask a waiter to acknowledge and resolve a call; simulate failed notification delivery and unauthorized access | Validate role scope, call state labels, and escalation policy (P-STAFF, P-CALL) |

External payment/POS behavior may be simulated during prototyping. A successful simulation validates a flow hypothesis, not a working provider integration or a quality target.

## Example Sprint Goals

These are candidate goals, not a schedule or completed work.

| Candidate Sprint | Goal | Reviewable result and acceptance examples |
| --- | --- | --- |
| Booking | Validate table selection and conflict handling | Clickable prototype, UC-02 walkthrough, and concurrent-request test design. Given one table/interval and two requests, at most one succeeds; the other receives a conflict (FR-005, NFR-004). |
| Pre-order and payment | Validate honest payment status and restaurant delivery | UC-03 prototype with provider/POS simulations. An unanswered provider request stays UNKNOWN; a duplicate success does not create a second payment or order; delivery failure does not erase payment success. |
| Restaurant service | Validate scoped waiter and manager roles, including one employee holding both | UC-04/UC-05 prototype and permission cases. An unrelated restaurant's staff cannot access its requests; an acknowledgement is distinguishable from resolution. Proposed permissions must be approved before becoming release acceptance criteria. |

Quantitative performance acceptance remains blocked on the targets and workload in D-08. Proposed rules are evaluated as hypotheses until agreed.

## One Sprint and prototype cycle

**Scrum is the single coordination and planning framework. Rapid Prototyping is the validation technique used inside it.** There is one Product Backlog, one Sprint Goal and one Sprint Backlog per Sprint, not a second prototype planning process. Production work proceeds incrementally in the same framework.

The proposed Sprint duration remains **two weeks**. A complete focused prototype cycle is planned to fit one Sprint: refine one uncertainty, design/build a reviewable prototype, validate it, and turn evidence into backlog updates. A broader workflow may need several Sprints; a prototype demonstration is not automatic requirements approval.

The schedule below is illustrative for ten working days, not a commitment. Activities overlap; their durations are not intended to sum as independent sequential work.

| Stage | Indicative timing | Responsible participants | Concrete deliverable | Expected outcome |
| --- | --- | --- | --- | --- |
| Sprint Planning | Day 1, about 2 hours | Three developers and tester; product representative/accountability assignment TBD | One Sprint Goal, selected linked backlog items, capacity and initial acceptance cases | A feasible reviewable outcome is selected |
| Requirements refinement | Two 60–90 minute sessions on days 1–2; short follow-ups as needed | Team with available customer/staff representative | Clarified UC, unresolved Q/D-IDs, proposed acceptance criteria | Requirements identification is several focused discussions, not assumed to be one meeting or a completed project-wide phase |
| Prototype design | Days 2–3, roughly 2 days | Developers; tester reviews failure/permission cases | Flow/screens or executable model for the Sprint Goal | The uncertain user interaction becomes testable |
| Implementation | Days 4–7, roughly 4 days | Developers with continuous tester input | Prototype code/simulation or a production increment, explicitly labelled | A demonstrable artifact exists; external mocks are disclosed |
| Validation | Days 7–9, roughly 2 days, overlapping implementation | Tester and developers with representative users where available | Task observations, acceptance results, conflict/failure/abandonment evidence | Identify supported assumptions, defects and open decisions |
| Sprint Review | Day 10, about 1 hour | Team and available stakeholders | Demonstration against the Goal and acceptance cases | Feedback is recorded; stakeholder decisions are recorded separately if made |
| Backlog refinement | Day 10, about 1 hour, after review feedback | Team; product ordering/accountability owner TBD | Updated/new Product Backlog Items with links, criteria and dependencies | Evidence changes future work through the same backlog |
| Retrospective | Day 10, about 45 minutes | Whole team | One or two process improvements for the next Sprint | Adjust collaboration and validation practice |

A proposed short Daily Scrum supports coordination throughout. Product Owner and Scrum Master accountabilities remain unassigned; job titles of three developers and one tester do not resolve those accountabilities. Testing is shared work.

At Sprint end, produce a reviewable prototype or increment appropriate to the Goal, acceptance evidence, updated use-case/requirement clarification, recorded decisions still needed, and a revised backlog. No separate artifact file or backlog system is selected here.

## From prototype evidence to implementation work

"Use validated requirements to guide implementation" means converting an observed behavior into explicit acceptance criteria, then traceable work. It does not mean implementing every suggestion or declaring a policy approved after a demo.

For example, a waiter-call prototype may show that a dual-role employee can handle calls but another restaurant's Manager must not see them:

1. Record the observation and test context against UC-04/UC-05, FR-014, NFR-006 and D-11.
2. Clarify P-STAFF role-set criteria: WAITER-only, MANAGER-only, both roles in one restaurant, and a different assignment elsewhere. Keep the policy proposed until accepted by the appropriate stakeholder.
3. Update the existing backlog item or create focused implementation items for scoped authorization, call acknowledgement and denial tests. Each item carries the requirement IDs, observable acceptance conditions, evidence and remaining decision dependencies.
4. Order those items in the same Product Backlog; select implementable items during a later Sprint Planning when their needed decisions are sufficiently clear.
5. Re-test the behavior in the increment and demonstrate the evidence at Sprint Review.

If checkout testing reveals an abandoned draft, update UC-03 and P-PAY with a finite proposed expiry rule, add an expiry/reconciliation implementation item and alternative-path tests, and keep the actual deadline as Q-29/D-04 until agreed.

MoSCoW categories remain unchanged. Prototype scope does not redefine the release MVP, and a positive task observation does not establish a performance service level.

## Proposed Definition of Done

For a documentation/prototype item:

- Related requirements, main flow, and failure behavior are traceable.
- Proposed rules and unresolved decisions are labelled; no stakeholder approval is inferred from a demonstration.
- A peer has reviewed consistency across prose, use cases, class models, and sequences.
- UML sources render, SVGs have been visually inspected, and local links resolve.
- Prototype acceptance cases have results recorded, including conflicts and access failures where relevant.

For a future implementation item, additionally require reviewed code, meaningful behavior/security checks, relevant integration evidence, and verified recovery behavior. Simulated integrations and unagreed performance thresholds must be reported as limitations. This Definition of Done is proposed and has not yet been adopted by the team.

## Deliverables and constraints

The existing documentation provides the requirements baseline, scenario specifications, models, and decision register. Prototypes, feedback, a Product Backlog, Sprint Backlogs, and future test evidence are planned artifacts. No additional technology stack or delivery infrastructure is selected here.

The approach fits a small team, changing requirements, limited experience, and limited time. Focused increments reduce rework across reservations, ordering, payments, and recommendations while preserving a coherent end-to-end design.
