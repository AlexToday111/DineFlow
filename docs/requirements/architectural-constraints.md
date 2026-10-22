# Architectural Constraints

The original modal verbs are preserved: “must” identifies mandatory constraints; “should” identifies recommendations. Integration is conditional where the source says “where required”.

- **AC-001** — The system must be able to integrate with existing restaurant automation/POS systems where required.

- **AC-002** — Payment card processing should be delegated to a certified external payment provider rather than storing raw card details in the application.

- **AC-003** — The customer-facing functionality must be accessible from smartphones.

- **AC-004** — The architecture must support multiple restaurants as separate business entities.

- **AC-005** — The system must exchange booking, order and table-availability information with restaurant-side systems.

- **AC-006** — External integrations should be isolated from the core business logic so that different restaurant systems can be supported.

These constraints do not select a technology stack or identify specific integration partners. See the [open questions](open-questions.md) and [architecture documentation](../architecture/README.md).
