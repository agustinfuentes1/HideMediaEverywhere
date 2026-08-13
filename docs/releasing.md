# Release checklist

Use releases for stable points that users can return to. Do not create a release for every small commit.

1. Update Vencord and install dependencies.
2. Run `pnpm testTsc` and `pnpm build` from the Vencord source folder.
3. Test hide, cross-channel matching, drag-to-peek, unhide, search results, and one client restart.
4. Update `CHANGELOG.md` and replace `Unreleased` with the release version and date.
5. Commit the release changes.
6. Create an annotated tag such as `v1.0.0`.
7. Push the commit and tag.
8. Create a GitHub release from the tag and paste the matching changelog section.
9. Mark it as a pre-release if a Discord or Vencord update has not been tested yet.

## Release note template

```md
## What changed

- Describe the user-facing change.

## Tested with

- Discord or Vesktop:
- Vencord commit:
- Windows, macOS, or Linux:

## Install or update

Follow the [installation guide](https://github.com/t6rtar/HideMediaEverywhere/blob/main/docs/installation.md). Existing users can pull the latest source, rebuild Vencord, then quit and reopen their client.

## Known issues

- None known.
```
