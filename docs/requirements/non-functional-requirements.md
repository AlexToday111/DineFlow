# Non-Functional Requirements

Requirements retain their original MoSCoW priorities. The Won't Have section records an exclusion status rather than an additional requirement.

## Must Have

- **NFR-001** — A table reservation request shall be processed within the agreed maximum response time.

- **NFR-002** — A waiter-call notification shall be delivered to restaurant staff within the agreed maximum time.

- **NFR-003** — Booking and payment functionality shall be available 24/7 except during scheduled maintenance.

- **NFR-004** — The system shall prevent double booking of the same table for overlapping time intervals.

- **NFR-005** — Sensitive customer and payment-related information shall be transmitted using encrypted connections.

- **NFR-006** — Restaurant management functionality shall require authenticated and authorized access.

- **NFR-007** — Customer-facing functionality shall be usable on supported modern mobile devices.

- **NFR-008** — Important booking, order and payment operations shall be logged.

## Should Have

- **NFR-009** — Restaurant search results should be returned within the agreed target response time.

- **NFR-010** — Menu content should load within the agreed target response time under normal conditions.

- **NFR-011** — The architecture should support adding new restaurants without redesigning the core system.

## Could Have

- **NFR-012** — Multimedia menu content could dynamically adapt its level of detail to the user's connection quality.

## Won't Have

No confirmed non-functional requirements are excluded from the current release.

## Undefined values

| Requirement | Value to be agreed |
| --- | --- |
| NFR-001 | Maximum reservation response time: **TBD** |
| NFR-002 | Maximum waiter-call delivery time: **TBD** |
| NFR-009 | Target restaurant-search response time: **TBD** |
| NFR-010 | Target menu-load response time and normal conditions: **TBD** |

Supported modern mobile devices (NFR-007), scheduled maintenance arrangements (NFR-003), and any numerical availability target remain unspecified (**TBD**). See the [open questions](open-questions.md).
