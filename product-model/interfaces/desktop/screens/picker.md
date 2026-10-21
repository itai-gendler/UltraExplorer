---
entities:
- entity: dialog-request
  shows:
  - Mode
  - Initial location
  - File types
  - Filename
  - Options
  - Application options
  - Result paths
  - Caller decision
  - Interaction
  collects:
  - Filename
  - File types
  - Application options
- entity: file
  shows:
  - Name
  - Path
  - Type
  - Size
  - Modified
- entity: folder
  shows:
  - Name
  - Path
  - Contents
  - Listing status
- entity: picker-preferences
  shows:
  - Caller
  - Last folder
  - File type
  - Recent names
- entity: workspace
  shows:
  - Locations
  - Selection
  - Camera
  - History
  - Search
  - Filter
  collects:
  - Locations
  - Search
  - Filter
- entity: favorite
  shows:
  - Name
  - Path
- entity: mark
  shows:
  - Path
  - Color
  - Note
  - Item kind
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.Picker.cs
---

# File dialog

A single application file-choice process, including navigation, names, types, confirmations and application options.
