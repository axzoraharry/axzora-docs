---
layout: default
title: Releases
permalink: /releases/
---
{% include nav.md %}

# AxzoraOS releases

Every build is signed with the same release key and installs in place over the
one before it. `versionCode` always increases; Android refuses anything else.

| Version | Code | Release | Headline |
| --- | --- | --- | --- |
| 18.20 | 212 | [v18.20](https://github.com/axzoraharry/axzora-ota/releases/tag/v18.20) | Depth, natively — Compose screen transitions, press tilt, admin bound to one device |
| 18.19 | 211 | [v18.19](https://github.com/axzoraharry/axzora-ota/releases/tag/v18.19) | Depth — 3D panel entrances, staggered rows, press tilt, reduced-motion aware |
| 18.18 | 210 | [v18.18](https://github.com/axzoraharry/axzora-ota/releases/tag/v18.18) | Hub panel — latency, history, live OTA channel readout |
| 18.17 | 209 | — | Command Deck — ten quick actions, type-ahead, history, copy/export |
| 18.16 | 96 | [v18.16](https://github.com/axzoraharry/axzora-ota/releases/tag/v18.16) | Omarchy terminal home |
| 18.15 | 95 | [v18.15](https://github.com/axzoraharry/axzora-ota/releases/tag/v18.15) | Titled TUI frames and pinned favourites |
| 18.14 | 94 | [v18.14](https://github.com/axzoraharry/axzora-ota/releases/tag/v18.14) | Command-bar calculator |
| 18.13 | 93 | [v18.13](https://github.com/axzoraharry/axzora-ota/releases/tag/v18.13) | Waybar workspaces |
| 18.12 | 92 | [v18.12](https://github.com/axzoraharry/axzora-ota/releases/tag/v18.12) | Fastfetch system card |
| 18.11 | 91 | [v18.11](https://github.com/axzoraharry/axzora-ota/releases/tag/v18.11) | Swipe gestures |
| 18.10 | 90 | [v18.10](https://github.com/axzoraharry/axzora-ota/releases/tag/v18.10) | Terminal home groundwork |

18.19 was built on-device without an Android SDK: the web assets were re-packed
into the signed APK and `versionCode`/`versionName` patched in the binary
manifest, then re-signed with the release key.

18.20 is the first build compiled on the phone itself. AGP ships an x86_64-only
`aapt2`; pointing Gradle at an arm64 `aapt2` (`-Pandroid.aapt2FromMavenOverride`)
lets the whole `:app:assembleRelease` run — Kotlin, R8, `lintVitalRelease`,
signing — with no SDK platform tools beyond `android.jar`. That is how the
Compose depth transitions and the keystore-bound admin console reached a device.

Release assets live in
[axzoraharry/axzora-ota](https://github.com/axzoraharry/axzora-ota/releases) —
big binaries belong there as Release assets, never in a repository tree.

## Installing a build

1. Download the `.apk` for the version you want.
2. Open it. Allow *Install unknown apps* for the app you downloaded it with,
   once.
3. Android's installer verifies the signature and installs over the existing
   copy. Your settings, history and pairing survive.

The in-app path is shorter: the app checks `/update/check` on launch, offers
the build it finds, and downloads it for you. See [Docs](/docs/) for how the
manifest and the local hub work.
