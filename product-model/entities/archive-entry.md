---
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Services/Archives/ArchiveIndex.cs
---

# Archive entry

A file or directory addressed inside a browsable archive.

## Information kept

- **Path** — The virtual location within the archive, including nested archives.
- **Name** — The entry name.
- **Kind** — File or directory.
- **Size** — The uncompressed size where supplied by the archive.
- **Origin** — The archive that contains it.
