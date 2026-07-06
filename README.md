# Nova, YouTube Growth Agent for Hermes

Nova is a reusable YouTube growth agent for [Hermes Agent](https://hermes-agent.nousresearch.com/). It helps creators move from random brainstorming to a repeatable content system.

Nova researches your channel, competitors, keywords, source videos, transcripts, pipeline, approvals, rejections, and voice before it recommends ideas or writes scripts.

## What Nova does

| System | What it does |
|---|---|
| Onboarding | Learns your channel, audience, goals, voice, competitors, tools, and boundaries |
| Channel analysis | Finds what is working and not working on your own channel |
| Competitor scan | Finds outlier videos, title patterns, hooks, thumbnails, and source structures |
| Idea generation | Interviews you and combines your real proof with market evidence |
| Filming slate | Helps decide what to film next without repeating posted or rejected ideas |
| Script writing | Writes filming scripts with retention structure, proof, caveats, and SEO |
| Upload package | Creates description, tags, chapters, title variants, thumbnail concept, and pinned comment |
| Performance log | Tracks video results and updates future recommendations |
| Feedback loop | Learns from approvals, rejections, and post-publish performance |

## Why this exists

Most creators do content strategy in scattered places: YouTube tabs, analytics, notes, vidIQ, Notion, comments, transcripts, and half-remembered ideas.

Nova turns that into one workflow:

1. Check what you already posted.
2. Check what is already approved, rejected, filmed, or scheduled.
3. Check your channel performance.
4. Check competitors and outliers.
5. Check keyword demand when tools are available.
6. Interview you for real proof and experience.
7. Recommend the strongest idea with receipts.
8. Turn it into a script and upload package.
9. Log performance and learn for next time.

## Installation

Clone this repo into your Hermes skills directory:

```bash
git clone https://github.com/sharbelxyz/nova-youtube-agent.git ~/.hermes/skills/nova-youtube-agent
```

Then tell Hermes:

```text
Nova, set up my YouTube agent.
```

Nova will run onboarding and create a private `config.md` file.

## Onboarding

Nova asks for your channel name, channel URL, niche, ideal viewer, subscriber goal, current size, voice, competitors, what to avoid, best videos, optional tools, and optional storage preferences.

Your answers stay local in `config.md`.

## Memory files

Nova creates a private `memory/` folder:

- `posted-videos.md`
- `approved-ideas.md`
- `rejected-ideas.md`
- `performance-log.md`
- `competitor-scans.md`
- `channel-analysis.md`
- `voice-examples.md`
- `pipeline.md`

These files are gitignored. They are where Nova learns your taste and avoids repeating old ideas.

## Evidence labels

Nova labels recommendations so you know what is proven and what is judgment:

- `channel-data-backed`
- `pipeline-backed`
- `vidIQ-backed`
- `competitor-backed`
- `YouTube-validation-backed`
- `transcript-backed`
- `strategic judgment`

If vidIQ is not available, Nova should say so and use a YouTube fallback. It should not pretend fallback data is vidIQ.

## Example prompts

```text
Nova, analyze my channel and tell me what is working.
```

```text
Nova, scan my competitors and find outlier video ideas.
```

```text
Nova, help me decide what to film next week.
```

```text
Nova, interview me and generate 5 video ideas.
```

```text
Nova, write a full filming script for this idea.
```

```text
Nova, create the upload description, chapters, tags, pinned comment, and thumbnail concept.
```

```text
Nova, log this video's performance and update the feedback loop.
```

## Optional integrations

Nova works with whatever information you provide. Useful optional tools:

- vidIQ, for keyword and outlier research
- YouTube Studio exports or screenshots
- Notion or another content board
- transcript tools
- Google Sheets or CSV analytics exports
- browser access for public YouTube research

All integrations should use your own local credentials and permissions. This repo does not include secrets.

## Privacy

This public repo intentionally excludes private memory logs, local file paths, API keys, secret locations, Notion database IDs, chat IDs, client information, and private channel strategy notes.

Use `example-config.md` and `templates/config-template.md` as safe starting points.

## License

MIT
