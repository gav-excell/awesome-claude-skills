# Head of Content — Starter Kit

Turnkey folder: copy this whole directory into the root of any project and you're ready to run content research once your API keys are in place.

## What's in here

```
.claude/skills/     the 6 Head of Content skills, already wired to each other
.claude/context/    fill these in with the accounts/channel you want researched
.env.example        copy to .env and add your keys
requirements.txt     python deps
```

## Setup

1. Copy this folder's contents into your project root (merge if `.claude/` already exists):
   ```bash
   cp -r starter-kit/. /path/to/your-project/
   ```
2. Install Python deps:
   ```bash
   pip install -r requirements.txt
   ```
3. Get your API keys and fill in `.env` (copy from `.env.example`):
   - `APIFY_TOKEN` — [console.apify.com](https://console.apify.com/?fpr=ih20xe) (X, Instagram, TikTok scraping)
   - `TUBELAB_API_KEY` — [tubelab.net](https://tubelab.net/?ref=brad) (YouTube outlier detection)
   - `GEMINI_API_KEY` — [aistudio.google.com/api-keys](https://aistudio.google.com/api-keys) (video analysis)
4. Edit the placeholder tables in `.claude/context/` with the real accounts/channel/niche you want researched:
   - `x-accounts.md`, `instagram-accounts.md`, `tiktok-accounts.md` — add `@username` rows
   - `youtube-channel.md` — describe your channel and niche

## Run it

Open the project in Claude Code and just ask, e.g.:

- "Run Instagram research on my tracked accounts"
- "What's working on TikTok right now?"
- "Create a content plan across all platforms" (runs all four research skills + generates playbooks)

Output lands in timestamped run folders like `instagram-research/2026-01-01_120000/report.md`, and `content-plans/{timestamp}/` for the full cross-platform plan.
