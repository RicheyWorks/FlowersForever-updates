# FlowersForever updates

This public repository is where FlowersForever looks for updates. It holds **only
the signed update list** and **no source code**. The app's source stays in a
private repository.

- **`latest.json`** is the signed update list. GitHub Pages serves it at
  <https://richeyworks.github.io/FlowersForever-updates/latest.json>.
  FlowersForever downloads this one small file over HTTPS when it opens, and
  again when someone chooses *Help > Check for updates…*.
- **Installers** (Windows `.msi`, macOS `.dmg`) are attached to this repository's
  [Releases](https://github.com/RicheyWorks/FlowersForever-updates/releases).
  They are not committed as files. The update list links to them.

## Why this is safe to keep public

- The update list and every installer are signed with the RicheyWorks Ed25519
  publisher key. The app has the matching public key built in.
- The app checks every download's size, SHA-256 checksum, and signature, and
  rejects any file that fails.
- An edited or fake `latest.json` is rejected, so nobody can push a fake update
  through this repository.
- Before installing an update, the app makes a checked backup of the farm
  records. If the new version fails its first-start database check, the app
  goes back to the previous version and restores that backup.
- The app sends no farm data here. It only downloads the files listed above.

Anyone with the link can download a published installer, so only publish
installers that are meant for testers.

## Current state

`latest.json` is a signed list with **no releases yet**, so installed copies
see "You have the latest version" and nothing is offered.

## Publishing (maintainer only)

The steps are in `docs/AUTO_UPDATES.md` in the private FlowersForever repository:
`scripts/update-release.ps1 add-release` → `sign` → `verify`. Then attach the
installers to a release here and commit the new `latest.json`. The private
signing key never goes in this repository or anywhere online.
