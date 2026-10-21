---
kind: primary
routes:
  cli: Command line
steps:
- text: Run the picker registration command.
  kind: actor
  actor: user
  entities: []
  contexts:
    cli:
      place: command-line
- text: The Product registers its own picker classes for this Windows user.
  kind: product
  actor: user
  entities:
  - entity: settings
    effect: changes
    facts:
    - Picker registration
  contexts:
    cli:
      place: command-line
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Picker/Com/ComServer.cs
---

# Register picker for this user

## Trigger

The person runs the picker registration command.

## Outcome

The picker classes are registered for the current Windows user.
