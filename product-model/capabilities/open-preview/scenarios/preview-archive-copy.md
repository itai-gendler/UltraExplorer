---
kind: edge
routes:
  desktop: Windows desktop
steps:
- text: Open Quick Look for the entry.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: An extracted archive entry is presented as a read-only preview with its origin; passive hover does not extract it.
  kind: product
  entities:
  - entity: archive-entry
    effect: reads
    facts: &id001
    - Path
    - Name
    - Kind
    - Size
    - Origin
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The archive entry can be inspected at Quick Look.
  kind: product
  entities:
  - entity: archive-entry
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

# Inspect an archive entry

## Trigger

Archive browsing is enabled and the person explicitly requests Quick Look on an entry.

## Outcome

An extracted archive entry is presented as a read-only preview with its origin; passive hover does not extract it.
