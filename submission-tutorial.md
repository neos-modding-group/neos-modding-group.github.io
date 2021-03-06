---
layout: page
title: Submission Tutorial
---

Create a new pull request adding a new mod definition to the [manifest]. (If you're new to GitHub, they have a simple [web editor][github web pull request] for pull requests). An example mod definition is provided below. Note that comments are not allowed in JSON and are only provided here for your reference.

```js
"dev.zkxs.examplemod": { // GUID for your mod. This MUST be unique.
    "name": "Example Mod", // Your mod's name
    "description": "Doesn't do anything", // Short description of your mod's functionality
    "category": "For Mod Developers", // The category that best fits your mod.
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

If you're trying to figure out how to get the sha256 hash, a [web tool like this][sha256 online] may help.

Some of these fields are optional, and some rarely-used fields are omitted from this example. Consult the [schema] for more details.

Once your pull request is created, community members will review your submission as per the [mod auditing process].

## Choosing a Category

Take a look at the [category list][categories] and check how [other mods][mod list] are categoriezed.

<!-- Links -->
[categories]: categories
[github web pull request]: https://github.com/neos-modding-group/neos-mod-manifest/edit/master/manifest.json
[manifest]: https://github.com/neos-modding-group/neos-mod-manifest/blob/master/manifest.json
[mod auditing process]: auditing-process
[mod list]: mods
[mod submission guidelines]: mod-guidelines
[schema]: schema
[sha256 online]: https://emn178.github.io/online-tools/sha256_checksum.html
