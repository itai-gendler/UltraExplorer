---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Begin the requested path choice.
  kind: actor
  entities: []
  contexts:
    desktop:
      place: desktop::picker
  actor: user
- text: A dialog request starts pending with the caller’s mode, name, options and initial location; the workspace opens that location.
  kind: product
  entities:
  - entity: dialog-request
    effect: creates
    facts:
    - Mode
    - Initial location
    - File types
    - Filename
    - Options
    - Application options
    - Result paths
    - Caller decision
    - Interaction
    - Origin
    to: Pending
  - entity: workspace
    effect: changes
    facts:
    - Locations
  contexts:
    desktop:
      place: desktop::picker
  actor: user
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

# Receive a new file-choice request

## Trigger

A documented caller request or supported enabled native dialog starts a new choice.

## Outcome

A dialog request starts pending with the caller’s mode, name, options and initial location; the workspace opens that location.
