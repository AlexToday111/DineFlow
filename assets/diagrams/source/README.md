# Diagram Sources

This directory contains the editable PlantUML sources supplied for Lab 6 and Lab 7. Chat attribution lines were removed; UML logic is preserved.

## Files

Paths below are relative to the repository root.

| Diagram | PlantUML source | Rendered image | Documentation |
| --- | --- | --- | --- |
| Detailed class model — Lab 6 | [class-diagram.puml](class-diagram.puml) | [class-diagram.svg](../class-diagram.svg) | [Class diagram](../../../docs/architecture/class-diagram.md) |
| Interaction scenario — Lab 7 | [sequence-diagram.puml](sequence-diagram.puml) | [sequence-diagram.svg](../sequence-diagram.svg) | [Sequence diagram](../../../docs/architecture/sequence-diagram.md) |

The existing PNG exports in the parent directory remain available for reference. The earlier use-case image has no editable source in this repository.

## Rendering

The SVG files were generated locally with Java 21 and PlantUML 1.2025.2. Smetana provides class layout without a separate Graphviz installation. From the repository root, use a local PlantUML JAR:

```powershell
java -jar /path/to/plantuml-1.2025.2.jar -charset UTF-8 -Playout=smetana -tsvg -o .. assets/diagrams/source/class-diagram.puml assets/diagrams/source/sequence-diagram.puml
```

Replace the JAR path with its location on your machine. Output goes to `assets/diagrams/`. The PlantUML binary is not stored in this repository.

## Update workflow

1. Add or edit the corresponding `.puml` source.
2. Render the source to SVG using PlantUML and save the result under the matching image filename.
3. Inspect the rendered image for readable labels, complete content, and clear relationships.
4. Update the diagram page with the image, source link, explanation, and relevant requirement IDs.
5. Check consistency with requirements and other diagrams. Record unresolved differences in the open questions.
6. Commit the source, rendered image, and documentation together.

Do not edit rendered images independently of their sources. If a model replaces an existing diagram, identify the previous version explicitly and update all affected links.

[Back to architecture and UML](../../../docs/architecture/README.md)
