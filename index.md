---
layout: page
title: Neos Mod Loader
---

[NeosModLoader] is a mod loading [plugin] for [NeosVR].
It also contains some extra magic to still let you hang out with other people that might not have the plugin, as usually having different plugins means you can't connect to the same sessions.

You can find the source code and release builds of it [from Github][NeosModLoader].

## Finding mods

The [mods list][mods] is a community-managed listing of mods that are vetted to not be malicious.

The purpose of the list is to make it easier & safer for people to run mods.
Since mods are another form of executables, and it's generally not recommended to not run random executables from the internet.

NeosModLoader of course allows you to run any mods, but be extra cautious about making sure that they're safe if you go looking for ones not on the list.

## For developers

If you have more items for the list, please [open a PR][submission tutorial]. If you want to get update notifications join [our Discord][discord].

The [list][mods] is automatically generated from a machine-readable [manifest] with github actions. The [schema documentation][schema] explains what the fields in the manifest mean. Having a machine-readable manifest is an important step towards our planned mod manager and auto-updater software.

The source is hosted at [this GitHub repository][github repository].

<!-- Links -->
[discord]: https://discord.gg/vCDJK9xyvm
[github repository]: https://github.com/neos-modding-group/neos-mod-manifest
[manifest]: https://github.com/neos-modding-group/neos-mod-manifest/blob/master/manifest.json
[mods]: mods
[NeosModLoader]: https://github.com/neos-modding-group/NeosModLoader
[schema]: schema
[submission tutorial]: submission-tutorial
[NeosVR]: https://neos.com
[plugin]: https://wiki.neos.com/Plugins
