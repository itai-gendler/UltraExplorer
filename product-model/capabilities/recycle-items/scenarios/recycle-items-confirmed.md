---
kind: primary
routes:
  desktop: Windows desktop
steps:
- text: Confirm the requested removal when asked.
  kind: actor
  entities: []
  actor: user
  contexts:
    desktop:
      place: desktop::files
- text: The Product removes the selected standalone file paths through Windows Shell.
  kind: product
  entities:
  - entity: file
    effect: removes
  actor: user
  contexts: &id001
    desktop:
      place: desktop::files
- text: The Product removes the selected folder paths with their contents through Windows Shell.
  kind: product
  entities:
  - entity: folder
    effect: removes
  - entity: workspace
    effect: changes
    facts:
    - Selection
  actor: user
  contexts: *id001
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/MainViewModel.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/NativeShellService.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/ShellFileOperation.cs
---

# Recycle selected items

## Trigger

The person requests recycle.

## Outcome

The selected file and folder paths are removed from their source locations through Windows Shell and the workspace selection and affected listings are refreshed.

## Edge cases

- Selected items that are not currently shown require a count-based confirmation.
- Cancelling confirmation makes no change.
- Missing paths are removed from selection without asking Windows to remove them again.
- Windows can cancel or fail the operation; the reported result is not a promise that every source was removed.
