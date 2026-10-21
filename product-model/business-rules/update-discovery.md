---
appliesTo:
- type: entity
  id: update
  effect: creates
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/Updates/QuietUpdateService.cs
permits:
- unattended: true
  when:
  - entity: settings
    fact: Receive updates
    is: true
---

# The Product prepares updates only while receiving updates is enabled

Quiet discovery and downloading are enabled by the saved preference.
