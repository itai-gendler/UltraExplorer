---
kind: edge
routes:
  desktop: Windows desktop
steps:
- text: Complete the choice.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::picker
- text: The picker preferences are created with the caller identity and the accepted location, type and recent names.
  kind: product
  entities:
  - entity: picker-preferences
    effect: creates
    facts:
    - Caller
    - Last folder
    - File type
    - Recent names
  - entity: dialog-request
    effect: reads
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

# Remember a caller’s accepted choice

## Trigger

An identified caller allows remembered choices.

## Outcome

The picker preferences are created with the caller identity and the accepted location, type and recent names.

## Edge cases

- Later choices for the same identity update its existing preferences.
- State-storage failure does not fail an otherwise valid file choice.
