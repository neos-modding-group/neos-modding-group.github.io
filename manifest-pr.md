---
layout: default
title: Manifest PR Guide
---

## General Tips

- Don't insert your mod at the very end of the file, as you'll have to add a comma to the mod preceding you which can confuse git. Instead, put new mods at the top of the file (or anywhere really).
- Try not to move things around unnecessarily, as it will generate a larger diff and make reviewing your PR harder.
- Take care not to mess up the indentation. While it may not seem like a big deal, not enforcing consistent indentation would result in absolute chaos.
- For security reasons the automatic checks won't run on your first PR until a contributor manually triggers them. Your subsequent PRs will benefit from automatic whitespace and schema validation checks.

## Creating a PR

There are multiple ways to make a GitHub PR. We'll cover a few approaches.

### GitHub Web UI

Pros:

- You don't need to install any software
- Requires the least git knowledge of any method

Cons:

- The web editor isn't very good
- No schema validation
- No automatic indentation fixer

Simply edit manifest.json via the [GitHub Web Editor](https://github.com/neos-modding-group/neos-mod-manifest/edit/master/manifest.json).

### Local Text Editor (Like Visual Studio Code)

Pros:

- Can validate json schema
- Can fix bad indentation
- There are some very good text editors available

Cons:

- Requires some git know-how
- Requires you to install software

Teaching git is out of scope of this document, but it really is worth learning. Perhaps take a look at the [Git website](https://git-scm.com/).

1. Install [Visual Studio Code](https://code.visualstudio.com/)
2. [Fork](https://github.com/neos-modding-group/neos-mod-manifest/fork) the manifest
3. [Clone](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) your manifest fork ([git clone docs](https://git-scm.com/docs/git-clone))
4. `git remote add upstream git@github.com:neos-modding-group/neos-mod-manifest.git`
5. `git fetch upstream`
6. `git checkout upstream/master`
7. `git branch my-new-branch-name` ([git branch docs](https://git-scm.com/docs/git-branch))
8. Edit the manifest in VSC, enjoying its built-in JSON schema validator
9. `git add manifest.json` ([git add docs](https://git-scm.com/docs/git-add))
10. `git commit -m 'Add MyMod to the manifest'` ([git commit docs](https://git-scm.com/docs/git-commit))
11. `git push` ([git push docs](https://git-scm.com/docs/git-push))
12. Head back to the [manifest repo](https://github.com/neos-modding-group/neos-mod-manifest), where you should now see a button to open a PR. If not, you can manually [create a pull request from a fork](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork).

Repeat from step 5 for subsequent PRs.

## Additional Help

If you need additional help, you can ask in the [#mod-manifest channel in our Discord].

<!-- Links -->
[#mod-manifest channel in our Discord]: https://discord.gg/YUPK8UsBy4
