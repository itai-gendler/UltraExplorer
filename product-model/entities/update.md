---
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/Updates/QuietUpdateModels.cs
---

# Update

A newer release prepared for the person to install.

## Information kept

- **Version** — The offered release version.
- **Progress** — Download progress.
- **Package** — The prepared release package.
- **Failure** — An installation problem when one is reported to the person.

## States

### Downloading

A newer release is being obtained.

### Ready

A prepared release is available for explicit installation.

### Installing

The person has requested installation.

### Failed

Preparation or installation did not complete.
