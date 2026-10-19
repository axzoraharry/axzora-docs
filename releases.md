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
| 18.18 | 210 | [v18.18](https://github.com/axzoraharry/axzora-ota/releases/tag/v18.18) | Hub panel — latency, history, live OTA channel readout |
| 18.17 | 209 | — | Command Deck — ten quick actions, type-ahead, history, copy/export |
| 18.16 | 96 | [v18.16](https://github.com/axzoraharry/axzora-ota/releases/tag/v18.16) | Omarchy terminal home |
| 18.15 | 95 | [v18.15](https://github.com/axzoraharry/axzora-ota/releases/tag/v18.15) | Titled TUI frames and pinned favourites |
| 18.14 | 94 | [v18.14](https://github.com/axzoraharry/axzora-ota/releases/tag/v18.14) | Command-bar calculator |
| 18.13 | 93 | [v18.13](https://github.com/axzoraharry/axzora-ota/releases/tag/v18.13) | Waybar workspaces |
| 18.12 | 92 | [v18.12](https://github.com/axzoraharry/axzora-ota/releases/tag/v18.12) | Fastfetch system card |
| 18.11 | 91 | [v18.11](https://github.com/axzoraharry/axzora-ota/releases/tag/v18.11) | Swipe gestures |
| 18.10 | 90 | [v18.10](https://github.com/axzoraharry/axzora-ota/releases/tag/v18.10) | Terminal home groundwork |

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
