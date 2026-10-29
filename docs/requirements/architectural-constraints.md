# Architectural Constraints

The original modal verbs are preserved: “must” identifies mandatory constraints; “should” identifies recommendations. Integration is conditional where the source says “where required”.

- **AC-001** — The system must be able to integrate with existing restaurant automation/POS systems where required.

- **AC-002** — Payment card processing should be delegated to a certified external payment provider rather than storing raw card details in the application.

- **AC-003** — The customer-facing functionality must be accessible from smartphones.

- **AC-004** — The architecture must support multiple restaurants as separate business entities.

- **AC-005** — The system must exchange booking, order and table-availability information with restaurant-side systems.

- **AC-006** — External integrations should be isolated from the core business logic so that different restaurant systems can be supported.

These constraints do not select a technology stack or identify specific integration partners. See the [open questions](open-questions.md) and [architecture documentation](../architecture/README.md).

## Responsibility boundaries

| Party | Responsibility in the proposed model | Boundary |
| --- | --- | --- |
| DineFlow | Customer/staff interactions, authorization, coordinating booking and ordering, reflecting verified payment state, and tracking restaurant handoff | Does not infer availability, payment success, or delivery success from a sent request alone |
| Authoritative booking source | Decide whether one table/interval can be reserved and atomically create a booking | DineFlow or a restaurant/POS source: D-02 is open; there must be one coordinated authority for all booking channels |
| Restaurant/POS | Supply agreed restaurant-side information and receive confirmed reservations/pre-orders | Data ownership, bill source, acknowledgement, and local staff workflow remain D-02, D-05, D-06, D-10 |
| External payment provider | Process payment and provide a verifiable result/reference | Recommended by AC-002 and adopted as proposal P-PAY; no vendor, processing protocol, or credential design is selected |
| Staff notification endpoint | Receive a call notification for the relevant restaurant staff | Delivery evidence and offline/escalation policy remain D-07–D-08 |

AC-004 requires separate restaurant business entities. The proposed permission checks use restaurant scope; this does not select a database isolation mechanism or imply a multi-country release.

## Proposed integration contracts

The logical interfaces in the focused class diagrams express responsibilities, not deployed services or database APIs:

- **BookingAuthority:** preview availability and atomically create a reservation if the table remains available. Its success/conflict/unavailable results support NFR-004. No specific transaction, lock, storage engine, or distributed architecture is chosen.
- **POSIntegration:** deliver a confirmed reservation or paid pre-order and return acknowledgement/failure. The original undefined interface is replaced by this explicit contract. Booking/table information is read through BookingAuthority in these scenarios; wider synchronization ownership remains open.
- **PaymentProviderPort:** initiate an attempt, verify a provider result, and query an unresolved result. Business order coordination depends on this contract, rather than making an OrderService implement a POS interface.
- **StaffNotifier:** notify the relevant restaurant's staff and distinguish endpoint receipt from failure. Human acknowledgement remains a separate call state.

An interface may be fulfilled by an internal component or a partner adapter as appropriate. These are proposals supporting AC-006; implementing each as a microservice is neither required nor recommended by this documentation.

## Authority and failure handling

Displayed table availability is advisory. The authoritative create-if-available operation must prevent conflicting successful bookings even if the preview was free. If other channels bypass that authority, global conflict prevention cannot be claimed; a synchronization/ownership agreement is required (D-02).

P-INTEGRATION proposes independently tracked delivery states and repeated handoff using the same business reference. A failed handoff is retained for recovery and does not roll back a verified payment. Retry timing, limits, escalation, acknowledgement semantics, and any compensation remain D-06. Confirmed reservations are handed off after creation; pre-orders are handed off after verified prepayment in the illustrated P-PAY workflow.

P-PAY treats timeouts as unknown and verifies results before applying them. Stable attempt/business references and duplicate-safe processing are proposed safeguards, not selected middleware. P-CALL similarly separates call creation, notification receipt, and staff response.

Frameworks, databases, hosting, provider partners, identity technology, numerical performance targets, and data residency are not selected. See the [decision register](open-questions.md) and [architecture index](../architecture/README.md).

## Planning scale and expansion boundary

The [target-business and workload envelope](../overview.md#target-businesses-and-planning-scale) is proposal P-SCALE, not a new AC or capacity guarantee. AC-004 supports multiple separate restaurant businesses; it does not grant chain-wide administration, multi-country data sharing, or globally scoped staff roles.

P-STAFF assigns roles per employee/restaurant membership. One employee may have both WAITER and MANAGER in one restaurant without giving every waiter Manager access. The interface/authorization design must evaluate the requested action against the active restaurant and assigned role set.

A future country rollout, including China if selected, requires the [geographical expansion assessment](../architecture/README.md#geographical-expansion-assessment): localization, time-zone interpretation, applicable data obligations, network latency, regional payments/POS contracts, monitoring, and revised workload/deployment evidence. No country-specific legal claim, infrastructure region, or hosting vendor is selected here.
