# qlf-duoq-bot
Discord bot for QLF DuoQ Challenge — League of Legends
# ⚔️ QLF DuoQ Challenge Bot

> Discord bot for managing a competitive League of Legends DuoQ challenge between community members.

---

## 📖 Overview

**QLF DuoQ Challenge** is a community-driven competitive event where teams of 2 players (duos) compete on fresh League of Legends accounts over a limited period (typically 1 week).

The bot automates all challenge management directly inside Discord:
- 📊 Automatic LP tracking via Riot Games API (every 6 hours)
- 🏆 Live leaderboard updated in real-time
- ⚔️ Private team channels with restricted access
- ✅ Bonus / 💀 Malus system managed by referees
- 🎮 Daily challenges published automatically
- ⚖️ Sanctions and history logging

---

## 🎯 Use Case

This bot is designed for small to mid-size communities (10–100 players) who want to organize a structured DuoQ challenge with:
- Automated score tracking
- Fair referee management
- Community engagement through daily challenges and announcements

The challenge is open to community members recruited via social media (TikTok, Discord).

---

## 🔧 Tech Stack

- **Runtime**: Node.js 18+
- **Discord Library**: discord.js v14
- **API**: Riot Games Official API (account-v1, summoner-v4, league-v4)
- **Region support**: EUW, EUNE, NA, KR, BR, TR, OCE

---

## ⌨️ Commands

| Command | Access | Description |
|---|---|---|
| `/setup` | Admin | Generate full server structure |
| `/register` | Everyone | Link your LoL account via OP.GG/DPM link |
| `/createduo` | Referee | Create a team with private channels |
| `/setlp` | Referee | Manually update a duo's LP |
| `/bonus` | Referee | Award bonus points |
| `/malus` | Referee | Apply penalty points |
| `/challenge` | Referee | Post the daily challenge |
| `/leaderboard` | Everyone | View full standings |
| `/score` | Everyone | View a team's score |
| `/annonce` | Referee | Post official announcement |
| `/sanction` | Referee | Issue official sanction |
| `/refreshlp` | Referee | Force LP refresh from Riot API |
| `/journal` | Referee | View action history |

---

## 📊 Scoring System

```
Total Score = (LP Player 1 + LP Player 2) + Bonus Points − Penalty Points
```

LP values are fetched automatically from the **Riot Games API** every **6 hours**.

---

## 🌍 Riot API Usage

This bot uses the following Riot Games API endpoints:

| Endpoint | Usage |
|---|---|
| `account-v1` `/accounts/by-riot-id/{gameName}/{tagLine}` | Resolve Riot ID → PUUID |
| `summoner-v4` `/summoners/by-puuid/{puuid}` | Resolve PUUID → Summoner ID |
| `league-v4` `/entries/by-summoner/{summonerId}` | Fetch ranked LP data |

**Request volume estimate:**
- ~10–100 registered players
- Refresh every 6 hours = ~4 full refreshes per day
- Max ~400 API calls/day (well within rate limits)

All data is used solely to display LP rankings within the private Discord community.

---

## 🔐 Privacy & Compliance

- No user data is stored permanently (in-memory only during bot runtime)
- Only public ranked data is accessed (no private match details)
- Bot is restricted to a single Discord server
- Fully compliant with Riot Games Developer Policies

---

## 📄 License

MIT License — Open source, community project.

---

*This project is not endorsed by Riot Games and doesn't reflect the views or opinions of Riot Games.*
