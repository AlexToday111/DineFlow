# Architecture and UML

Status: **Preliminary design documentation.** The Lab 6 class model and Lab 7 sequence diagram are available as editable PlantUML sources and rendered SVG images. Design questions remain open.

## Diagram index

| Diagram | Purpose | Status |
| --- | --- | --- |
| [Use-case diagram](../requirements/use-cases.md) | Shows actors and system capabilities | Existing image available; textual scenarios pending |
| [Class diagram](class-diagram.md) | Describes the system's classes and relationships | Lab 6 source and SVG available |
| [Sequence diagram](sequence-diagram.md) | Shows interactions during booking, pre-ordering, and payment | Lab 7 source and SVG available |

Read the use-case diagram for the user-facing scope, the class model for structure, and the sequence diagram for interactions in a specific scenario.

## Scope and open decisions

The [architectural constraints](../requirements/architectural-constraints.md) guide future architecture work. The technology stack, deployment infrastructure, API contracts, and architectural patterns remain unspecified. UML models describe proposed designs rather than implemented functionality.

The supplied UML logic is preserved. The generated class-model SVG is the primary illustration; the previously stored PNG export remains linked for reference. Model gaps and differences from requirements are recorded in the [open UML questions](../requirements/open-questions.md#uml-model-review).

## Maintaining diagrams

Editable PlantUML files are stored in [assets/diagrams/source](../../assets/diagrams/source/), with rendered SVG images in [assets/diagrams](../../assets/diagrams/). Each diagram page includes its image, a source link, a short explanation, and relevant requirement references.

See the [diagram file guide](../../assets/diagrams/source/README.md) for filenames, rendering commands, and update steps.

[Back to project documentation](../../README.md#documentation)
