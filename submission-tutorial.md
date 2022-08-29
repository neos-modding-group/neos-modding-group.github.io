---
layout: page
title: Submission Tutorial
---

## How to Make a Submission

Create a new pull request to [manifest.json] adding your new mod. Once your pull request is created, community members will review your submission as per the [mod auditing process].

If you're new to git or GitHub, take a look at the [Manifest PR Guide](manifest-pr).

## Requirements

A full list of submission requirements is available [here][mod submission guidelines], but here are the important ones for submitting your first mod:

- Follow the [schema]. We have automatic validation on GitHub PRs to check this.
- Don't ruin the whitespace (indent using four spaces!) We have automatic validation on GitHub PRs to check this.
- Include a valid SHA-256 hash for your mod. If you don't have a SHA-256 tool on your PC, a [web tool like this][sha256 online] may help.
- Don't remove existing manifest entries. Deprecate them instead using the `deprecated` [flag].
- Pick a category from the [category list][categories]. If you're uncertain, check how [other mods][mod list] are categorized.


An example mod definition is provided below. Note that comments are not allowed in JSON and are only provided here for your reference.

```js
"dev.zkxs.examplemod": { // GUID for your mod. This MUST be unique.
    "name": "Example Mod", // Your mod's name
    "description": "Doesn't do anything", // Short description of your mod's functionality
    "category": "Misc", // The category that best fits your mod.
    "website": "https://github.com/zkxs/ExampleMod", // your mod's homepage
    "sourceLocation": "https://github.com/zkxs/ExampleMod", // where your source code is hosted
    "authors": { // note that you can have more than one author!
        "runtime": { // author name
            "url": "https://github.com/zkxs" // author's website
        }
    },
    "versions": { // all of your versions go here
        "1.1.0": { // version number
            "releaseUrl": "https://github.com/zkxs/ExampleMod/releases/tag/1.1.0.0", // home page for this version
            "artifacts": [ // note that you can have more than one artifact!
                {
                    "url": "https://github.com/zkxs/ExampleMod/releases/download/1.1.0.0/ExampleMod.dll", // download URL
                    "sha256": "4d7aee0c357c6683bc6d046b1961ed1ce21bbbd23f120b8dc7b1553db01d7174" // sha256 hash of ExampleMod.dll. It is very important that this is correct.
                }
            ]
        }
    }
}
```

Here is the same JSON again, but this time ready for copy/pasting into the manifest. Just update the fields to match your mod.
```json
        "dev.zkxs.examplemod": {
            "name": "Example Mod",
            "description": "Doesn't do anything",
            "category": "Misc",
            "website": "https://github.com/zkxs/ExampleMod",
            "sourceLocation": "https://github.com/zkxs/ExampleMod",
            "authors": {
                "runtime": {
                    "url": "https://github.com/zkxs"
                }
            },
            "versions": {
                "1.1.0": {
                    "releaseUrl": "https://github.com/zkxs/ExampleMod/releases/tag/1.1.0.0",
                    "artifacts": [
                        {
                            "url": "https://github.com/zkxs/ExampleMod/releases/download/1.1.0.0/ExampleMod.dll",
                            "sha256": "4d7aee0c357c6683bc6d046b1961ed1ce21bbbd23f120b8dc7b1553db01d7174"
                        }
                    ]
                }
            }
        },
```

Note that some of these fields are optional, and some rarely-used fields are omitted from this example. Consult the [schema] for more details.

## Additional Help

If you need additional help, you can ask the [#mod-manifest channel in our Discord].

<!-- Links -->
[#mod-manifest channel in our Discord]: https://discord.gg/YUPK8UsBy4
[categories]: categories
[flag]: manifest-flags
[manifest.json]: https://github.com/neos-modding-group/neos-mod-manifest/blob/master/manifest.json
[mod auditing process]: auditing-process
[mod list]: mods
[mod submission guidelines]: mod-guidelines
[schema]: schema
[sha256 online]: https://emn178.github.io/online-tools/sha256_checksum.html
