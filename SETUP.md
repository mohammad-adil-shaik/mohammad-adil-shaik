# Setup Guide

This repository powers the GitHub profile README for **@mohammad-adil-shaik**.
Everything is already committed and works out of the box. This guide explains
how each piece works and how to keep it running.

## Repository Structure

```
mohammad-adil-shaik/
├─ README.md                      # The profile README (renders on your profile)
├─ SETUP.md                       # This file
├─ assets/
│  └─ background.svg              # Animated Tokyo Night code-card (About Me)
└─ .github/
   └─ workflows/
      └─ snake.yml                # Generates the contribution snake animation
```

## 1. The Contribution Snake

The snake animation is produced by the `Platane/snk` action defined in
`.github/workflows/snake.yml`.

**How it runs**
- Automatically every 12 hours (cron).
- On every push to `main`.
- Manually from the **Actions** tab → *Generate Contribution Snake* → **Run workflow**.

**What it does**
It renders three files and pushes them to a dedicated `output` branch:
- `github-snake.svg` (light)
- `github-snake-dark.svg` (dark)
- `ocean.gif`

The README references these via:
`https://raw.githubusercontent.com/mohammad-adil-shaik/mohammad-adil-shaik/output/github-snake.svg`

### One-time permission check
If the workflow fails to push the `output` branch:
1. Go to **Settings → Actions → General**.
2. Under **Workflow permissions**, select **Read and write permissions**.
3. Save, then re-run the workflow.

## 2. README Widgets

All widgets use actively maintained, free providers — no API keys needed:

| Widget | Provider |
|---|---|
| Header / Footer wave | capsule-render.vercel.app |
| Typing animation | readme-typing-svg.demolab.com |
| Profile views | komarev.com |
| Followers badge | img.shields.io |
| GitHub stats / Top languages | github-readme-stats.vercel.app |
| Streak stats | streak-stats.demolab.com |
| Activity graph | github-readme-activity-graph.vercel.app |
| Trophies | github-profile-trophy.vercel.app |
| Skill icons | skillicons.dev |
| Contribution snake | github (this repo, output branch) |

> Note: The stats providers count **public** contributions by default. To include
> private contribution counts, the `github-readme-stats` instance would need a
> personal access token — optional and not required for the profile to work.

## 3. Updating Content

Just edit `README.md` and commit to `main`. The push automatically re-triggers
the snake workflow, so the animation stays current.

## 4. Customization Tips

- **Colors**: The palette is Tokyo Night — `#1a1b27`, `#24283b`, `#7aa2f7` (blue),
  `#bb9af7` (purple), `#9ece6a` (green), `#f7768e` (red).
- **Typing lines**: Edit the `lines=` query parameter in the Typing SVG URL.
- **Trophy theme**: `theme=tokyonight` in the trophy URL.

---

Built as a premium, recruiter-focused profile. No broken links, no deprecated widgets.
