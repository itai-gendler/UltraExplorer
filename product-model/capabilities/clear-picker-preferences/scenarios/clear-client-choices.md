---
kind: primary
routes:
  com: COM caller
steps:
- text: The calling application requests clearing of its remembered client data.
  kind: actor
  actor: calling-application
  entities: []
  contexts:
    com:
      place: picker-api
- text: The Product removes the picker preferences for the supplied client identity.
  kind: product
  actor: calling-application
  entities:
  - entity: picker-preferences
    effect: removes
  contexts:
    com:
      place: picker-api
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Picker/Com/FileDialogComBase.cs
---

# Clear client choices

## Trigger

The caller clears its client data.

## Outcome

Subsequent requests no longer use those remembered choices.
