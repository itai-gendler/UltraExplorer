---
kind: edge
routes:
  desktop: Windows desktop
steps:
- text: The launched installation reports that it did not complete.
  kind: condition
  entities: []
  contexts:
    desktop:
      place: desktop::files
  unattended: true
- text: The update returns to ready with the installation failure available for review.
  kind: product
  entities:
  - entity: update
    effect: changes
    facts:
    - Failure
    from: Installing
    to: Ready
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.Updates.cs
---

# Restore a failed installation offer

## Trigger

The launched installation reports that it did not complete.

## Outcome

The update returns to ready with the installation failure available for review.
