# Architecture and UML

Status: **Preliminary design documentation.** An existing class diagram is available. Pages are prepared for the detailed class model and sequence diagram; their new sources and images are pending.

## Diagram index

| Diagram | Purpose | Status |
| --- | --- | --- |
| [Use-case diagram](../requirements/use-cases.md) | Shows actors and system capabilities | Existing image available; textual scenarios pending |
| [Class diagram](class-diagram.md) | Describes the system's classes and relationships | Existing image available; detailed Lab 6 source pending |
| [Sequence diagram](sequence-diagram.md) | Shows interactions during booking, pre-ordering, and payment | Lab 7 source and image pending |

Read the use-case diagram for the user-facing scope, the class model for structure, and the sequence diagram for interactions in a specific scenario.

## Scope and open decisions

The [architectural constraints](../requirements/architectural-constraints.md) guide future architecture work. The technology stack, deployment infrastructure, API contracts, and architectural patterns remain unspecified. UML models describe proposed designs rather than implemented functionality.

When the new UML code is supplied, the detailed class model will be compared with the existing image before deciding whether it replaces or supplements that model. Any differences from requirements will be recorded in the [open questions](../requirements/open-questions.md).

## Maintaining diagrams

Editable PlantUML files will be stored in [assets/diagrams/source](../../assets/diagrams/source/), with rendered SVG images in [assets/diagrams](../../assets/diagrams/). Each diagram page will include its image, a source link, a short explanation, and relevant requirement references.

See the [diagram file guide](../../assets/diagrams/source/README.md) for the planned filenames and update steps.

[Back to project documentation](../../README.md#documentation)
