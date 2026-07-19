# Head of Content

A social media content research skill pack. Identifies high-performing content across X/Twitter, Instagram, YouTube, and TikTok, analyzes viral patterns with AI, and generates actionable content plans and platform playbooks.

## Skills

- **[x-research](./x-research/)** - Find outlier tweets from tracked accounts using Apify's X/Twitter scraper.
- **[instagram-research](./instagram-research/)** - Find outlier posts/reels from tracked Instagram accounts using Apify.
- **[youtube-research](./youtube-research/)** - Find outlier videos using TubeLab's outlier detection API.
- **[tiktok-research](./tiktok-research/)** - Find outlier videos from tracked TikTok accounts using Apify.
- **[video-content-analyzer](./video-content-analyzer/)** - Analyze short-form videos with Gemini AI to extract hooks, structure, and replicable formulas. Used by the research skills above.
- **[content-planner](./content-planner/)** - Orchestrates all four research skills in parallel, then aggregates findings into cross-platform content ideas and platform-specific playbooks.

## Prerequisites

- Python 3.8+ with `apify-client`, `google-genai`, `requests`
- **Apify** token (X, Instagram, TikTok scraping) - [console.apify.com](https://console.apify.com/?fpr=ih20xe)
- **TubeLab** API key (YouTube outlier detection) - [tubelab.net](https://tubelab.net/?ref=brad)
- **Gemini** API key (video analysis) - [aistudio.google.com](https://aistudio.google.com/api-keys)

Set these as environment variables or in a `.env` file at your project root:

```bash
TUBELAB_API_KEY=your-api-key-here
APIFY_TOKEN=your-apify-token-here
GEMINI_API_KEY=your-key
```

Each research skill also expects a tracked-accounts file in `.claude/context/` (e.g. `.claude/context/instagram-accounts.md`), and `youtube-research` expects `.claude/context/youtube-channel.md` describing the channel/niche to research.

## Installation

Fastest path: copy the **[starter-kit](./starter-kit/)** folder into your project root — it already has all six skills wired up under `.claude/skills/`, placeholder context files under `.claude/context/`, and a `.env.example`. See its README for setup steps.

To install manually instead, copy the skill folders you want into your project's `.claude/skills/` directory, e.g.:

```bash
cp -r x-research instagram-research youtube-research tiktok-research video-content-analyzer content-planner /path/to/your-project/.claude/skills/
```

The skills cross-reference each other by path (e.g. `content-planner` calls the platform-specific research skills, and each research skill calls `video-content-analyzer`), so install them together under `.claude/skills/`.

**Credit:** Based on [bradautomates/head-of-content](https://github.com/bradautomates/head-of-content).
