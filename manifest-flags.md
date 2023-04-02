---
layout: default
title: Mod Manifest Flags
---

Flags used in the [manifest](manifest) to indicate various things about mods or mod versions.

## Mod Flags

These flags can be defined on a mod:

- `deprecated` Deprecated (maintainer is gone, users need to migrate)
- `plugin` it needs a -LoadAssembly argument to work and it does not depend on NML
- `file` it does not depend on NML

## Version Flags

Mod versions inherit the flags of their defining mod, and can additionally use these flags:

- Security Vulnerability
  - `vulnerability:low` Low
  - `vulnerability:medium` Medium
  - `vulnerability:high` High
  - `vulnerability:critical` Critical
- `broken` This version is broken and doesn't work on any platform.
  - `broken:linux-native` Doesn't work on linux native
  - `broken:linux-wine` Doesn't work on linux wine/proton
  - `broken:windows` Doesn't work on windows
- `prerelease` Mod dev wants to limit distribution
