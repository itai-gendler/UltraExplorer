---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Choose the desired values.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::about
- text: The settings retain the chosen values and apply them without a separate Save action.
  kind: product
  entities:
  - entity: settings
    effect: changes
    facts:
    - Receive updates
  actor: user
  contexts:
    desktop:
      place: desktop::about
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/SettingsViewModel.cs
---

# Change a preference in About

## Trigger

The person changes a preference in this section.

## Outcome

The settings retain the chosen values and apply them without a separate Save action.

## Edge cases

- A preference-save failure is reported.
