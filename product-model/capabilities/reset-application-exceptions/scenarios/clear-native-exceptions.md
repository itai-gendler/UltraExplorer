---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Reset exceptions.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::windows-settings
- text: The saved application exception entries are removed.
  kind: product
  entities:
  - entity: application-exception
    effect: removes
  actor: user
  contexts:
    desktop:
      place: desktop::windows-settings
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Picker/Integration/DialogIntegrationController.cs
---

# Reset native application exceptions

## Trigger

The person requests Reset exceptions.

## Outcome

The saved application exception entries are removed.
