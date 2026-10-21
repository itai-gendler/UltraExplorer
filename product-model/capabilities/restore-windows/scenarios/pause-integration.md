---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Restore and pause.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::windows-settings
- text: The settings disable general Windows integration and restore native dialogs while retaining the Win E choice.
  kind: product
  entities:
  - entity: settings
    effect: changes
    facts:
    - Windows integration
  actor: user
  contexts:
    desktop:
      place: desktop::windows-settings
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Picker/Integration/DialogIntegrationController.cs
---

# Restore Windows and pause integration

## Trigger

The person requests Restore and pause.

## Outcome

The settings disable general Windows integration and restore native dialogs while retaining the Win E choice.
