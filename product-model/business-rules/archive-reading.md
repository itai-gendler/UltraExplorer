---
appliesTo:
- type: entity
  id: archive-entry
  effect: reads
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/MainViewModel.Archives.cs
permits:
- actors:
  - user
  when:
  - entity: settings
    fact: Archives
    is: true
---

# Users inspect archive entries while archive browsing is enabled

Archive entry inspection is available with archive browsing enabled.
