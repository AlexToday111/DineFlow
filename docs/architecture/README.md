# Architecture and UML

Status: **Proposed logical design.** The models support academic review and design validation. They do not establish a technology stack, database schema, deployed services, or implemented behavior.

## Reading order

1. [Use cases](../requirements/use-cases.md): product boundary and Customer/Waiter/Manager responsibilities.
2. [Class models](class-diagram.md): a domain overview, then booking, ordering/payment, and staff operations.
3. [Sequence diagrams](sequence-diagram.md): table reservation, pre-order/checkout exits, payment outcomes, and waiter calls.
4. [Architectural constraints](../requirements/architectural-constraints.md): responsibility boundaries and integration recommendations.
5. [Decision register](../requirements/open-questions.md): approval gaps and alternative policies.

## Diagram index

All 12 current diagrams have editable sources and generated SVGs in the existing asset directories.

| View | Current diagram | Main traceability |
| --- | --- | --- |
| Use cases | [General](../requirements/use-cases.md#general-use-case-diagram) | FR-001–FR-026; AC-001, AC-005 |
| Use cases | [Customer](../requirements/use-cases.md#customer-use-case-diagram) | FR-001–FR-011, FR-015–FR-026 |
| Use cases | [Waiter](../requirements/use-cases.md#waiter-use-case-diagram) | FR-013–FR-014; P-STAFF/P-CALL |
| Use cases | [Manager](../requirements/use-cases.md#manager-use-case-diagram) | FR-012–FR-013; NFR-006; P-STAFF |
| Classes | [General domain](class-diagram.md#general-domain-model) | Core visit entities; FR-017–FR-019 remain Should Have |
| Classes | [Booking/reservation](class-diagram.md#booking-and-reservation) | FR-004–FR-005, FR-009, FR-020; NFR-004 |
| Classes | [Ordering/payment](class-diagram.md#ordering-and-payment) | FR-006–FR-009; AC-002, AC-005–AC-006 |
| Classes | [Staff/operations](class-diagram.md#restaurant-staff-and-operations) | FR-010, FR-012–FR-014; NFR-006 |
| Sequence | [Table reservation](sequence-diagram.md#table-reservation) | UC-02; atomic booking invariant |
| Sequence | [Pre-order/checkout exit](sequence-diagram.md#pre-order-and-payment) | UC-03; confirmation, unpaid cancellation and abandonment |
| Sequence | [Payment outcomes](sequence-diagram.md#payment-initiation-and-outcomes) | UC-03; verified results, timeout, late success and review |
| Sequence | [Waiter call](sequence-diagram.md#waiter-call) | UC-04; routing, receipt, acknowledgement, resolution |

[Source and SVG file index](../../assets/diagrams/source/README.md#files)

## Scope and modelling conventions

The [recorded requirements](../requirements/functional-requirements.md) own scope and MoSCoW priorities. Their proposed lifecycle section owns the state vocabulary. P-BOOK, P-PAY, P-INTEGRATION, P-STAFF, and P-CALL identify unapproved policies used consistently in the diagrams.

Domain entities represent business facts; application services coordinate operations; explicit interfaces describe authoritative booking, provider access, restaurant handoff, and staff notification. These distinctions do not imply separate microservices or selected storage technologies.

AC-001/AC-005 establish integration capability; AC-002/AC-006 remain recommendations. The diagrams adopt provider delegation and separated integration contracts as proposals. Authoritative availability ownership, lifecycle/deadline policies, bill/payment rules, staff allocation, and recovery targets remain open.

FR-011 bill payment and FR-020/FR-021 modification are specified in use cases but not claimed as complete detailed integration sequences. Could Have features remain documented candidates. Blacklist management is excluded initially. International rollout and physical order-refusal/refund workflows have no approved detailed requirements.

## Geographical expansion assessment

International rollout is a future scenario, not an approved requirement or selected deployment. China is an example to assess, not a committed launch country. P-SCALE currently assumes one pilot region/country; the [overview](../overview.md#target-businesses-and-planning-scale) owns the illustrative workload.

| Software concern | Consequence to investigate before adding a country | Evidence needed; no decision implied |
| --- | --- | --- |
| Language and locale | Separate translatable text and localized menu content; support appropriate date, number, currency, address, and phone formats | Reviewed translations and country-specific task walkthroughs |
| Restaurant time zones | Represent booking intervals as unambiguous instants with restaurant zone context; show restaurant-local visit times and handle clock changes | Cross-zone booking, midnight, and clock-change tests; exact time model proposed under D-02 |
| Data governance | Determine applicable privacy, residency, transfer, retention, and access obligations for the planned data flows | Country-specific assessment before choosing storage/processing locations; no legal conclusion or compliance claim is made here |
| Network and placement | Measure customer/staff-to-system and system-to-provider/POS latency from candidate regions, including mainland China if considered | Regional measurements and failure tests before deciding whether additional infrastructure is justified |
| Regional payments | Verify currencies, payment methods, provider availability, result verification, and reconciliation semantics | Provider contract tests; retain the PaymentProviderPort boundary |
| Restaurant integrations | Identify differences in POS availability ownership, bill data, menu formats, and acknowledgement behavior | Adapter/contract tests and a booking-authority agreement for all channels |
| Capacity and deployment | Recalculate restaurant/customer counts, peak request mix, regional dependencies, rollout and rollback needs | A revised workload envelope and deployment options; no automatic move to microservices or a region per country |
| Monitoring and recovery | Observe regional latency, errors, delivery failures, payment UNKNOWN/review queues, and cross-region dependencies | Regional dashboards/probes and agreed recovery ownership/targets |

Finding restaurant partners is a business activity. Software scalability is demonstrated through workload, isolation, latency, failure/recovery, and integration evidence. More countries do not by themselves establish a particular architecture. Any expansion must revisit D-01, D-02, D-05, D-08, and the proposed scale envelope before implementation.

## Superseded diagrams and maintenance

The old combined class model and sequence are explicitly replaced at their existing source/SVG filenames by focused current views. Pre-order creation/checkout exits are now separate from provider payment processing. Existing [class PNG](../../assets/diagrams/restaurant-service-class-diagram.png) and [use-case PNG](../../assets/diagrams/restaurant-service-use-case-diagram.png) are regenerated from the current general class/use-case sources. The source guide links each PNG and SVG to its editable source; there are no maintained image-only diagrams.

Edit PlantUML sources, regenerate their SVGs, inspect readability, update affected prose, and check links and requirement/state consistency together. Rendering instructions are in the [source guide](../../assets/diagrams/source/README.md#rendering).

[Back to project documentation](../../README.md#documentation)
