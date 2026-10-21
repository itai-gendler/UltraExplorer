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
  - Preview editing
- entity: archive-entry
  shows:
  - Path
  - Name
  - Kind
  - Size
  - Origin
- entity: text-draft
  shows:
  - Source
  - Text
  - Encoding
  collects:
  - Text
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/QuickPreviewWindow.cs
---

# Quick Look

Inspection of one file or archive entry, including media, document pages and editable text.
