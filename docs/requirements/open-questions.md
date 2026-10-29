# Open Stakeholder Questions and Decisions

Status: **Design-stage tracking.** Questions, documented baseline facts, and proposed design choices are separate. Instructor feedback authorizes improving the specification; it does not establish stakeholder answers, a country rollout, or numerical service targets.

## Stakeholder questions

Each Q-ID covers one information need. Questions are reworded and split from the earlier bundled register; the unresolved topics are preserved. Status is Open unless an answer is explicitly recorded. D-IDs link questions to technical decision tracking, not predetermined choices.

### Business and release planning

| ID | Topic | Question | Status | Decision area |
| --- | --- | --- | --- | --- |
| Q-01 | Problem | Which customer problem should the first release solve first? | Open | D-01 |
| Q-02 | Business type | Which types of table-service restaurant should the first release serve? | Open | D-01 |
| Q-03 | Coverage | Which geographical area should the first release cover? | Open | D-01 |
| Q-04 | Restaurants | How many restaurants are expected at launch? | Open | D-01 |
| Q-05 | Customers | How many customers are expected to use the first release? | Open | D-01 |
| Q-06 | Concurrency | How many customers and staff are expected to use the system at the same time? | Open | D-08 |
| Q-07 | Reservations | How many reservation requests are expected per day? | Open | D-08 |
| Q-08 | Orders | How many pre-orders are expected per day? | Open | D-08 |
| Q-09 | Peaks | What demand is expected during the busiest periods? | Open | D-08 |
| Q-10 | Launch | When should the first version of DineFlow launch? | Open | D-01 |
| Q-11 | Budget | What budget is available for the project? | Open | D-01 |
| Q-12 | Release approach | How should functionality be introduced over successive releases? | Open | D-01 |
| Q-13 | MVP validation | Which recorded capabilities are essential for the first usable release? | Open | D-01 |
| Q-14 | Search | Which restaurant filters do customers need? | Open | D-01 |

### Restaurant and payment integration

| ID | Topic | Question | Status | Decision area |
| --- | --- | --- | --- | --- |
| Q-15 | Operations | Which restaurant operations should DineFlow support? | Open | D-02 |
| Q-16 | Existing software | Which existing restaurant systems must DineFlow connect to? | Open | D-02 |
| Q-17 | Staff interface | What separate management interface, if any, does the restaurant need? | Open | D-02 |
| Q-18 | Accounting scope | What accounting functionality, if any, is expected from DineFlow? | Open | D-02 |
| Q-19 | Payment services | Which payment-related services are expected? | Open | D-04 |
| Q-20 | Booking ownership | Which system should decide whether a table can be booked? | Open | D-02 |
| Q-21 | Menu ownership | Who maintains restaurant and menu information? | Open | D-10 |
| Q-22 | Bill ownership | Which system provides the amount of the restaurant bill? | Open | D-05 |
| Q-23 | Handoff failure | How should staff handle confirmed information that has not reached the restaurant? | Open | D-06 |

### Visit rules and staff responsibilities

| ID | Topic | Question | Status | Decision area |
| --- | --- | --- | --- | --- |
| Q-24 | Reservation changes | Which details of a confirmed reservation may a customer change? | Open | D-03 |
| Q-25 | Reservation deadline | Until when may a customer change a reservation? | Open | D-03 |
| Q-26 | Order changes | Which details of a confirmed pre-order may a customer change? | Open | D-03 |
| Q-27 | Order deadline | Until when may a customer change a pre-order? | Open | D-03 |
| Q-28 | Visit cancellation | When may a customer cancel a visit? | Open | D-03 |
| Q-29 | Abandoned checkout | How long should an unfinished pre-order remain available for checkout? | Open | D-04 |
| Q-30 | Checkout cancellation | What should happen to the table reservation when a customer cancels an unpaid pre-order? | Open | D-03 |
| Q-31 | Late payment | How should a received payment be handled after the visit or order is no longer valid? | Open | D-04 |
| Q-32 | Refunds | Under what circumstances should a payment be refunded? | Open | D-04 |
| Q-33 | Staff roles | Which responsibilities should each employee have in each restaurant? | Open | D-11 |
| Q-34 | Call routing | Which staff should receive a customer's waiter call? | Open | D-07 |
| Q-35 | Unanswered call | What should happen when no staff member responds to a call? | Open | D-07 |
| Q-36 | Visit context | How should the system establish that a customer is at the restaurant? | Open | D-07 |
| Q-37 | After-visit features | How should the selected favorites or feedback features work? | Open | D-09 |
| Q-38 | Additional orders | How should additional in-restaurant orders be handled if this capability is selected? | Open | D-09 |

