---
layout: default
title: Docs
permalink: /docs/
---
{% include nav.md %}

# Documentation

Technical documentation for Axzora tools and platforms.

## AxzoraOS

AxzoraOS is an Android launcher and personal assistant (`com.axzora.os`) built
around a single voice-first surface — Mr Happy — with a written HUD underneath
it. The HUD is a WebView over `assets/hud.html`, so the interface can be
updated without touching a line of Kotlin.

### Install

| Step | What happens |
| --- | --- |
| 1. Download | Grab the newest APK from [Releases](/releases/), or let the app update itself |
| 2. Install | Android's own installer takes over; existing data is kept in place |
| 3. Permissions | Microphone (so it can hear its name), notifications (for update alerts), location (optional, for the *Where* chip) |

The app is signed with one long-lived release key. Every build installs **in
place over the previous one** — no uninstall, no lost settings. A build signed
with a different key cannot be installed at all, which is why the keystore is
backed up separately and never committed.

### Over-the-air updates

`GET /update/check` returns the manifest; `GET /update/download` returns the
APK. Both live on whatever server the app is pointed at — the hosted backend,
a laptop on the same Wi-Fi, or the phone itself.

```jsonc
{
  "versionCode": 210,
  "versionName": "18.18",
  "file": "AxzoraOS-18.18.apk",
  "url":  "https://github.com/axzoraharry/axzora-ota/releases/download/v18.18/AxzoraOS-18.18.apk",
  "notes": "Shown inside the update dialog"
}
```

`file` and `url` are alternatives, not duplicates:

* **`file`** — the APK sits next to `update.json`. Served straight off disk,
  which is what the phone-local hub does: fastest install, and the only one
  that works with no internet connection at all.
* **`url`** — the APK is hosted elsewhere (a GitHub Release asset, which
  allows 2 GB; the repository itself caps files at 100 MB). Used when the
  local file is absent, for example on a free hosting disk.

The server prefers the local file and only redirects when it is missing, so a
phone on the same Wi-Fi never pulls a 109 MB build over mobile data.

### Local hub

A second, optional server can run on the phone or on the LAN. The HUD probes
`/health` and shows the result in the **HUB** chip; tapping it opens a panel
with the round-trip latency, a 30-sample history, and the version the hub is
currently advertising.

```
http://127.0.0.1:8787      # a hub on the phone itself
http://192.168.29.204:8787 # a hub on the LAN
```

The address is remembered in `localStorage['hr.hub']` and can be changed from
either the first-run card or the hub panel.

### HUD keyboard and gestures

| Action | Result |
| --- | --- |
| `/` | Jump to the composer |
| `↑` / `↓` | Walk back through command history (60 entries) |
| `Tab` / `Enter` | Accept a type-ahead suggestion |
| `Esc` | Dismiss the suggestion list |
| Tap a bubble | Copy that single line |
| `⤓` | Copy the whole transcript |

Ten one-tap chips sit under the diagnostics row — Battery, Time, Where, Light,
Alarm, Timer, Screen, Alerts, Music, Memory — each one sending the command the
assistant already understands.

### Troubleshooting

**HUB shows DOWN.** Nothing is listening at that address, or the device is on
a different network. Open the hub panel, correct the address, press *Test*.
The dot stays grey — not red — until an address has been probed at least once.

**"Copy blocked by WebView."** Clipboard access needs a user gesture on some
WebView versions. The HUD falls back to `document.execCommand('copy')`; long
press a bubble to select it manually if both fail.

**An update downloads but will not install.** Check that *Install unknown
apps* is allowed for AxzoraOS, and that the new build carries the same signing
key. Android refuses downgrades outright, so `versionCode` must increase.

Found an error? [Open an issue](https://github.com/axzoraharry) or
[email us](mailto:harry@axzora.com).
