---
kind: primary
routes:
  cli: Folder command
steps:
- text: The calling application requests opening a directory or revealing its selected paths.
  kind: actor
  actor: calling-application
  entities: []
  contexts:
    cli:
      place: command-line
- text: The Product creates an independent workspace context for the requested location and selection.
  kind: product
  actor: calling-application
  entities:
  - entity: workspace
    effect: changes
    facts:
    - Open tabs
    - Locations
    - Selection
  contexts:
    cli:
      place: command-line
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/FolderInvocation.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/ExplorerLaunchRouter.cs#ShouldCreateTab
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.FolderInvocation.cs
---

# Open a requested location

## Trigger

An external caller launches a filesystem folder or asks to reveal paths.

## Outcome

The requested location opens in an independent context. The existing context is retained.

## Decision points

### Incoming context

Where should the new context appear?

- New-tab preference with an available host → create a retained tab.
- Separate-window preference, explicit new-window request, or no usable host → open a separate window.
