# FlowersForever update feed

Public update metadata for [FlowersForever](https://github.com/RicheyWorks/FlowersForever).
The published feed describes available application updates.

[View the feed](https://richeyworks.github.io/FlowersForever-updates/latest.json) ·
[Browse releases](https://github.com/RicheyWorks/FlowersForever-updates/releases) ·
[Application source](https://github.com/RicheyWorks/FlowersForever)

## Current status

The current manifest contains **no release entries**. No installers have been
published in this repository's Releases as of October 7, 2026.

`latest.json` uses the `flowersforever-signed-manifest-v1` envelope: an encoded
payload, a publisher key identifier, and a signature. The payload identifies
FlowersForever and carries the release list. Client verification and installation
behavior belong to the application's update implementation.

## Repository contents

| File | Purpose |
| --- | --- |
| [`latest.json`](./latest.json) | Published update manifest. |
| [`.nojekyll`](./.nojekyll) | Tells GitHub Pages to serve the files as provided. |
| [`README.md`](./README.md) | Feed status and navigation. |

To inspect the feed, open [`latest.json`](./latest.json) or its
[HTTPS endpoint](https://richeyworks.github.io/FlowersForever-updates/latest.json).
Installers, when published, will be attached to
[Releases](https://github.com/RicheyWorks/FlowersForever-updates/releases).

## Maintainer notes

Generate and verify manifests with the application's release tooling before
publishing them. Keep signing keys outside this repository. Publish only
installers intended for public distribution.

GitHub Pages currently publishes this repository's `main` branch at `/`.
Changes merged into that branch can rebuild the public feed, so publishing a
manifest is a release action.