### Quality and data

| ID | Topic | Question | Status | Decision area |
| --- | --- | --- | --- | --- |
| Q-39 | Booking time | How long may a customer wait for a reservation result? | Open | D-08 |
| Q-40 | Search time | How long may a customer wait for search results? | Open | D-08 |
| Q-41 | Menu time | How long may a customer wait for a usable menu? | Open | D-08 |
| Q-42 | Call delivery | How quickly should staff receive a waiter-call notification? | Open | D-08 |
| Q-43 | Service interruption | How much unexpected service interruption is acceptable? | Open | D-08 |
| Q-44 | Maintenance | When may scheduled maintenance interrupt service? | Open | D-08 |
| Q-45 | Devices | Which mobile platforms and browser versions must be supported? | Open | D-08 |
| Q-46 | Adaptive media | What menu content should remain usable on a slow connection? | Open | D-12 |
| Q-47 | Personal data | How long should customer activity and preference information be retained? | Open | D-09 |
| Q-48 | Payment follow-up | Who should investigate a payment whose outcome is still unknown? | Open | D-04 |

Questions about accounting, refunds, or additional capabilities do not add them to the release scope. FR-024–FR-026 remain Could Have; FR-027 blacklist management remains excluded.

## Established baseline facts

These are facts already present in the repository, not newly claimed stakeholder approvals.

| Reference | Established scope | Still unresolved |
| --- | --- | --- |
| NFR-003 | Booking/payment are intended to operate 24/7 except scheduled maintenance | Measured availability target, maintenance allowance, unexpected downtime and monitoring conditions |
| NFR-004 | Overlapping bookings for the same table must be prevented | Authority ownership and coordination mechanism |
| NFR-006 / AC-004 | Management requires authentication/authorization; restaurants are separate business entities | Per-employee restaurant role assignments and identity mechanism |
| FR-020–FR-021 | Customer modification is Should Have | Editable fields, deadlines, and paid-order adjustments |
| FR-024–FR-026 | Additional dishes, favorites, feedback are Could Have | Selected behavior and release inclusion |
| FR-027 | Staff blacklist management is excluded initially | No initial-release blacklist design is needed |

## Decision register

The entries below are **unresolved design areas**, not approved decisions. Alternatives are engineering analysis, not a forced-choice stakeholder questionnaire.

