# Nova — YouTube Growth Agent for OpenClaw

Nova is an AI agent that handles your YouTube content strategy.
She researches what's working in your niche, learns your voice, interviews you for ideas, and writes full scripts with SEO packages.

Built with [OpenClaw](https://openclaw.ai). Takes about 10 minutes to set up.

---

## What Nova Does

- **Monitors competitor channels** for outlier videos (2x+ their average views)
- **Learns your voice** from your transcripts and past scripts
- **Interviews you** before generating ideas (real experience > thin air ideas)
- **Writes full scripts** in your voice — not generic YouTube-advice voice
- **Delivers a full SEO package** with every script: title variants, description, tags, chapters, thumbnail concept

## Results (the creator who built this)

- 1,010 subs → 3,010 in 4 weeks
- Hit YouTube monetization threshold (1K subs + 4K watch hours)
- Video prep time cut from 4-6 hours to ~1 hour per video

---

## Requirements

- [OpenClaw](https://openclaw.ai) installed and running
- An API key for any supported model (Claude, GPT-4, Gemini — all work)
- A YouTube channel (any size, any niche)

---

## Installation

### Step 1 — Clone this repo

```bash
git clone https://github.com/sharbel/nova-youtube-agent.git
```

### Step 2 — Move the skill into OpenClaw

```bash
mv nova-youtube-agent ~/clawd/skills/
```

That's it. OpenClaw auto-discovers skills in the `~/clawd/skills/` directory.

### Step 3 — Fill in your config

Open `~/clawd/skills/nova-youtube-agent/config.md` and fill in:

- Your channel name and URL
- Your niche and target audience
- Your voice description (how you naturally talk)
- 5-10 competitor channels to monitor
- Your core topics
- Anything to avoid

See `example-config.md` for a real example.

### Step 4 — Run Nova

In your OpenClaw chat, just say:

```
Hey Nova, I want to generate some video ideas for this week.
```

Or:

```
Nova, analyze what's working in my niche and suggest 3 video ideas.
```

Nova will read your config, research your competitors, and ask you a few interview questions before generating ideas.

---

## How to Use Nova

### Generate video ideas
```
Nova, I want to make a video this week. Interview me and let's find a good idea.
```

### Get a full script
```
Nova, write a full script for [idea/title]. Use my voice from the config.
```

### Analyze a competitor
```
Nova, look at [channel URL] and tell me what's working for them right now.
```

### Review a video's performance
```
Nova, my last video got [X] views. Here's the data: [paste analytics]. What should I do differently?
```

---

## File Structure

```
nova-youtube-agent/
├── README.md           ← You're reading this
├── SKILL.md            ← Nova's instructions (don't edit unless you want to change her behavior)
├── config.md           ← Fill this in with your details
└── example-config.md   ← Real example for reference
```

---

## Customizing Nova

The only file you need to edit is `config.md`.

If you want to change how Nova behaves (her research process, output format, script structure), edit `SKILL.md`. It's plain English — no code.

---

## Frequently Asked Questions

**Does this work for any niche?**
Yes. Nova uses your `config.md` to calibrate to your niche. It works for tech, fitness, finance, cooking, gaming — anything.

**Do I need to be technical?**
No. If you can install OpenClaw and edit a text file, you're set.

**Does Nova post videos for me?**
No. Nova handles strategy and scripts. Filming and uploading stays with you.

**What model does Nova use?**
Whatever model you have configured in OpenClaw. Claude Sonnet and GPT-4o both work well.

**Can I use this without OpenClaw?**
Nova is built for OpenClaw. You could adapt `SKILL.md` as a system prompt for any chat interface, but you'd lose the skills/memory integration.

---

## About

Nova was built by [Sharbel](https://youtube.com/@sharbel) while trying to hit 10,000 YouTube subscribers in 2026.

The video that goes with this repo: [The AI Agent That Got Me YouTube Monetized](https://youtu.be/[VIDEO_ID])

If this helps you, star the repo and subscribe to the channel. More agent builds coming.

---

## License

MIT — free to use, modify, and share.
