# GETTR Desktop Downloads

Public distribution for GETTR Desktop installers and the Tauri updater manifest.
This repository holds build outputs only — there is no source code here.

A browser-friendly download page is published from `docs/` at
[flamecast-pc.github.io/gettr-desktop-releases](https://flamecast-pc.github.io/gettr-desktop-releases/).

## Download

These links always resolve to the newest stable release. They do not change when
a new version ships, so they are safe to bookmark, publish, or embed.

| Platform | Download |
| --- | --- |
| Windows x64 (installer) | [GETTR_Desktop_x64-setup.exe](https://github.com/flamecast-pc/gettr-desktop-releases/releases/latest/download/GETTR_Desktop_x64-setup.exe) |
| Windows x64 (MSI) | [GETTR_Desktop_x64_en-US.msi](https://github.com/flamecast-pc/gettr-desktop-releases/releases/latest/download/GETTR_Desktop_x64_en-US.msi) |
| macOS (Apple Silicon) | [GETTR_Desktop_aarch64.dmg](https://github.com/flamecast-pc/gettr-desktop-releases/releases/latest/download/GETTR_Desktop_aarch64.dmg) |
| macOS (Intel) | [GETTR_Desktop_x86_64.dmg](https://github.com/flamecast-pc/gettr-desktop-releases/releases/latest/download/GETTR_Desktop_x86_64.dmg) |

macOS ships as two separate packages rather than a universal binary. On Apple
Silicon, take the Apple Silicon build: the Intel build runs under Rosetta but is
slower and carries no beauty filter.

Earlier versions are listed under
[Releases](https://github.com/flamecast-pc/gettr-desktop-releases/releases).
Releases marked as pre-release are internal test builds and are deliberately
excluded from the links above.

## Verify a download

Every release ships a `SHA256SUMS.txt` covering all version-stamped assets of
that release:

```bash
curl -fsSLO https://github.com/flamecast-pc/gettr-desktop-releases/releases/download/<tag>/SHA256SUMS.txt
sha256sum --check SHA256SUMS.txt
```

On macOS, use `shasum -a 256 --check` instead of `sha256sum --check`.

The unversioned files linked above are byte-identical copies of the
version-stamped assets in the same release, so their checksums are the ones
listed for the corresponding `GETTR_Desktop_<version>_*` file.

## Automatic updates

Installed clients check
[`latest.json`](https://github.com/flamecast-pc/gettr-desktop-releases/releases/latest/download/latest.json)
through the Tauri updater and verify the update package signature against a
public key built into the application. Updates replace the whole application
rather than patching it, so the client must leave the room and stop every media
source before installing.
