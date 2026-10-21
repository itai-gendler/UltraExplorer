---
kind: primary
routes:
  cli: Command line
steps:
- text: Run the picker unregistration command.
  kind: actor
  actor: user
  entities: []
  contexts:
    cli:
      place: command-line
- text: The Product unregisters its own picker classes for this Windows user.
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

# Unregister picker for this user

## Trigger

The person runs the picker unregistration command.

## Outcome

The picker registration is removed for the current Windows user.
