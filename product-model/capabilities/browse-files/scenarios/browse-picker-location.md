---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Navigate to a location or enter a wildcard name.
  kind: actor
  actor: user
  entities: []
  contexts:
    desktop:
      place: desktop::picker
- text: The workspace reaches the location and the dialog request uses the current name filter.
  kind: product
  actor: user
  entities:
  - entity: workspace
    effect: changes
    facts:
    - Locations
    - Camera
    - History
    - Filter
  - entity: dialog-request
    effect: changes
    facts:
    - Filename
    - File types
    - Interaction
  - entity: folder
    effect: reads
    facts:
    - Path
    - Contents
    - Listing status
  contexts:
    desktop:
      place: desktop::picker
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.Picker.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/Picker/FileDialogSession.cs
---

# Browse during an application choice

## Trigger

A path choice is in progress.

## Outcome

The workspace and dialog request follow the selected location and caller-provided type filtering; directories remain available for navigation.
