# 🍃 Leaf Village Legends

**A comprehensive guild contribution tracker and gamification addon for World of Warcraft (Vanilla / Classic 1.12).**

The Leaf Village Legends addon transforms our guild experience by tracking member contributions, awarding badges, managing leaderboards, and fostering community engagement — all themed around the Naruto-inspired Leaf Village guild hierarchy.

![Version](https://img.shields.io/badge/Version-10.7-green) ![Interface](https://img.shields.io/badge/Interface-1.12-blue) ![Language](https://img.shields.io/badge/Language-Lua-purple)

---

## ✨ Features

### 🏅 Leaf Points System
- **Automatic point tracking** across multiple activities: daily logins, quest completions, boss kills, dungeon runs, and grouping with guildmates.
- **Three point categories:**
  - **L (Login)** — Earned from daily logins and login streaks.
  - **G (Gameplay)** — Earned from quests, dungeons, raids, and boss kills.
  - **S (Social)** — Earned from shoutouts and guild social interactions.
- **700 LP daily cap** — A hard-coded 700 Leaf Point daily cap applies across all sources combined (login, group, quests, shoutouts). Quest completions have no separate daily cap.
- **AFK protection** — Group points are paused if you are AFK or have been inactive for 10+ minutes.
- **Alt character pooling** — Link alt characters to a main so Gameplay and Social points accumulate on one identity. Login points remain per-character.

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
- **Seasonal rewards** — Fixed gold rewards for top-placing members each season (1st: 10g, 2nd: 5g, 3rd: 3g, 4th: 2g, 5th: 1g).
- **Guild-wide syncing** via addon messaging (`GUILD` channel) — leaderboard data is shared and merged across all online members.

### 📣 Shoutout System
- Give shoutouts to guildmates for recognition.
- Shoutouts award Leaf Points to the receiver.
- Autocomplete target suggestions from the guild roster.
- Shoutout history is synced across guild members.

### 🎯 Achievement Tracking
- Integrates with the companion achievement addon (`LeafVE_AchTest`) for tracking Classic WoW achievements (professions, leveling, PvP, raids, and more).
- Per-player achievement popups with detailed progress.
- Achievement icons mapped for dozens of Classic milestones.

### 🗂️ Guild Roster & Player Cards
- View the full guild roster with rank, level, class, and online status.
- **Player Cards** display a member's Leaf Points breakdown, earned badges (with quality-colored tooltips), and activity history.
- Click any guild member to inspect their profile.

### 🔔 Notification System
- Elegant toast-style pop-up notifications for badge unlocks, point gains, and achievements.
- Configurable toggles for notification categories (points, badges, sound).
- Notification queue system so alerts never overlap.

### ⚙️ Admin Panel
Restricted to guild leadership ranks (**Hokage**, **Sannin**, **Anbu**):
- **Current Rules** — Displays all hard-coded point values and the 700 LP daily cap for quick reference.
- **Announce Weekly Standings** — Preview and announce top 5 weekly standings to the guild with gold reward amounts.
- **Player Management** — Award badges to specific players or remove all data for a player.
- Hard reset leaderboards, badges, or achievement data.
- Version check to confirm all guild members are on the same addon version.

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

### UI Tabs

The main window provides tabbed navigation:

| Tab | Description |
|-----|-------------|
| **Welcome** | How-to guide and feature overview |
| **My Stats** | Your personal Leaf Points, badges, and activity stats |
| **Roster** | Full guild member list with details |
| **Weekly** | Current week's rankings |
| **Lifetime** | All-time Leaf Points rankings |
| **Achievements** | Achievement leaderboard and tracking |
| **Badges** | Full badge collection with progress |
| **Alts** | Link alt characters to your main |
| **History** | Point earning history log |
| **Live History** | Real-time point award feed |
| **Options** | Notification and display settings |
| **Admin** | Officer/leadership tools (rank-restricted) |

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

Only **Hokage**, **Sannin**, and **Anbu** ranks can access the Admin panel and broadcast configuration changes.

---

## 📊 Point Earning Activities

| Activity | Point Type | Details |
|----------|-----------|---------|
| Daily Login | L (Login) | 20 LP once per day; streak bonuses tracked |
| Quest Completion | G (Gameplay) | 10 LP per quest turn-in (requires guildie in group, no daily cap) |
| Boss Kill | G (Gameplay) | 10 LP (dungeon) / 25 LP (raid) per recognized boss kill |
| Dungeon Completion | G (Gameplay) | 10 LP flat per dungeon completion |
| Raid Completion | G (Gameplay) | 25 LP flat per raid completion |
| Guild Grouping | G (Gameplay) | 10 LP per guildie every 20 min (AFK-protected) |
| Shoutout Received | S (Social) | 10 LP when a guildie gives you a shoutout (max 2/day given) |

**Daily cap: 700 LP total across all sources per day (hard-coded).**

---

## 🗄️ Saved Variables

| Variable | Scope | Description |
|----------|-------|-------------|
| `LeafVE_DB` | Per-Character | Points, badges, options, history, and UI settings |
| `LeafVE_GlobalDB` | Account-Wide | Shared data across all characters |

---

## 🔧 Configuration

All point values and caps are **hard-coded** and not configurable. The following values apply:

| Setting | Value |
|---------|-------|
| Daily LP Cap | 700 (total across all sources) |
| Group Points per Guildie | 10 LP every 20 min |
| Quest Points | 10 LP per turn-in (no daily cap) |
| Daily Login Points | 20 LP |
| Dungeon Boss | 10 LP |
| Raid Boss | 25 LP |
| Dungeon Completion | 10 LP |
| Raid Completion | 25 LP |
| Shoutout Points | 10 LP (giver and receiver) |
| Shoutout Max Per Day | 2 per giver |
| AFK Inactivity Threshold | 10 minutes |
| Season Reward 1st Place | 10 gold |
| Season Reward 2nd Place | 5 gold |
| Season Reward 3rd Place | 3 gold |
| Season Reward 4th Place | 2 gold |
| Season Reward 5th Place | 1 gold |

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
