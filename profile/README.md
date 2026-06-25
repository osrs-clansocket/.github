<div align="center">

<img src="https://avatars.githubusercontent.com/u/291145122?v=4" width="120" height="120" alt="ClanSocket" />

# ClanSocket

**Live, open-source platform for Old School RuneScape clans.**

Real-time clan and gameplay telemetry, streamed from RuneLite to a multi-tenant
clan dashboard at [clansocket.com](https://clansocket.com) — consent-first, over a single WebSocket.

<br />

[![Website](https://img.shields.io/badge/website-clansocket.com-1f6feb?style=for-the-badge&logo=googlechrome&logoColor=white)](https://clansocket.com)
[![Plugin Hub installs](https://img.shields.io/endpoint?url=https://api.runelite.net/pluginhub/shields/installs/plugin/clansocket&style=for-the-badge)](https://runelite.net/plugin-hub/show/clansocket)
[![Plugin Hub rank](https://img.shields.io/endpoint?url=https://api.runelite.net/pluginhub/shields/rank/plugin/clansocket&style=for-the-badge)](https://runelite.net/plugin-hub/show/clansocket)
[![License: BSD-2-Clause](https://img.shields.io/badge/license-BSD--2--Clause-3fb950?style=for-the-badge)](https://opensource.org/license/bsd-2-clause)

</div>

---

## What is ClanSocket?

ClanSocket turns your in-game OSRS clan into a live web dashboard. A RuneLite
plugin streams real-time telemetry and clan chat over a single WebSocket to
[clansocket.com](https://clansocket.com), where **every clan is its own tenant** —
resolved automatically from your in-game clan name.

It is **consent-first by design**: telemetry only flows once a clan is claimed,
behind per-stream privacy gates, explicit in-game consent prompts, and
GDPR-grade data rights. Events for unclaimed clans are dropped silently on the
server.

Beyond live tracking, the dashboard brings Wise Old Man integration, deep
Discord sync (including bring-your-own-bot), passwordless passkey sign-in, and
**Varez** — a built-in AI assistant.

<div align="center">

| | |
| --- | --- |
| 🗺️ **Live world map & roster** | your clan across Gielinor in real time, with live presence |
| 📡 **24 telemetry streams** | XP, skills, combat, loot, collection log, clues, slayer, quests, pets… |
| 🔒 **Consent-first privacy** | per-stream gates, in-game consent prompts, GDPR data rights |
| 🔗 **Wise Old Man** | native WOM integration |
| 🤖 **Discord** | full guild sync + bring-your-own-bot |
| 🔑 **Passkey sign-in** | WebAuthn, no passwords |
| ✨ **Varez** | a built-in AI assistant |
| 🧊 **3D clan icons** | Voxlab — a three.js engine + editor for clan-icon authoring |

</div>

<details>
<summary><b>All 24 telemetry streams</b></summary>

XP gains · Skills snapshot · Combat · Vitals · Prayer · Stat boosts · Status
effects · Location · Inventory · Bank · Loot · Pet drops · Clues · Collection
log · Combat achievements · Diaries · Quests · Slayer · Farming patches · Rune
pouch · Menu actions · Clan chat · Clan roster · Death

</details>

## How it fits together

```text
 RuneLite plugin  ──wss://ws.clansocket.com/data──▶  ClanSocket server  ──▶  clan dashboard
 telemetry + clan chat          single WebSocket            routes per clan tenant
```

The plugin is the client; the app is the platform. Telemetry and clan chat ride
the same transport, and the server resolves each payload to the correct clan
tenant from the player's in-game clan name.

## Stack

<div align="center">

![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?logo=vite&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?logo=express&logoColor=white)
![Discord.js](https://img.shields.io/badge/Discord.js-5865F2?logo=discord&logoColor=white)
![Electron](https://img.shields.io/badge/Electron-47848F?logo=electron&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?logo=openjdk&logoColor=white)
![Three.js](https://img.shields.io/badge/Three.js-000000?logo=threedotjs&logoColor=white)
![OpenGL](https://img.shields.io/badge/OpenGL-5586A4?logo=opengl&logoColor=white)
![nginx](https://img.shields.io/badge/nginx-009639?logo=nginx&logoColor=white)

</div>

The core app is a single npm-workspaces monorepo: a Vite + TypeScript dashboard
SPA (DOM-factory rendering, plain CSS — no framework), an Express server, a
Discord.js bot, and an Electron desktop wrapper. The RuneLite plugin is Java;
OSRS item/object/NPC icons are rendered offline through LWJGL3 / OpenGL.

## Public repositories

| Repository | What it is |
| --- | --- |
| [`clansocket-app`](https://github.com/osrs-clansocket/clansocket-app) | The platform — dashboard SPA, server, Discord bot, Electron wrapper |
| [`clansocket-plugin`](https://github.com/osrs-clansocket/clansocket-plugin) | The RuneLite client plugin (Plugin Hub: **ClanSocket**) |
| [`clansocket-error-screens`](https://github.com/osrs-clansocket/clansocket-error-screens) | Branded interactive error pages + minigames, served at the edge |
| [`clansocket-osrs-cache-extractor`](https://github.com/osrs-clansocket/clansocket-osrs-cache-extractor) | OSRS cache extractor + icon renderer (LWJGL3 / OpenGL) |
| [`clansocket-voxlab`](https://github.com/osrs-clansocket/clansocket-voxlab) | Voxlab — standalone three.js 3D engine + editor for clan icons |
| [`clansocket-asset-optimization`](https://github.com/osrs-clansocket/clansocket-asset-optimization) | Asset and map-tile optimization pipeline |
| [`clansocket-deploy`](https://github.com/osrs-clansocket/clansocket-deploy) | Droplet deployment and nginx automation |

## Get started

- **Players** — install **ClanSocket** from the RuneLite Plugin Hub
  (`Configure → Plugin Hub → search "ClanSocket"`), enable it, and log in on a
  character in your clan.
- **Clan owners** — claim your clan at [clansocket.com](https://clansocket.com)
  so its telemetry can flow.
- **Developers** — every public repository is BSD-2-Clause; start with
  [`clansocket-app`](https://github.com/osrs-clansocket/clansocket-app).

## License

[BSD-2-Clause](https://opensource.org/license/bsd-2-clause).

<div align="center"><sub>Built for Old School RuneScape clans · <a href="https://clansocket.com">clansocket.com</a></sub></div>
