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
| 18.45 | 237 | [v18.45](https://github.com/axzoraharry/axzora-ota/releases/tag/v18.45) | Happy Paisa by voice: `balance`/`mint`/`send` crashed on first use — a one-time holder built the wallet object with a null wallet, a linkage error no `catch(Exception)` can see; the wallet is now fetched per call |
| 18.44 | 236 | ↑ v18.45 | A live "paisa" balance on the home card, and the server finder probes loopback before any cached host |
| 18.43 | 235 | ↑ v18.45 | The local hub is preferred on-device (127.0.0.1) |
| 18.42 | 234 | ↑ v18.45 | Every installed app on the home screen, four to a row |
| 18.41 | 233 | ↑ v18.45 | Intermediate build |
| 18.40 | 232 | ↑ v18.45 | Happy Paisa voice tool wired into Mr Happy |
| 18.39 | 231 | ↑ v18.45 | Intermediate build |
| 18.38 | 230 | ↑ v18.45 | The admin console no longer wipes your code and seat on a hub outage |
| 18.37 | 229 | [v18.37](https://github.com/axzoraharry/axzora-ota/releases/tag/v18.37) | Mr Happy fully Axzora-branded — Axzora Core headers, wake words "Axzora"/"Mr Happy" |
| 18.36 | 228 | [v18.36](https://github.com/axzoraharry/axzora-ota/releases/tag/v18.36) | The on-device model proves it is a model: the archive is checked before it is called installed, a damaged file is named and offers **Repair**, resumes that arrive at the wrong offset are thrown away, and the default model is the public 547 MB Qwen 2.5 0.5B instead of a gated repo |
| 18.35 | 227 | ↑ v18.36 | The same model fix, uploaded minutes earlier with "Blank = default Gemma" still on the URL field; superseded |
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


## A model that was only pretending to be installed

A 1.6 GB download arrived damaged — 1,647 MB on a 1,597 MB file — and Settings
said **Installed (1647MB)** because the only test was `length > 50MB`. Pressing
Load produced MediaPipe's C++ stack trace: *"Unable to read the file in zip
archive"*. A `.task` model is a ZIP archive, and the bytes on disk were not one.

18.36 checks the archive instead of its size: a local header near the start, an
end-of-central-directory record in the last 64 KB, and a central directory that
ends exactly where the file ends. That gives four named failures — truncated,
spliced, wrong file, too small — a sentence saying which one happened, and a
**Repair** button. Resumes are also stricter: a `206` that does not continue at
the exact byte offset, or a body longer than the server promised, now discards
the partial file instead of appending to it. Two downloads can no longer race on
one `.part`, and a partial file remembers which URL it came from.

The default model moved off `litert-community/Gemma3-1B-IT` — a **gated** repo,
so a plain Download answered 401 without a HuggingFace token — to the public
`Qwen2.5-0.5B-Instruct` 8-bit task: 547 MB, no account, and published in the
bundle format MediaPipe reads. Both published Qwen bundles were read back from
HuggingFace range-by-range and pass the same validation, so a genuine `.task`
can never be reported as damaged.

## Installing a build

1. Download the `.apk` for the version you want.
2. Open it. Allow *Install unknown apps* for the app you downloaded it with,
   once.
3. Android's installer verifies the signature and installs over the existing
   copy. Your settings, history and pairing survive.

The in-app path is shorter: the app checks `/update/check` on launch, offers
the build it finds, and downloads it for you. See [Docs](/docs/) for how the
manifest and the local hub work.
