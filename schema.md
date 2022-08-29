---
layout: page
title: Manifest Schema
---

An actual json schema is provided [here](https://github.com/neos-modding-group/neos-mod-manifest/blob/master/schema.json). This can be used in all manner of [schema viewers](https://json-schema.app/view/%23?url=https%3A%2F%2Fraw.githubusercontent.com%2Fneos-modding-group%2Fneos-mod-manifest%2Fmaster%2Fschema.json), if you prefer a more interactive view of the schema.

If you're having trouble visualizing, take a look at the actual [manifest json](https://github.com/neos-modding-group/neos-mod-manifest/blob/master/manifest.json).

In the schema, the type of `map` differs from `object` in that the names of the keys aren't always the same.

Anything not explicitly marked as **optional** is mandatory.

Top-level: `object`

- `schemaVersion`: `string` [semver] of schema
- Mods: `map`
  - Key: `string` mod GUID, any unique string but typically something like "io.github.myuser.mymod"
  - Value: `object` the mod definition
    - `name`: `string` the mod's name
    - `description`: `string` short description of the mod's functionality
    - `authors`: `map`
      - Key: `string` author name
      - Value: `object`
        - Url: `string`
    - `sourceLocation`: `string` **optional** A link to the mod's source code.
    - `website`: `string` **optional** A link to the mod's website. May be the same as `sourceLocation`.
    - `tags`: `string[]` **optional** A list of tags that may be used for search in the future.
    - `category`: `string` A [category](categories) that your mod fits into
    - Flag list: `string[]` **optional** A list of [flags](manifest-flags) that apply to your mod
    - Versions: `map`
      - Key: `string` [semver], should match NeosMod.Version
      - Value: `object` the mod version definition
        - `changelog`: `string` **optional** A short description of what changed in your mod. This is markdown formatted text, so you can do things like bulleted lists.
        - `releaseURL`: **optional** `string` A link to this mod version's release notes.
        - `neosVersionCompatibility `: `string` **optional** Neos does not follow [semver] "2022.1.28.1310" but "<" and ">" rules will work fine. An example rule might be ">2021.4.2.690,<=2022.1.28.1310"
        - `modloaderVersionCompatibility `: `string` **optional** [semver] version specifier, such as "~1.12.0" or ">=1.8.0"
        - `flags`: `string[]` **optional** A list of [flags](manifest-flags) that apply to this specific mod version
        - `conflicts`: `map` **optional**
          - Key: `string` conflicting mod GUID
          - Value: `object`
            - `version`: `string` [semver] version specifier, "*" is all versions
        - `dependencies`: `map` **optional**
          - Key: `string` dependency mod GUID
          - Value: `object`
            - `version`: `string` [semver] version specifier
        - `artifacts`: `object[]` A list of files to install as part of this mod version.
          - `url`: `string` download url of the artifact
          - `filename`: `string` **optional** filename to use for the file. If absent, filename will be extracted from the last part of the URL
          - `Sha256`: `string` SHA-256 hash of this artifact
          - `blake3`: `string` **optional** Blake3 hash of this artifact
          - `installLocation`: `string` **optional** Where this artifact should be installed. defaults to "/nml_mods"

[semver]: https://semver.org/
