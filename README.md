# DineFlow

A planned restaurant platform that helps customers choose a restaurant, reserve a table, pre-order dishes, request waiter assistance, and pay by phone.

**Project status: Design and documentation.** This repository contains a Software Engineering specification and proposed UML models. It does not contain an implemented application or claim completed integrations.

## Problem

Planning a restaurant visit can involve uncertain table availability and waiting. During the visit, customers may struggle to find a waiter or settle the bill promptly. DineFlow connects visit planning with restaurant staff workflows through a smartphone-accessible experience.

## Main user roles

- **Customer:** discover restaurants, book, pre-order, pay, and call a waiter.
- **Waiter:** receive customer-call notifications; acknowledgement/resolution and relevant pre-order read access are proposed workflow details.
- **Manager:** proposed owner of restaurant-scoped reservation/pre-order management. One employee may hold both Waiter and Manager roles in a restaurant; each role's permissions remain distinct.

Payment Provider and Restaurant/POS are external collaborators. The [overview](docs/overview.md) defines their boundaries, and the [permission matrix](docs/requirements/functional-requirements.md#proposed-staff-permissions) separates recorded staff scope from proposed role allocation.

## Core platform capabilities and release scope

| Scope | Recorded requirements | Planning interpretation |
| --- | --- | --- |
| Candidate MVP / Must Have | Restaurant discovery and filtering; information, floor plans and menus; reservations; pre-orders and prepayment; restaurant handoff; waiter calls; bill payment; staff reservation/pre-order management (FR-001–FR-014) | Baseline release capabilities; detailed acceptance rules still need validation |
| Later candidates / Should Have | Current occupancy, adaptive menus, activity/history, profiles, recommendations, reservation/pre-order changes (FR-015–FR-021) | Retain their recorded priority; deadlines and detailed rules remain TBD |
| Optional candidates / Could Have | Average occupancy, dish advice, additional in-restaurant ordering, favorites, feedback (FR-022–FR-026) | Include only when selected for a release |
| Excluded initially / Won't Have | Customer blacklist management (FR-027) | No initial-release staff permission or workflow |

This is a candidate MVP based on the recorded priorities, not a newly approved release commitment. A prototype may simulate providers or a subset of interactions; that does not remove Must Have requirements from the intended release. Multiple restaurants are required by AC-004. The proposed audience is table-service restaurants; the [P-SCALE pilot envelope](docs/overview.md#target-businesses-and-planning-scale) gives explicit unapproved planning counts and workload. International rollout is not established.

## Documentation

Read the overview, requirements, use cases, class models, and interaction scenarios in that order.

| Section | Contents | Status |
| --- | --- | --- |
| [Project overview](docs/overview.md) | Problem, roles, workflows, and boundaries | Design context |
| [Functional requirements](docs/requirements/functional-requirements.md) | FR baseline, acceptance checks, proposed states and permissions | Original IDs/priorities preserved; policies proposed/TBD |
| [Non-functional requirements](docs/requirements/non-functional-requirements.md) | NFR baseline and measurement/reliability plan | Numerical targets/workload TBD |
| [Architectural constraints](docs/requirements/architectural-constraints.md) | Mandatory constraints, recommendations, integration boundaries | Technology/authority decisions open |
| [Use cases](docs/requirements/use-cases.md) | Four role-based diagrams and UC-01–UC-08 specifications | Recorded capabilities with labelled refinements |
| [Architecture and UML](docs/architecture/README.md) | General/focused class models and four scoped sequences | Proposed design; 12 editable diagrams |
| [Open stakeholder questions](docs/requirements/open-questions.md) | Decision and proposal register | No new stakeholder approval inferred |
| [Development approach](docs/development/methodology.md) | Practical Rapid Prototyping/Scrum plan and candidate acceptance/DoD | Planned work |

FR, NFR, and AC identifiers remain stable. The existing requirements are the recorded baseline; diagram detail does not independently create an approved requirement. Proposed policies use P-IDs, and unresolved decisions use D-IDs.

## Laboratory materials

The [source Google document](https://docs.google.com/document/d/1uYLRcOJxa0YR9Lsh4C2f--5P2zQ14fUCAJ1MeqVXjpA/edit) groups materials by laboratory work. This repository organizes them by subject; the new views explicitly refine or replace earlier diagrams.

| Source section | Repository location |
| --- | --- |
| Topic | [Project overview](docs/overview.md) |
| Lab 2 — stakeholder questions | [Decision register](docs/requirements/open-questions.md) |
| Lab 3 — requirements and constraints | [Functional](docs/requirements/functional-requirements.md), [non-functional](docs/requirements/non-functional-requirements.md), and [architectural](docs/requirements/architectural-constraints.md) requirements |
| Lab 4 — use-case diagram | [Overview and Customer/Waiter/Manager views](docs/requirements/use-cases.md) |
| Lab 5 — lifecycle and methodology | [Development approach](docs/development/methodology.md) |
| Lab 6 — class diagram | [Domain overview and focused class models](docs/architecture/class-diagram.md) |
| Lab 7 — sequence diagram | [Reservation, pre-order/checkout exit, payment, and waiter-call scenarios](docs/architecture/sequence-diagram.md) |

## Repository structure

```text
docs/
  overview.md                 Project context and boundaries
  requirements/               Baseline, acceptance checks, use cases, decisions
  architecture/               UML index, class models, interaction explanations
  development/                Planned lifecycle and methodology
assets/
  diagrams/                   Current SVGs and source-linked PNG exports
    source/                   Editable PlantUML sources and rendering guide
```

See the [diagram source guide](assets/diagrams/source/README.md) for source/image pairs and rendering commands. Current SVGs replace outdated views. The two existing PNGs are regenerated from maintained sources, so no published diagram is image-only.
