---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Choose Open with.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: Windows offers an application choice and receives the file to open.
  kind: product
  entities:
  - entity: file
    effect: reads
    facts:
    - Path
    - Type
  actor: user
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/MainViewModel.cs
---

# Choose an application

## Trigger

The person wants another application for the focused file.

## Outcome

Windows offers an application choice and receives the file to open.

## Edge cases

- A missing file is reported.
