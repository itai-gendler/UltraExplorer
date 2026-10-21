---
appliesTo:
- type: entity
  id: shelf-item
  effect: changes
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/MainViewModel.OptionalFeatures.cs
permits:
- actors:
  - user
  when:
  - entity: settings
    fact: Shelf
    is: true
---

# Users arrange shelf items while the shelf is enabled

The shelf preference enables editing the retained arrangement.
