---
appliesTo:
- type: entity
  id: text-draft
  effect: creates
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/QuickPreviewWindow.cs#LoadFileAsync
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/PreviewTextEditSession.cs#OpenAsync
permits:
- actors:
  - user
  when:
  - entity: file
    fact: Preview editing
    is: true
  - entity: file
    fact: Read only
    is: false
  - entity: file
    fact: Size
    at-most: 2097152
---

# Users create text drafts for complete writable text previews

Text editing is available for complete supported plain text at most 2 MiB that is not read-only.
