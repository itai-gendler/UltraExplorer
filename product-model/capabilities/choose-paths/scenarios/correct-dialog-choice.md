---
kind: validation
routes:
  desktop: Windows desktop
steps:
- text: Submit the proposed choice.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::picker
- text: The dialog request stays pending and the reason is shown so its filename or location can be corrected.
  kind: product
  entities:
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

# Correct an invalid or rejected choice

## Trigger

A proposed choice does not meet the current request.

## Outcome

The dialog request stays pending and the reason is shown so its filename or location can be corrected.

## Edge cases

- Required existence and selected-type checks are applied.
- A caller rejecting the answer leaves the dialog open.
- Cancelling an overwrite or creation confirmation does not accept the request.
