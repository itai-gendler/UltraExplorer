---
kind: edge
routes:
  desktop: Windows desktop
steps:
- text: Select an entry, then inspect another location.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::picker
- text: The dialog request retains the chosen file’s full path while the person navigates elsewhere; clearing it or typing a new filename replaces that pending choice.
  kind: product
  entities:
  - entity: dialog-request
    effect: changes
    facts:
    - Filename
    - Interaction
  - entity: workspace
    effect: changes
    facts:
    - Locations
  - entity: file
    effect: reads
    facts:
    - Path
  actor: user
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
- kind: code
  role: implementation
  target: src/UltraExplorer/Picker/FileDialogValidator.cs
---

# Retain an exact pending file choice

## Trigger

A native Open request has a pending file selection.

## Outcome

The dialog request retains the chosen file’s full path while the person navigates elsewhere; clearing it or typing a new filename replaces that pending choice.
