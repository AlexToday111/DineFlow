# Diagram Sources

This directory is prepared for editable PlantUML sources. The new UML code has not yet been added.

## Planned files

Paths below are relative to the repository root.

| Diagram | PlantUML source | Rendered image | Documentation |
| --- | --- | --- | --- |
| Detailed class model — Lab 6 | `assets/diagrams/source/class-diagram.puml` | `assets/diagrams/class-diagram.svg` | [Class diagram](../../../docs/architecture/class-diagram.md) |
| Interaction scenario — Lab 7 | `assets/diagrams/source/sequence-diagram.puml` | `assets/diagrams/sequence-diagram.svg` | [Sequence diagram](../../../docs/architecture/sequence-diagram.md) |

The existing PNG diagrams in the parent directory remain available. Their editable sources are not currently present in this repository.

## Update workflow

1. Add or edit the corresponding `.puml` source.
2. Render the source to SVG using PlantUML and save the result under the matching image filename.
3. Inspect the rendered image for readable labels, complete content, and clear relationships.
4. Update the diagram page with the image, source link, explanation, and relevant requirement IDs.
5. Check consistency with requirements and other diagrams. Record unresolved differences in the open questions.
6. Commit the source, rendered image, and documentation together.

Do not edit rendered images independently of their sources. If a model replaces an existing diagram, identify the previous version explicitly and update all affected links.

[Back to architecture and UML](../../../docs/architecture/README.md)
