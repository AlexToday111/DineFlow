# DineFlow

A planned restaurant platform for table reservations, food pre-orders, payments, and personalized recommendations.

**Project status: Design and documentation.** The repository currently contains project documentation and preliminary UML diagrams. Implementation has not started in this repository.

## Problem

Restaurant customers face long waits, difficulty finding a waiter, slow service, and poor service quality. DineFlow aims to help customers plan visits and access restaurant services through their smartphones.

## Core platform capabilities

- Find restaurants by dishes, price, distance, and other supported parameters.
- View floor plans, select tables, and reserve a date and time.
- Browse menus, pre-order dishes, and prepay for a planned visit.
- Call a waiter and pay the bill by phone inside the restaurant.
- Support staff in managing reservations, pre-orders, and waiter calls.
- Provide preference profiles and personalized recommendations, subject to the documented priorities.

## Documentation

Start with the project overview, then read the requirements and UML models.

| Section | Contents | Status |
| --- | --- | --- |
| [Project overview](docs/overview.md) | Problem, objectives, and user roles | Documented |
| [Functional requirements](docs/requirements/functional-requirements.md) | Platform capabilities and MoSCoW priorities | Documented; some details remain open |
| [Non-functional requirements](docs/requirements/non-functional-requirements.md) | Quality requirements and values to be agreed | Documented; numerical targets are TBD |
| [Architectural constraints](docs/requirements/architectural-constraints.md) | Integration and platform constraints | Documented |
| [Use cases](docs/requirements/use-cases.md) | Existing use-case diagram and specification template | Diagram available; textual scenarios pending |
| [Architecture and UML](docs/architecture/README.md) | Diagram index, class model, and interaction scenario | Lab 6 and Lab 7 sources and images available; design questions remain open |
| [Open stakeholder questions](docs/requirements/open-questions.md) | Unresolved scope, business rules, and quality targets | Awaiting answers |
| [Development approach](docs/development/methodology.md) | Rapid Prototyping and Scrum | Planned approach |

Requirement IDs (`FR`, `NFR`, and `AC`) provide stable references. The requirement documents define scope and MoSCoW priorities; diagram elements alone do not add approved requirements.

## Laboratory materials

The [source Google document](https://docs.google.com/document/d/1uYLRcOJxa0YR9Lsh4C2f--5P2zQ14fUCAJ1MeqVXjpA/edit) groups the materials by laboratory work. This repository organizes them by subject.

| Source section | Repository location |
| --- | --- |
| Topic | [Project overview](docs/overview.md) |
| Lab 2 — stakeholder questions | [Open questions](docs/requirements/open-questions.md) |
| Lab 3 — requirements and constraints | [Functional requirements](docs/requirements/functional-requirements.md), [non-functional requirements](docs/requirements/non-functional-requirements.md), and [architectural constraints](docs/requirements/architectural-constraints.md) |
| Lab 4 — use-case diagram | [Use cases](docs/requirements/use-cases.md) |
| Lab 5 — lifecycle and methodology | [Development approach](docs/development/methodology.md) |
| Lab 6 — detailed class diagram | [Class model](docs/architecture/class-diagram.md) with PlantUML source and SVG |
| Lab 7 — sequence diagram | [Booking, pre-order, and payment scenario](docs/architecture/sequence-diagram.md) with PlantUML source and SVG |

## Repository structure

```text
docs/
  overview.md                 Project context and objectives
  requirements/               Requirements, use cases, and open questions
  architecture/               UML index and diagram explanations
  development/                Lifecycle and methodology
assets/
  diagrams/                   Diagram images
    source/                   Editable PlantUML sources
```

See the [diagram file guide](assets/diagrams/source/README.md) for naming and update conventions.
