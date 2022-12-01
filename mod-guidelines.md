---
layout: page
title:  Mod Submission Guidelines
---

These guidelines explain what is expected when submitting a new mod version to the manifest.

## Submissions

New submissions **must** be submitted as a pull request to the [manifest repository].

If you need help with your submission, read the [submission tutorial].

## General Manifest Requirements

### Schema Correctness

Submissions **must** follow the [schema]. Match your indentation to the existing json (indent using 4 spaces).

You **must** include a correct SHA256 hash of your artifacts.

### Do Not Remove Versions

You **must** not remove old versions of your mod from the manifest. If you no longer plan to maintain the mod, use the `deprecated` [flag] on the mod entry, which will hide it from the [mod list] and autoupdaters. The manifest is designed to store a history of mods: not just current versions. This allows us to flag mods with additional metadata, for example marking them as having security vulnerabilities.

### Indicate Platform Incompatibilities

If your mod is incompatible with a platform, you **must** indicate that using the appropriate [flag] (for example `broken:linux-native`).

### Version Numbers

Your manifest submission **should** have version numbers that match the NeosMod version. The `AssemblyVersion` and `AssemblyFileVersion` assembly attributes **should** match your mod version.

If you think having to change the version number in three places is a pain, you're right. Luckily, there's a way you can get away with having it in one place, which I've demonstrated in [this mod](https://github.com/zkxs/NeosDesktopToolShortcutRemapper).

### Libraries

Mods **should** avoid repackaging third party libraries into their DLL. Consider adding third-party libraries as an external dependency in the manifest. This allows auditors to review your mod and libraries separately and makes the auditing process much faster.

## Privacy and Security

### Obfuscation

Mods **must not** be obfuscated. We audit mods by inspecting their binaries, which is not feasible for obfuscated mods.

### Transparency

Mods **should** be up-front about what they do. Accurate descriptions, screenshots, etc, are all good to have.

Mods **should** be open-source. While this is not a hard requirement, having up-to-date source code available is helpful for the auditing process.

### Remote Code

Mods **must not** download or execute remote code. This means the following are forbidden:

- auto updaters
- fetching Neos json/7zbson/etc from a non-neos server (neosdb urls are okay)

### Neos Guidelines

Mods **must not** violate the [Neos guidelines] or the [mod and plugin policy]. Some significant points from the guidelines:

- Do not bypass protections and controls within Neos, for example SimpleAvatarProtection, permissions, and bans.
- Do not enable asset theft
- Do not enable harassment
- Do not track users without their consent

This is not an exhaustive list. The [Neos guidelines] are the definitive source on what is and is not allowed.

## Optional Stuff

### Performance

Mods **should** avoid performance hits to Neos where possible. While performance is not the primary goal of the audit, if we notice code that is extremely inefficient we may ask you to improve it.

<!-- Links -->
[flag]: manifest-flags
[manifest repository]: https://github.com/neos-modding-group/neos-mod-manifest
[mod and plugin policy]: https://wiki.neos.com/Mod_%26_Plugin_Policy
[mod list]: https://www.neosmodloader.com/mods 
[Neos guidelines]: https://docs.google.com/document/d/1G_-PaxSp8rGYeHUIXK-19b2VqOLlpOZ18e7DrOwNjG4/edit
[schema]: schema
[submission tutorial]: submission-tutorial
