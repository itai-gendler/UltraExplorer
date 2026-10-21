---
appliesTo:
- type: entity
  id: mark
- type: capability
  id: rename-filesystem-item
- type: capability
  id: move-items
- type: capability
  id: unpin-tag
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/FolderMarkService.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/ViewModels/MainViewModel.cs#CarryMarksAsync
---

# Colors and notes belong to paths and remain independent

Removing a color keeps the note. App renames carry marks beneath the renamed path. A move carries marks only for confirmed arrivals whose target name was free before the operation; copies do not duplicate marks.
