---
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/PreviewTextEditSession.cs
---

# Text draft

Editable text held while a file is being inspected. Saving applies the text to its source file; a failed save retains the draft.

## Information kept

- **Source** — The source file path.
- **Text** — The current proposed contents.
- **Encoding** — The source encoding and byte-order-mark choice preserved when saving.

## States

### Modified

Text has been edited and is not yet saved.

### Saved

The draft matches the last successful save.

### Conflict

The source changed outside the editor and the proposed text remains available.
