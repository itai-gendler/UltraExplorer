---
entities:
- entity: file
  shows:
  - Name
  - Path
  - Size
  - Modified
  - Type
  - Content
  - Hidden
  - Read only
- entity: folder
  shows:
  - Name
  - Path
  - Modified
  - Contents
  - Listing status
  - Hidden
  - Sort order
- entity: workspace
  shows:
  - Locations
  - Selection
  - History
  - Camera
  - Filter
  - Search
  - Split
  - Open tabs
  - Closed folders
  - Saved arrangement
  collects:
  - Locations
  - Filter
  - Search
- entity: mark
  shows:
  - Path
  - Color
  - Note
  - Item kind
  collects:
  - Color
  - Note
- entity: favorite
  shows:
  - Name
  - Path
- entity: archive-entry
  shows:
  - Path
  - Name
  - Kind
  - Size
  - Origin
- entity: update
  shows:
  - Version
  - Progress
  - Package
  - Failure
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/MainWindow.xaml
---

# Files

A filesystem working context, including its canvas, current-folder list, navigation, selection and search.
