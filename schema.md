---
layout: page
title: Manifest Schema
---

In the schema, the type of `map` differs from `object` in that the names of the keys aren't always the same.

Top-level: `object`

- Schema version: `string` (semver version)
- Mods: `map`
  - Key: `string` (mod GUID)
  - Value: `object`
    - Name: `string`
    - Description: `string`
    - Authors: `map`
      - Key: `string` (author name)
      - Value: `object`
        - Url: `string`
    - Source Location: `string`
    - Website: `string`
    - Tag list: `string[]` (useful for search)
    - Category: `string`
    - Flag list: `string[]` (see mod flags below)
    - Versions: `map`
      - Key: `string` (semver version)
      - Value: `object`
        - Changelog: `string`
        - Release URL: `string`
        - Neos version compatibility: `string` (NOT semver "2022.1.28.1310" but "<" and ">" rules will work fine)
        - Modloader version compatibility: `string` (semver version specifier)
        - Flag list: `string[]` (see version flags below)
        - Conflicts: `map`
          - Key: `string` (mod GUID)
          - Value: `string` (semver version specifier, "*" is all versions)
        - Dependencies: `map`
          - Key: `string` (dependency mod GUID)
          - Value: `object`
            - Key: `string` (mod GUID)
            - Value: `object`
              - Version: `string` (semver version specifier)
        - Artifacts: `object[]`
          - URL: `string` (download url of the .dll file)
          - Filename: `string` (filename to use for the file, if missing extract from the last part of the URL)
          - Sha256: `string`
          - Install location: `string` (defaults to "/nml_mods")
