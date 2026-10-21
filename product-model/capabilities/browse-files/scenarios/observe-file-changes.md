---
kind: edge
routes:
  desktop: Windows desktop
steps:
- text: A watched location changes while it is being used.
  kind: condition
  entities: []
  contexts:
    desktop:
      place: desktop::files
  unattended: true
- text: The folder listing and file metadata reflect the change; workspace selection follows observed renames and drops paths that disappeared.
  kind: product
  entities:
  - entity: folder
    effect: changes
    facts:
    - Contents
    - Listing status
  - entity: file
    effect: changes
    facts:
    - Name
    - Path
    - Size
    - Modified
  - entity: workspace
    effect: changes
    facts:
    - Selection
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/ViewAllViewModel.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/Watch/ChangeHub.cs
---

# Follow changes on disk

## Trigger

A watched location changes while it is being used.

## Outcome

The folder listing and file metadata reflect the change; workspace selection follows observed renames and drops paths that disappeared.
