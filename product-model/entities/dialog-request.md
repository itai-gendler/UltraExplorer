---
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Picker/FileDialogModels.cs
---

# Dialog request

One request for an Open, Save or folder choice, with the requesting application’s options and eventual answer.

## Information kept

- **Origin** — Direct caller request or supported native-dialog integration.
- **Mode** — Open, Save or folder selection.
- **Initial location** — The requested or remembered starting location.
- **File types** — The offered filename patterns and selected type.
- **Filename** — The typed name or pending selection.
- **Options** — The caller’s selection, validation and interaction requirements.
- **Application options** — Extra options carried by a supported native dialog.
- **Result paths** — The accepted filesystem locations, empty when cancelled.
- **Caller decision** — Accepted when no caller veto is present or the caller approves; otherwise rejected.
- **Interaction** — True once the caller’s interaction requirement is satisfied, including requests without such a requirement.

## States

### Pending

The choice is still in progress.

### Accepted

The caller has an accepted choice.

### Cancelled

The request ended without a choice.
