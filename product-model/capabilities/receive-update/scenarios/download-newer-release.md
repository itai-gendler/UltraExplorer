---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Enabled release discovery finds a newer supported release.
  kind: condition
  entities:
  - entity: settings
    effect: reads
    facts:
    - Receive updates
  contexts:
    desktop:
      place: desktop::files
  unattended: true
- text: An update is downloading with its progress available.
  kind: product
  entities:
  - entity: update
    effect: creates
    facts:
    - Version
    - Progress
    - Package
    - Failure
    to: Downloading
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/Updates/QuietUpdateService.cs
---

# Prepare a newer release

## Trigger

Enabled quiet-update discovery finds a newer supported release.

## Outcome

An update is downloading with its progress available.
