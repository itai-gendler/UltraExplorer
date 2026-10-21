---
appliesTo:
- type: entity
  id: dialog-request
  effect: creates
permits:
- actors:
  - user
  when:
  - fact: Origin
    is: Direct
- actors:
  - user
  when:
  - fact: Origin
    is: Native
  - entity: settings
    fact: Windows integration
    is: true
references:
- kind: code
  role: implementation
  target: src/UltraExplorer/Picker/Integration/NativeDialogProxy.cs
- kind: code
  role: implementation
  target: src/UltraExplorer/Picker/FileDialogCommandLine.cs
---

# Users start direct choices or enabled native choices

Direct caller requests offer a choice independently of general Windows integration. Native-dialog integration offers its supported choice only while enabled.
