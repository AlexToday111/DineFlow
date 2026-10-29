# Sequence Diagram

Status: **Lab 7 scenario documented; design questions remain open.**

## Purpose

This scenario covers table booking, dish pre-ordering, and payment. Participants are the customer, customer application, `BookingService`, `RestaurantTable`, `OrderService`, and `Payment`. Service and entity names correspond to the class model; the application represents the user interface.

## Diagram — Lab 7

![Restaurant Service System sequence diagram](../../assets/diagrams/sequence-diagram.svg)

[Open full-size diagram](../../assets/diagrams/sequence-diagram.svg) · [Editable PlantUML source](../../assets/diagrams/source/sequence-diagram.puml)

## Main flow

1. The customer searches for restaurants and selects a restaurant and table.
2. The application asks `BookingService` to check availability for the requested interval. The service calls `RestaurantTable.isAvailable`.
3. If the table is available, the customer confirms the booking and the application calls `createBooking`.
4. The customer selects dishes and the application calls `OrderService.createPreOrder` for the reservation.
5. The customer confirms payment and the application calls `Payment.initiate`.
6. A successful payment leads to a booking-confirmation message to the customer.

## Alternative outcomes

| Condition | Shown outcome |
| --- | --- |
| Table unavailable | The customer is asked to choose another table. |
| Payment failed | The application displays a payment-failure message. |

## Requirement references

The scenario illustrates restaurant search (FR-001), table selection and booking (FR-004–FR-005), pre-ordering (FR-007), and prepayment (FR-008). It does not show every interaction required to satisfy those requirements.

## Review notes

- Availability checking and booking creation are separate messages. The diagram does not show an atomic recheck or hold to prevent double booking (NFR-004).
- A reservation is created before payment. Its status, expiry, cancellation, or retry behavior following payment failure is unspecified.
- Dish selection is shown as a customer action, but adding order items and calculating the payable amount are omitted.
- Payment-provider interactions and restaurant/POS delivery (FR-009, AC-002, AC-005) are outside the shown flow. `OrderService.sendToPOS` exists in the class model but is not called here.

These items are tracked in the [open UML questions](../requirements/open-questions.md#uml-model-review). The supplied interaction logic is preserved.

## Related documentation

- [Functional requirements](../requirements/functional-requirements.md)
- [Non-functional requirements](../requirements/non-functional-requirements.md)
- [Use cases](../requirements/use-cases.md)
- [Class diagram](class-diagram.md)

This diagram describes one interaction scenario. A full textual use-case specification remains separate work.

[Back to architecture and UML](README.md)
