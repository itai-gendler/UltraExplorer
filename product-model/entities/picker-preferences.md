---
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Picker/FileDialogClientStore.cs
---

# Picker preferences

Remembered choices belonging to a caller’s client identity.

## Information kept

- **Caller** — The application-provided client identity.
- **Last folder** — The last accepted location.
- **File type** — The remembered type choice.
- **Recent names** — Up to twelve recently chosen names.
