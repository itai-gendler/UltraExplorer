---
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Models/ViewAllGraphModels.cs
relations:
- entity: text-draft
  verb: has an editable draft
  cardinality: one-to-many
---

# File

A named filesystem file that can be selected, inspected and acted on.

## Information kept

- **Name** — The filename including its extension.
- **Path** — Its current filesystem location.
- **Size** — Its size in bytes.
- **Modified** — Its last modification time.
- **Type** — Its file type.
- **Content** — The contents opened or previewed.
- **Hidden** — Whether filesystem attributes classify it as hidden or system.
- **Read only** — Whether the file is read-only.
- **Preview editing** — Whether the preview has complete supported plain text rather than truncated, binary or extracted document content.