| ID | Area | Status | Impact / unresolved design work | Related requirements |
| --- | --- | --- | --- | --- |
| D-01 | Target, scale, release and filter scope | Open; P-SCALE illustrative | Validate pilot business/geography, counts, launch date, budget, release strategy and first-release scope separately. | FR-001–FR-014, FR-027, NFR-011 |
| D-02 | Restaurant boundaries and booking authority | Open | Establish operational scope, existing-system contracts, authority across all booking channels, time-zone/interval semantics, and separate-interface/accounting boundaries. No POS/vendor selected. | FR-004–FR-005, NFR-004, AC-001, AC-005 |
| D-03 | Reservation and modification lifecycle | P-BOOK revised; proposed | Independent finite reservation versus a separately designed hold policy; capacity, cancellation, modification deadlines, expiry, and restaurant notification. | FR-005, FR-020–FR-021, NFR-004 |
| D-04 | Checkout and payment lifecycle | P-PAY revised; proposed | Approve finite draft expiry, pre-initiation cancellation, cancel/pay race handling, UNKNOWN reconciliation, late-success review, retry/refund policy and review owner. | FR-007–FR-008, NFR-008, AC-002 |
| D-05 | Pricing and restaurant bill | Open | Quote/currency, price changes, taxes/discounts, bill source, adjustments, and settlement reconciliation. No pricing additions approved. | FR-006–FR-008, FR-011 |
| D-06 | Restaurant delivery and recovery | P-INTEGRATION proposed | Acknowledgement, handoff timing, duplicate-safe business references, bounded recovery and escalation. | FR-009, AC-005–AC-006 |
| D-07 | Customer presence and waiter-call routing | P-CALL proposed | Visit-context evidence, staff recipients, acknowledgement, resolution and no-response recovery. | FR-010, FR-014, NFR-002 |
| D-08 | Quality measurements and workload | Open; P-SCALE illustrative | Approve latency/availability targets, operating/maintenance conditions, mobile matrix, demand profiles and test evidence. 24/7 is not 100% uptime. | NFR-001–NFR-011 |
| D-09 | Personalization and optional visit enhancements | Open | Occupancy definitions, activity/profile behavior, retention/access, recommendation evaluation, favorites/feedback, and additional-order details. | FR-015, FR-017–FR-019, FR-022–FR-026 |
| D-10 | Restaurant content ownership | Open | Restaurant/POS or delegated staff supply menus, prices, floor plans and information; menu editing remains a candidate capability. | FR-003–FR-006, AC-005 |
| D-11 | Restaurant-specific employee role sets | P-STAFF revised; proposed | Separate WAITER/MANAGER responsibilities, allow both for one employee, and evaluate permissions within each restaurant membership. No automatic inheritance of Manager rights. | FR-012–FR-014, NFR-006, AC-004 |
| D-12 | Adaptive multimedia overlap | Open; priorities retained | FR-016 remains Should Have, NFR-012 Could Have. Clarify capability/quality distinction, connection conditions and fallback. | FR-016, NFR-012 |
| D-13 | Unapproved legacy details | Deferred, not approved | Loyalty points, generic login APIs, tax/discount algorithms, food-refusal and refund operations remain outside confirmed detailed scope. Cancellation/expiry now have explicit proposed safeguards, not approved policy. | FR-007–FR-008, FR-020–FR-021 |

## Proposal register

| Proposal | Content | Status / dependency |
| --- | --- | --- |
| P-BOOK | Atomic booking; capacity/interval checks; finite independent reservation lifecycle | Proposed; D-02–D-03 |
| P-PAY | Quoted pre-orders; cancellation/abandonment; provider outcomes, reconciliation and ineligible late-success review | Proposed; D-03–D-05 |
| P-INTEGRATION | Independent acknowledged restaurant delivery and recoverable effects | Proposed; D-02, D-06 |
| P-STAFF | Role sets per employee/restaurant; WAITER and MANAGER can coexist | Proposed; D-07, D-10–D-11 |
| P-CALL | Routed notification, receipt, acknowledgement and resolution | Proposed; D-07–D-08 |
| P-SCALE | Illustrative pilot business/workload envelope in the overview | Planning assumption only; D-01, D-08 |

State labels are owned by the [proposed lifecycle model](functional-requirements.md#proposed-lifecycle-model), workload numbers by the [overview](../overview.md#target-businesses-and-planning-scale). No proposal is approved simply because it appears in a diagram.

## Recorded modelling revisions

The undefined POSIntegration has an explicit proposed contract. Domain entities, service orchestration, provider results and restaurant delivery are separated. The instructor's role criticism is addressed through restaurant-specific multiple-role assignment, rather than merging Waiter and Manager. Checkout abandonment is distinct from rejection or provider timeout.

The source name Restaurant Service System and repository name DineFlow refer to the same product. Scrum organizes a single backlog/Sprint cycle; prototyping is a validation technique inside that cycle. These documentation/model revisions are not records of stakeholder acceptance.

## Decision completion rule

An actual decision record must identify the selected policy, rationale, stakeholder/owner, date and affected Q/FR/NFR/AC/model references. Until that record exists, keep status Open, Proposed or Planning assumption. Approved baseline facts and unanswered questions must remain distinguishable.

[Class design](../architecture/class-diagram.md) · [Interaction assumptions](../architecture/sequence-diagram.md#design-assumptions)
