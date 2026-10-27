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
| 18.34 | 226 | [v18.34](https://github.com/axzoraharry/axzora-ota/releases/tag/v18.34) | Settings → About names the publisher — Axzora Private Limited, `harry@axzora.com`, +91 96969 69691 — tappable to mail or dial; the server reports the same three facts at `/api/identity` |
| 18.33 | 225 | ↑ v18.34 | A 1.6 GB model download survives a bad connection: `Range` resume, eight retries, the partial file kept across attempts and across app updates |
| 18.32 | 224 | ↑ v18.34 | A pinned server is actually used — the discovery loop read the first frame's empty settings and overwrote the pin with the cloud host |
| 18.31 | 223 | ↑ v18.34 | The brains stop being frozen at first composition |
| 18.30 | 222 | ↑ v18.34 | Assistant race readout names every brain that was asked |
| 18.27 | 219 | ↑ v18.34 | Three brains raced concurrently, best answer kept (`AnswerRacer`), speed only a tie-break |
| 18.26 | 218 | ↑ v18.34 | HappyBetPlay — "what's today's P/L?" answered out loud, in lakh and crore |
| 18.25 | 217 | ↑ v18.34 | The updater verifies the sha256 of the APK it installs instead of trusting its size |
| 18.24 | 216 | ↑ v18.34 | The launcher bar hands its sentence to Mr Happy instead of discarding it |
| 18.23 | 215 | [v18.23](https://github.com/axzoraharry/axzora-ota/releases/tag/v18.23) | Hub by voice — "open the sheets" resolves through the local everything-hub |
| 18.22 | 214 | ↑ v18.34 | Mr Happy answers your voice with **no wake word** (`VoicePrint`: a doorbell, not a lock) |
| 18.21 | 213 | [v18.21](https://github.com/axzoraharry/axzora-ota/releases/tag/v18.21) | Circle secrets — a circle is a code *and* a 192-bit secret; God's Eye reads only while sharing is on |
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

18.22 to 18.34 shipped on the phone and were not published until 18.34. The
manifest on the server stayed at 213 the whole time, so the in-app updater
offered nothing for twelve builds: the phone moved on, the channel did not. All
of them are in the 18.34 asset — the table above links each to the release that
actually carries it rather than to a tag that never existed.

Publishing an APK is a separate problem from building one. A repository file is
capped at 100 MB and the build is 109 MB, so it can only be a Release asset, and
that upload is a single non-resumable POST that fails on a phone by stalling
until GitHub answers *"Upload body timed out due to inactivity"*. Four attempts
failed that way. `tools/ota/release-upload.sh` now creates the release as a
**draft**, uploads with an explicit `--speed-limit 1024 --speed-time 30` so a
stall is detected in 30 seconds instead of 60, deletes the half-written asset
before retrying, and compares **both** the size and the sha256 the API reports
against the local file before publishing. 18.34 took 56 seconds and the
downloaded bytes hash to `28904e5c…38674`.

18.19 was built on-device without an Android SDK: the web assets were re-packed
into the signed APK and `versionCode`/`versionName` patched in the binary
manifest, then re-signed with the release key.

18.20 is the first build compiled on the phone itself. AGP ships an x86_64-only
`aapt2`; pointing Gradle at an arm64 `aapt2` (`-Pandroid.aapt2FromMavenOverride`)
lets the whole `:app:assembleRelease` run — Kotlin, R8, `lintVitalRelease`,
signing — with no SDK platform tools beyond `android.jar`. That is how the
Compose depth transitions and the keystore-bound admin console reached a device.

18.21 closes a privacy hole rather than adding a feature. A circle used to be a
short word — `/godseye?code=X` answered with a family's live positions to anyone
who guessed or overheard it. A circle is now a code plus a secret the server
mints; the creator sees it once as a join string `CODE~SECRET`, secrets are
stored `0600`, comparisons are constant time, and the `403` depends only on what
the caller sent so codes cannot be probed. God's Eye also stopped talking to the
server when sharing was switched off. **Circles created on 18.20 or earlier have
no secret and are refused — re-create them and share the new join string.**

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
