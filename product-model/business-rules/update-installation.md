---
appliesTo:
- type: entity
  id: update
  effect: changes
  to: Installing
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.Updates.cs
permits:
- actors:
  - user
  when:
  - entity: settings
    fact: Receive updates
    is: true
---

# Only the user starts installation of a prepared update

A ready release is installed only after explicit review and confirmation; background preparation never starts installation.
