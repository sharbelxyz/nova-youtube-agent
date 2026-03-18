# Nova — YouTube Growth Agent for OpenClaw

Nova is an AI agent that handles your YouTube content strategy end-to-end.
Competitor research. Channel analysis. Video ideas. Scripts. Performance tracking. Feedback loop.

Built with [OpenClaw](https://openclaw.ai). Self-installs in under 5 minutes.

---

## What Nova Does

| System | What It Does |
|--------|-------------|
| 🔍 Competitor Scan | Finds outlier videos (2x+ avg) across your competitor channels and extracts what's working |
| 📊 Channel Analysis | Analyzes your own videos to find patterns in what performs and what doesn't |
| 💡 Idea Generation | Interviews you first, then generates research-backed ideas grounded in real experience |
| 📝 Script Writing | Full scripts in your voice with a complete SEO package (title variants, description, tags, chapters, thumbnail) |
| 📈 Performance Logging | Tracks how each video does after publishing |
| 🔄 Feedback Loop | Logs every approval and rejection with reasons — Nova never repeats a rejected angle |
| 🧠 Learning Loop | Reads all memory files before every session — gets smarter the longer you use it |

---

## Results (the creator who built this)

- 1,010 subs → 3,010 in 4 weeks using Nova
- Hit YouTube monetization (1K subs + 4K watch hours)
- Video prep cut from 4-6 hours to ~1 hour per video

---

## Requirements

- [OpenClaw](https://openclaw.ai) installed
- Any supported AI model (Claude, GPT-4o, Gemini — all work)
- A YouTube channel (any size, any niche)

---

## Installation — 2 Ways

### Option A: Send the repo link to OpenClaw (easiest)

Just tell your OpenClaw agent:

```
Install this skill: https://github.com/sharbelxyz/nova-youtube-agent
```

OpenClaw will clone the repo, install the skill, and Nova will run onboarding automatically.

### Option B: Manual install

```bash
# Clone into your OpenClaw skills directory
git clone https://github.com/sharbelxyz/nova-youtube-agent.git ~/clawd/skills/nova-youtube-agent
```

Then tell your OpenClaw:
```
Install Nova
```

Nova will detect the new skill and walk you through 10 onboarding questions.

---

## Onboarding

First time you run Nova, she'll ask you 10 questions:

1. Your name and channel name
2. Channel URL
3. Your niche (one sentence)
4. Your target audience
5. Your subscriber goal + deadline
6. Current subscriber count
7. How you naturally talk (voice description)
8. 5-10 competitor channels to monitor
9. What to avoid (flops, off-brand formats)
10. Your top 2-3 videos (optional — for voice calibration)

Takes about 5 minutes. Nova writes your answers to `config.md` automatically. You never do this again.

---

## How to Use Nova

After setup, just talk to her naturally:

```
Nova, scan my competitors for what's working this week
```
```
Nova, I want to make a video — interview me and let's find an idea
```
```
Nova, write a full script for [idea]
```
```
Nova, my last video got 4,200 views — log the performance
```
```
Nova, show me the feedback loop — what patterns have you noticed?
```

---

## How the Learning Loop Works

Nova keeps a `memory/` folder with:
- `approved-ideas.md` — every idea you said yes to
- `rejected-ideas.md` — every idea you rejected + why
- `performance-log.md` — every video's stats after publishing
- `competitor-scans.md` — history of niche research
- `voice-examples.md` — your voice patterns and phrases

Before every session, Nova reads all of these. She never repeats a rejected angle. She weights suggestions toward what's actually performed on your channel. The longer you use her, the better the ideas.

---

## File Structure

```
nova-youtube-agent/
├── README.md              ← You're reading this
├── SKILL.md               ← Nova's full instructions (all 7 systems)
├── config.md              ← Auto-created during onboarding (gitignored)
├── example-config.md      ← Real example for reference
└── memory/
    ├── approved-ideas.md  ← Auto-populated (gitignored)
    ├── rejected-ideas.md  ← Auto-populated (gitignored)
    ├── performance-log.md ← Auto-populated (gitignored)
    ├── competitor-scans.md← Auto-populated (gitignored)
    ├── channel-analysis.md← Auto-populated (gitignored)
    └── voice-examples.md  ← Auto-populated (gitignored)
```

Note: `config.md` and all `memory/` files are gitignored. Your personal data never leaves your machine.

---

## Customizing Nova

- To change your channel details: edit `config.md`
- To change how Nova behaves: edit `SKILL.md` (plain English, no code)
- To reset and start fresh: delete `config.md` and all `memory/` files, then run "Install Nova" again

---

## FAQ

**Does this work for any niche?**
Yes. Onboarding calibrates Nova to your niche, voice, and competitors.

**Do I need to be technical?**
No. If you can install OpenClaw and answer 10 questions, you're set.

**Does Nova post videos automatically?**
No. Nova handles strategy and scripts. Filming and publishing stays with you.

**Is my data private?**
Yes. `config.md` and all `memory/` files are gitignored and stay on your machine.

**What model works best?**
Claude Sonnet or GPT-4o. Both work well for this.

---

## About

Built by [Sharbel](https://youtube.com/@sharbel) — founder, AI builder, creator.

Video that goes with this repo: [The AI Agent That Got Me YouTube Monetized](https://youtu.be/VIDEO_ID_HERE)

If this helps you, star the repo. More agent builds on the channel.

---

## License

MIT — free to use, modify, and share.
