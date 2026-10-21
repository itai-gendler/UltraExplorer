---
appliesTo:
- type: entity
  id: text-draft
- type: capability
  id: save-text
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/PreviewTextEditSession.cs
---

# Saving text preserves encoding and retains conflicting edits

A save preserves the original encoding and byte-order mark. A changed source, unencodable text or a size above 2 MiB prevents committing the proposed text and retains it for the person.
