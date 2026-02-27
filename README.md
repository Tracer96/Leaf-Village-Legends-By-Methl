# 🍃 Leaf Village Legends

**A comprehensive guild contribution tracker and gamification addon for World of Warcraft (Vanilla / Classic 1.12).**

The Leaf Village Legends addon transforms our guild experience by tracking member contributions, awarding badges, managing leaderboards, and fostering community engagement — all themed around the Naruto-inspired Leaf Village guild hierarchy.

![Version](https://img.shields.io/badge/Version-10.8-green) ![Interface](https://img.shields.io/badge/Interface-1.12-blue) ![Language](https://img.shields.io/badge/Language-Lua-purple)

---

## ✨ Features

### 🏅 Leaf Points System
- **Automatic point tracking** across multiple activities: daily logins, quest completions, boss kills, dungeon runs, and grouping with guildmates.
- **Three point categories:**
  - **L (Login)** — Earned from daily logins and login streaks.
  - **G (Gameplay)** — Earned from quests, dungeons, raids, and boss kills.
  - **S (Social)** — Earned from shoutouts and guild social interactions.
- **700 LP daily cap** — All Leaf Points from all sources are governed by a single unified 700 LP daily cap.
- **Alt character pooling** — Link alt characters to a main so Gameplay and Social points accumulate on one identity. Login points remain per-character.

### 🔔 Toast Notifications (Always-On)
Every LP award shows a contextual toast notification describing exactly why points were earned:
- `+20 LP — Daily login`
- `+10 LP — Boss kill: Ragnaros`
- `+10 LP — Quest completed`
- `+10 LP — Group activity`

Notifications fire unconditionally — there is no suppression logic.

### 🛡️ AFK Detection for Group Points
Group points are **not** awarded when the player is AFK or idle:
- The addon tracks player activity via combat events, zone changes, chat messages, and looting.
- If `UnitIsAFK("player")` is true **or** the player has been inactive for **10 minutes**, the group point tick is skipped with a chat message.
- AFK detection applies **only** to group points — boss kills, quests, logins, and shoutouts are unaffected.

### 🎖️ Badge Collection
Over 20 collectible badges across 6 categories, each with WoW-style quality tiers:

| Quality | Color | Examples |
|---------|-------|----------|
| ⬜ **Common** | Gray | First Steps, Team Player, Generous Soul |
| 🟩 **Uncommon** | Green | Dedicated, Groupie, Raider, Well Known |
| 🟦 **Rare** | Blue | Truly Dedicated, Social Butterfly, Core Member, Raid Veteran |
| 🟪 **Epic** | Purple | Guild Hero, Guild Elite |
| 🟧 **Legendary** | Orange | Hokage Legend, One Year Legend |

**Badge categories include:**
- **Activity** — Login streaks and consistency.
- **Social** — Grouping with guildmates.
- **Recognition** — Giving and receiving shoutouts.
- **Milestones** — Total Leaf Point thresholds.
- **Raids** — Raid attendance tracking.
- **Loyalty** — Time spent in the guild (30 days, 90 days, 1 year).

Badges are **auto-tracked** and awarded with in-game toast notifications, chat announcements, and clickable badge hyperlinks.

### 🏆 Leaderboards
- **All-Time Leaderboard** — Lifetime total Leaf Points across all members.
- **Weekly Leaderboard** — Resets each week for competitive seasons.
- **Achievement Leaderboard** — Tracks completed in-game achievements.
- **Seasonal rewards** — Configurable gold rewards for top-placing members each season.
- **Guild-wide syncing** via addon messaging (`GUILD` channel) — leaderboard data is shared and merged across all online members.

### 📣 Shoutout System
- Give shoutouts to guildmates for recognition via `/lve shoutout <PlayerName> [reason]`.
- Shoutouts award Leaf Points to both the receiver and the giver.
- Autocomplete target suggestions from the guild roster.
- Shoutout history is synced across guild members.
- The Shoutouts tab has been removed from the tab bar to keep the UI clean, but the shoutout system remains fully functional via the slash command.

### 🎯 Achievement Tracking
- Integrates with the companion achievement addon (`LeafVE_AchTest`) for tracking Classic WoW achievements (professions, leveling, PvP, raids, and more).
- Per-player achievement popups with detailed progress.
- Achievement icons mapped for dozens of Classic milestones.

### 🗂️ Guild Roster & Player Cards
- View the full guild roster with rank, level, class, and online status.
- **Player Cards** display a member's Leaf Points breakdown, earned badges (with quality-colored tooltips), and activity history.
- Click any guild member to inspect their profile.

### ⚙️ Admin Panel
Restricted to guild leadership ranks (**Hokage**, **Sannin**, **Anbu**):
- **Current Rules section** — Read-only display of all active rules (daily LP cap, quest cap status, AFK timeout, point values).
- **Announce Weekly Standings** — Preview the top 5 weekly earners and broadcast them to guild chat with gold/silver/bronze formatting.
- **Player Management** — Search for any player by name and view their today/weekly/all-time LP stats.
- **Check Addon Versions** — Ping all online guild members and view their addon version in a popup.
- Hard reset leaderboards, badges, or achievement data.
- Award or remove badges from individual players.

### 🔗 Data Sync
- Peer-to-peer leaderboard syncing over the `GUILD` addon message channel.
- Automatic resync requests on login or UI open.
- Cooldown-protected broadcasts to prevent channel spam.
- Badge, shoutout, and achievement data all sync independently.

---

## 📦 Installation

1. **Download** or clone this repository.
2. Copy the `Leaf-Village-Legends-By-Methl` folder into your WoW addons directory:
   ```
   World of Warcraft/Interface/AddOns/
   ```
   > **Note:** The folder placed inside `AddOns/` must contain `LeafVillageLegends.toc` and `LeafVillageLegends.lua` at its root. Rename the folder if needed so WoW can detect it (e.g., `LeafVillageLegends`).
3. Restart WoW or type `/console reloadui` to load the addon.
4. Verify it appears in the **AddOns** list on the character select screen.

---

## 🚀 Usage

### Slash Commands

| Command | Description |
|---------|-------------|
| `/lve` | Toggle the main Leaf Village Legends UI |
| `/lve bigger` | Increase UI scale |
| `/lve smaller` | Decrease UI scale |
| `/lve wider` | Increase UI width |
| `/lve narrower` | Decrease UI width |
| `/lve shoutout <Player> [reason]` | Give a shoutout (and LP) to a guild member |

### UI Tabs

The main window provides tabbed navigation in the following order:

| # | Tab | Description |
|---|-----|-------------|
| 1 | **Welcome** | How-to guide and feature overview |
| 2 | **My Stats** | Your personal Leaf Points, badges, and activity stats |
| 3 | **Roster** | Full guild member list with details |
| 4 | **Weekly** | Current week's LP rankings |
| 5 | **Lifetime** | All-time Leaf Points rankings |
| 6 | **Achievements** | Achievement leaderboard and tracking |
| 7 | **Badges** | Full badge collection with progress |
| 8 | **Alts** | Link alt characters to your main |
| 9 | **History** | Point earning history log |
| 10 | **Live History** | Real-time feed of recent LP events for all players |
| 11 | **Options** | Notification and display settings |
| 12 | **Admin** | Officer/leadership tools (rank-restricted) |

> **Note:** The Shoutouts tab has been removed from the tab bar. Use `/lve shoutout` to give shoutouts.

### Minimap Button
A minimap icon provides quick access to toggle the UI.

---

## 🏰 Guild Rank Hierarchy

Leaf Village Legends uses a Naruto-themed rank system for access control:

| Rank | Access Level |
|------|-------------|
| **Hokage** | Full admin access |
| **Sannin** | Full admin access |
| **Anbu** | Full admin access |
| **Jonin** | Standard member access |
| **Chunin** | Standard member access |
| **Genin** | Standard member access |
| **Academy Student** | Standard member access |

Only **Hokage**, **Sannin**, and **Anbu** ranks can access the Admin panel.

---

## 📊 Point Earning Activities

| Activity | Point Type | Amount | Daily Limit |
|----------|-----------|--------|-------------|
| Daily Login | L (Login) | 20 LP | Once per day per character |
| Quest Completion | G (Gameplay) | 10 LP | **Unlimited** (quest cap removed) |
| Boss Kill | G (Gameplay) | 10 LP (dungeon) / 25 LP (raid) | Governed by 700 LP daily cap |
| Dungeon Completion | G (Gameplay) | 10 LP | Governed by 700 LP daily cap |
| Raid Completion | G (Gameplay) | 25 LP | Governed by 700 LP daily cap |
| Guild Grouping | G (Gameplay) | 10 LP per guildie per 20 min | Governed by 700 LP daily cap; skipped if AFK |
| Shoutout Received | S (Social) | 10 LP | Governed by 700 LP daily cap |

**All sources combined are capped at 700 LP per day.** Quest points are no longer individually capped.

---

## 🛡️ AFK Detection Details

Group points are skipped when either condition is true:
1. `UnitIsAFK("player")` returns true (WoW AFK flag is set)
2. The player has not had any tracked activity for **10 minutes** (600 seconds)

**Tracked activity events:**
- Entering/leaving combat (`PLAYER_REGEN_DISABLED`, `COMBAT_LOG_EVENT_UNFILTERED`)
- Zone changes (`ZONE_CHANGED_NEW_AREA`)
- Chat messages (`CHAT_MSG_SAY`, `CHAT_MSG_PARTY`, `CHAT_MSG_GUILD`, `CHAT_MSG_YELL`)
- Opening loot (`LOOT_OPENED`)

---

## 🗄️ Saved Variables

| Variable | Scope | Description |
|----------|-------|-------------|
| `LeafVE_DB` | Per-Character | Points, badges, options, history, and UI settings |
| `LeafVE_GlobalDB` | Account-Wide | Shared data across all characters |

---

## 🔧 Configuration

| Setting | Value |
|---------|-------|
| Daily LP Cap | **700 LP** (all sources, unified) |
| Quest Daily Cap | **Disabled** (unlimited quest LP) |
| AFK Timeout | **10 minutes** inactivity |
| Group Min Time | 300 seconds (5 min) |
| Group Cooldown | 900 seconds (15 min) |
| Group Point Interval | 20 minutes |
| Daily Login Points | 20 LP |
| Quest Points | 10 LP per completion |
| Dungeon Boss Points | 10 LP |
| Raid Boss Points | 25 LP |
| Dungeon Completion | 10 LP |
| Raid Completion | 25 LP |

---

## 🐛 Compatibility

- **WoW Interface:** 1.12 (Vanilla / Classic)
- **Lua Version:** 5.0 compatible (includes `string.match` polyfill for Lua 5.0 environments)
- **Optional Dependencies:** None required; integrates with `LeafVE_AchTest` addon if present.

---

## 📝 License

This project is provided as-is for use within the World of Warcraft Classic community. See the repository for any additional license information.

---

## 🤝 Contributing

Contributions, bug reports, and feature requests are welcome! Feel free to open an issue or submit a pull request.

---

*May the Will of Fire burn bright in your guild.* 🔥🍃
