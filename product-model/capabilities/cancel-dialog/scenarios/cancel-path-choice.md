---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Cancel the dialog.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::picker
- text: The dialog request becomes cancelled with no accepted result paths.
  kind: product
  entities:
  - entity: dialog-request
    effect: changes
    facts:
    - Result paths
    from: Pending
    to: Cancelled
  actor: user
  contexts:
    desktop:
      place: desktop::picker
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.Picker.cs
---

# Cancel the pending choice

## Trigger

A file choice is pending.

## Outcome

The dialog request becomes cancelled with no accepted result paths.
