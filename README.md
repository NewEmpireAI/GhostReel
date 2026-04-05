# GhostReel — Autonomous AI Content Factory

An autonomous 2-agent system that discovers viral spoken-word scripts on Instagram,
rewrites them for your brand voice, generates AI avatar videos, and publishes to
Instagram Reels — all while you sleep.

**[ghostreel.pro](https://ghostreel.pro)** · **[Watch it live](https://ghostreel.pro/live)**

## Architecture

```
┌──────────────────────────────────────────────────────────────┐
│                        Customer                              │
│                  Slack + ClickUp (phone)                     │
└──────────┬──────────────────────────────────┬────────────────┘
           │                                  │
    ┌──────▼──────┐                    ┌──────▼──────┐
    │   Scout     │                    │   Creator   │
    │  (Agent 1)  │                    │  (Agent 2)  │
    └──────┬──────┘                    └──────┬──────┘
           │                                  │
    ┌──────▼──────┐    ┌─────────┐     ┌──────▼──────┐
    │ Instagram   │    │ ClickUp │     │   Avatar    │
    │ Discovery   │    │  (SoR)  │     │  Engine     │
    │ + Whisper   │    └─────────┘     │ + Overlays  │
    └─────────────┘                    └──────┬──────┘
                                              │
                                       ┌──────▼──────┐
                                       │  Instagram  │
                                       │  Reels      │
                                       └─────────────┘
```

### The 2 Agents

| Agent | Role | Schedule |
|-------|------|----------|
| **Scout** | Discovers viral talking-head reels, transcribes, scores by engagement | 2:00 AM daily + ad-hoc |
| **Creator** | Rewrites scripts for brand voice, generates avatar videos, composites overlays, publishes | On demand (ClickUp trigger) |

### How It Works

1. **Scout** scans Instagram hashtags nightly for high-performing talking-head reels
2. Filters for original audio (speech, not music), 1,000+ likes, 15-90 seconds
3. Transcribes via Whisper, scores by viral potential, posts to ClickUp
4. **You** review scripts on your phone (ClickUp) and promote the best ones
5. **Creator** rewrites the script for your brand voice
6. Generates an AI avatar video delivering the adapted script
7. Composites branded overlays, captions, and CTA
8. You approve in Slack → auto-publishes to Instagram Reels

### Customer Control

Everything happens on your phone via **Slack** and **ClickUp**. No dashboard. No computer required.

| You say in Slack | What happens |
|-----------------|-------------|
| *paste a reel URL* | Scout processes in 30 seconds → ClickUp task |
| `promote GR-4821` | Script enters production pipeline |
| `default` | Use your default avatar |
| *send a photo* | Creator makes a custom avatar from your face |
| `approve` | Video publishes to Instagram |
| `add hashtag #saas` | Scout adds to nightly discovery |

Every interaction references a **GR ID** — one universal identifier across all systems.

### Pipeline

```
Instagram → Scout → ClickUp → Creator → Avatar Engine → Overlays → Instagram Reels
                      ↑                                              ↓
                   Customer                                      Published
                (Slack + ClickUp)
```

### Stack

- **Orchestration:** OpenClaw on DigitalOcean Droplets
- **Task Management:** ClickUp (document of record)
- **Communication:** Slack (customer control layer)
- **Discovery:** Instagram hashtag analysis + Whisper transcription
- **Video:** AI avatar generation + branded overlay compositing
- **Distribution:** Metricool → Instagram Reels (TikTok, YouTube, Facebook planned)

### Managed Hosting

Each customer gets a dedicated DigitalOcean Droplet with their own agents, their own ClickUp workspace, and their own Slack channels. Fully isolated. Fully autonomous.

- **$500-750/month** — managed hosting, skill maintenance, updates
- **$1,500-2,500 one-time** — self-hosted skill package (bring your own OpenClaw)

### Built by SetupClaw.Tech

GhostReel is built by [Brian MacDonald](https://github.com/brianxmacdonald), creator of the SetupClaw AIOS — a 6-agent AI workforce deployed on OpenClaw for small-to-midsize businesses.

**[Get GhostReel →](https://www.ghostreel.pro)**

---

*GhostReel v0.1.0 — April 2026*
