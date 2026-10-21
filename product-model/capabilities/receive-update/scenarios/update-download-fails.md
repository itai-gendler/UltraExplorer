---
kind: edge
routes:
  desktop: Windows desktop
steps:
- text: A download or preparation cannot finish.
  kind: condition
  entities: []
  contexts:
    desktop:
      place: desktop::files
  unattended: true
- text: The update enters failed state quietly; a previously ready package remains available when one exists.
  kind: product
  entities:
  - entity: update
    effect: changes
    facts:
    - Failure
    from: Downloading
    to: Failed
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/Updates/QuietUpdateService.cs
---

# Handle an unavailable update

## Trigger

A download or preparation cannot finish.

## Outcome

The update enters failed state quietly; a previously ready package remains available when one exists.
