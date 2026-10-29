# Diagram Sources

Status: **Proposed design.** The sources model the recorded requirements plus explicitly labelled design proposals. They are not executable application functionality.

## Files

All 12 current SVGs are generated from the matching editable source in this directory. Paths are relative to this guide.

| View | Source | Rendering |
| --- | --- | --- |
| General use cases | [use-case-general.puml](use-case-general.puml) | [use-case-general.svg](../use-case-general.svg) |
| Customer use cases | [use-case-customer.puml](use-case-customer.puml) | [use-case-customer.svg](../use-case-customer.svg) |
| Waiter use cases | [use-case-waiter.puml](use-case-waiter.puml) | [use-case-waiter.svg](../use-case-waiter.svg) |
| Manager use cases | [use-case-manager.puml](use-case-manager.puml) | [use-case-manager.svg](../use-case-manager.svg) |
| General domain | [class-diagram.puml](class-diagram.puml) | [class-diagram.svg](../class-diagram.svg) |
| Booking/reservation | [booking-class-diagram.puml](booking-class-diagram.puml) | [booking-class-diagram.svg](../booking-class-diagram.svg) |
| Ordering/payment | [ordering-class-diagram.puml](ordering-class-diagram.puml) | [ordering-class-diagram.svg](../ordering-class-diagram.svg) |
| Staff/operations | [staff-class-diagram.puml](staff-class-diagram.puml) | [staff-class-diagram.svg](../staff-class-diagram.svg) |
| Table reservation | [sequence-diagram.puml](sequence-diagram.puml) | [sequence-diagram.svg](../sequence-diagram.svg) |
| Pre-order creation / checkout exit | [preorder-payment-sequence.puml](preorder-payment-sequence.puml) | [preorder-payment-sequence.svg](../preorder-payment-sequence.svg) |
| Payment outcomes | [payment-sequence.puml](payment-sequence.puml) | [payment-sequence.svg](../payment-sequence.svg) |
| Waiter call | [waiter-call-sequence.puml](waiter-call-sequence.puml) | [waiter-call-sequence.svg](../waiter-call-sequence.svg) |

Use-case explanations are in [use-cases.md](../../../docs/requirements/use-cases.md); class/interaction explanations and traceability are in the [architecture index](../../../docs/architecture/README.md).

The earlier combined models are explicitly replaced by the current focused views. There are twelve scenarios/views, not separate duplicated PNG models.

The two pre-existing image-only PNG exports are now regenerated from canonical editable sources:

| PNG rendering | Maintained source |
| --- | --- |
| [restaurant-service-class-diagram.png](../restaurant-service-class-diagram.png) | [class-diagram.puml](class-diagram.puml) |
| [restaurant-service-use-case-diagram.png](../restaurant-service-use-case-diagram.png) | [use-case-general.puml](use-case-general.puml) |

These current exports replace the former image-only snapshots. Every published diagram format has a source link; SVG is the primary scalable rendering.

## Rendering

The current SVGs are generated locally using Java 21 and PlantUML 1.2025.2. Class sources explicitly select Smetana layout. Use-case diagrams use the available Graphviz 2.44.1 layout, which correctly attaches actor associations to the use-case boundaries. Sequence layout is handled by PlantUML. From the repository root, set the JAR path to its location on your machine:

```powershell
$plantUmlJar = 'C:/path/to/plantuml-1.2025.2.jar'
java -jar $plantUmlJar -charset UTF-8 -checkonly 'assets/diagrams/source/*.puml'
java -jar $plantUmlJar -charset UTF-8 -tsvg -o .. 'assets/diagrams/source/*.puml'
```

Run `java -jar $plantUmlJar -testdot` to check Graphviz availability before rendering use cases. The JAR and Graphviz binary are not stored in the repository. The output directory is relative to each source, so SVGs are written to the existing `assets/diagrams/` directory. No external diagram-hosting service is needed.

To refresh the two PNG formats, render the canonical files into a temporary preview directory and copy the results to the existing PNG filenames:

```powershell
$diagramPreviewDir = Join-Path $env:TEMP 'dineflow-diagram-preview'
New-Item -ItemType Directory -Path $diagramPreviewDir -Force | Out-Null
java -jar $plantUmlJar -charset UTF-8 -tpng -o $diagramPreviewDir assets/diagrams/source/class-diagram.puml assets/diagrams/source/use-case-general.puml
Copy-Item -LiteralPath (Join-Path $diagramPreviewDir 'class-diagram.png') -Destination assets/diagrams/restaurant-service-class-diagram.png -Force
Copy-Item -LiteralPath (Join-Path $diagramPreviewDir 'use-case-general.png') -Destination assets/diagrams/restaurant-service-use-case-diagram.png -Force
```

## Update workflow

1. Edit the source and identify affected FR/NFR/AC IDs and P-/D-IDs.
2. Preserve recorded priorities. Mark new policies as proposals until a decision record establishes approval.
3. Validate syntax and regenerate the corresponding SVG.
4. Visually inspect labels, multiplicities, branch conditions, and line crossings at readable zoom.
5. Review related prose/use cases and other diagrams for consistent names, service operations, permissions, and states.
6. Check all local document/source/image links and record validation limitations.
7. Commit source, SVG, and existing documentation changes together when requested.

Use ordinary associations unless lifetime ownership is meaningful; use composition for pre-order-owned items. Use include only for required sub-behavior, not page navigation or diagram hierarchy. Sequence fragments represent conditions/repetition, not approved retry counts. State definitions belong to the [proposed lifecycle model](../../../docs/requirements/functional-requirements.md#proposed-lifecycle-model).

[Back to architecture and UML](../../../docs/architecture/README.md)
