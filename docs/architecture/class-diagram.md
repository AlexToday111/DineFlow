# Class Diagram

Status: **Lab 6 model documented; design questions remain open.**

## Purpose

The class model describes system entities, responsibilities, and relationships in four groups: Users & Staff, Restaurant & Menu, Reservations & Ordering, and Personalization.

## Detailed model — Lab 6

![Restaurant Service System class diagram](../../assets/diagrams/class-diagram.svg)

[Open full-size diagram](../../assets/diagrams/class-diagram.svg) · [Editable PlantUML source](../../assets/diagrams/source/class-diagram.puml)

The diagram is wide; open the SVG separately and zoom in to read members and relationship labels.

## Model structure

| Group | Responsibilities |
| --- | --- |
| Users & Staff | `User` provides common account operations. `Customer` and `RestaurantStaff` specialize it; `Waiter` and `Manager` specialize restaurant staff. |
| Restaurant & Menu | `Restaurant`, `FloorPlan`, and `RestaurantTable` describe the venue and tables. `Menu` and `MenuItem` describe dishes and prices. |
| Reservations & Ordering | `Reservation`, `PreOrder`, `OrderItem`, and `Payment` describe a planned visit and payment. `BookingService` and `OrderService` coordinate operations; `WaiterCall` represents a customer request. |
| Personalization | `ActivityLog`, `PreferenceProfile`, and `Recommendation` describe recorded activity and personalized suggestions. |

Inheritance distinguishes user roles. Composition expresses ownership of floor plans, order items, and preference profiles; aggregation connects restaurants to staff and menus to dishes. Associations include multiplicities, while dependencies show temporary use by services. Notes illustrate `in`, `out`, and `inout` parameter directions.

## Requirement references

These references show intended coverage, not proof of complete satisfaction.

| Model area | Related requirements |
| --- | --- |
| Restaurant search, information, floor plans, and booking | FR-001–FR-005, FR-009, FR-012 |
| Menus, pre-orders, and payments | FR-006–FR-008, FR-011, FR-013 |
| Waiter calls | FR-010, FR-014 |
| Occupancy and adaptive menu media | FR-015, FR-016 |
| Activity, profiles, and recommendations | FR-017–FR-019 |
| Reservation changes | FR-020; the deadline remains TBD |
| Restaurant integration and separation | AC-001, AC-004–AC-006 |

## Review notes

- `POSIntegration` is referenced by a realization relationship but is not explicitly declared as an interface or given operations. PlantUML creates an implicit class for it; the intended contract needs clarification.
- Loyalty points, discounts, tax calculations, and cancellation operations appear without dedicated requirements. Their inclusion and rules need confirmation.
- The model does not demonstrate atomic booking, restaurant data isolation, authorization, or payment-provider delegation. These constraints require further design detail.

These items are tracked in the [open UML questions](../requirements/open-questions.md#uml-model-review).

## Earlier image

The [previously stored PNG export](../../assets/diagrams/restaurant-service-class-diagram.png) is retained for reference. The SVG above is generated from the supplied editable Lab 6 source and is the primary illustration on this page.

## Related documentation

- [Functional requirements](../requirements/functional-requirements.md)
- [Architectural constraints](../requirements/architectural-constraints.md)
- [Sequence diagram](sequence-diagram.md)

Model elements do not establish additional approved requirements or implementation decisions.

[Back to architecture and UML](README.md)
