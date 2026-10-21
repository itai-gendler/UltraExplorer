---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Choose one or more entries.
  kind: actor
  actor: user
  entities: []
  contexts:
    desktop:
      place: desktop::picker
- text: The workspace selection and the pending dialog request use the chosen paths.
  kind: product
  actor: user
  entities:
  - entity: workspace
    effect: changes
    facts:
    - Selection
  - entity: dialog-request
    effect: changes
    facts:
    - Filename
    - Interaction
  contexts:
    desktop:
      place: desktop::picker
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.Selection.cs#ConfigurePickerSelection
- kind: code
  role: implementation
  target: src/UltraExplorer/Picker/FileDialogSession.cs
---

# Select paths in a file dialog

## Trigger

The caller’s selection requirements have been loaded.

## Outcome

The workspace selection follows the chosen paths within the caller’s single- or multiple-selection requirement.
