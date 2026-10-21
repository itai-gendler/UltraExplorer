---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Copy the paths.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The selected paths, or the focused path when nothing is selected, are placed on the clipboard as quoted text.
  kind: product
  entities:
  - entity: file
    effect: reads
    facts:
    - Path
  - entity: folder
    effect: reads
    facts:
    - Path
  actor: user
  contexts:
    desktop:
      place: desktop::files
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/MainViewModel.cs
---

# Copy selected path text

## Trigger

The person requests Copy path.

## Outcome

The selected paths, or the focused path when nothing is selected, are placed on the clipboard as quoted text.

## Edge cases

- Clipboard failures are reported.
- Optional hover copy-path controls are offered only while their preference is enabled.
