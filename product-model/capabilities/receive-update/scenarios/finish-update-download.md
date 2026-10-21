---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: The prepared download has completed its validation.
  kind: condition
  entities: []
  contexts:
    desktop:
      place: desktop::files
  unattended: true
- text: The update becomes ready for the person to review and explicitly install.
  kind: product
  entities:
  - entity: update
    effect: changes
    facts:
    - Package
    - Progress
    from: Downloading
    to: Ready
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/Updates/QuietUpdateService.cs
---

# Offer a prepared release

## Trigger

The prepared download has completed its validation.

## Outcome

The update becomes ready for the person to review and explicitly install.
