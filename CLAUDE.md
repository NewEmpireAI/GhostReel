# CLAUDE.md — GhostReel

## What this project is

GhostReel is an autonomous AI content factory built on OpenClaw. Two agents (Scout + Creator) run on DigitalOcean Droplets, discovering viral Instagram scripts, generating AI avatar videos, and publishing — controlled via Slack and ClickUp.

## Project structure

```
GhostReel/
├── website/          # Static site → Vercel → ghostreel.pro
│   ├── index.html    # Homepage
│   ├── live.html     # /live dashboard
│   └── vercel.json   # Route config
├── .github/          # CI + templates
├── CLAUDE.md         # This file
└── README.md
```

## Development

Static HTML/CSS/JS. No build step.
- Body font: Inter
- Code font: Fira Code
- Colors: #000 background, #00ff88 green, #ff8a00 orange

```bash
cd website && python3 -m http.server 8000
```

## Deployment

Vercel auto-deploys from `website/` on push to main.
Engine (private repo) deploys to DigitalOcean Droplets.
