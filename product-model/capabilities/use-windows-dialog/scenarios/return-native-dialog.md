---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Choose Use the Windows dialog this time.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::picker
- text: The original Windows dialog is restored with the dialog request still pending and its current choices available.
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
  target: src/UltraExplorer/Picker/Integration/NativeDialogProxy.cs#UseWindows
---

# Continue with Windows this time

## Trigger

The person is using an integrated native dialog.

## Outcome

The original Windows dialog is restored with the dialog request still pending and its current choices available.
