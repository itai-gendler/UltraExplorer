---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Open Quick Look.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The file contents are presented for inspection, with document-page or media controls appropriate to its type.
  kind: product
  entities:
  - entity: file
    effect: reads
    facts: &id001
    - Name
    - Path
    - Size
    - Modified
    - Type
    - Content
    - Hidden
    - Read only
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The person can inspect the file at Quick Look.
  kind: product
  entities:
  - entity: file
    effect: reads
    facts: *id001
  actor: user
  contexts:
    desktop:
      place: desktop::preview
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/QuickPreviewWindow.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.HoverPreview.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.ArchivePreview.cs
---

# Inspect a selected file

## Trigger

The person requests Quick Look for a selected file.

## Outcome

The file contents are presented for inspection, with document-page or media controls appropriate to its type.

## Edge cases

- Hover previews provide passive inspection when enabled.
- An unavailable provider or unsupported content displays a failure or fallback while external Open remains available.
