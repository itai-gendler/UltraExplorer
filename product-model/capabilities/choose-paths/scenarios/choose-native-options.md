---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Set the application-specific options.
  kind: actor
  actor: user
  entities: []
  contexts:
    desktop:
      place: desktop::picker
- text: The dialog request carries the changed application options.
  kind: product
  actor: user
  entities:
  - entity: dialog-request
    effect: changes
    facts:
    - Application options
  contexts:
    desktop:
      place: desktop::picker
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.NativeProxy.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/Picker/Integration/NativeDialogProxy.cs
---

# Carry application options with a choice

## Trigger

A supported native dialog offers extra application options.

## Outcome

The chosen options are reflected in the original dialog before the calling application evaluates its answer.
