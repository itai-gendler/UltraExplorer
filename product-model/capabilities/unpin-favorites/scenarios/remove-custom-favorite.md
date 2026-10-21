---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Unpin the shortcut.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The favorite is removed while its target remains unchanged.
  kind: product
  entities:
  - entity: favorite
    effect: removes
  actor: user
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/MainViewModel.cs
---

# Unpin a custom shortcut

## Trigger

The person removes a custom shortcut.

## Outcome

The favorite is removed while its target remains unchanged.
