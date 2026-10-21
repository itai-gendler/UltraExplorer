---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Choose Always use Windows for this program.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::picker
- text: An application exception is retained and the pending dialog request returns to Windows.
  kind: product
  entities:
  - entity: application-exception
    effect: creates
    facts:
    - Application
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

# Keep this application native

## Trigger

The person chooses Always use Windows for this application.

## Outcome

An application exception is retained and the pending dialog request returns to Windows.
