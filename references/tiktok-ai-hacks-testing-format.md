# TikTok AI Hacks Testing Format

Use this when Sharbel wants a broad viral AI tools video reframed around TikTok-proven hacks or claims.

## Core lesson
Package the video as testing TikTok promises, not reviewing tools. The viewer wants to see whether viral AI claims survive real work.

Preferred title shape:
- `I Tested the Most Viral TikTok AI Hacks`
- `I Tested Viral TikTok AI Hacks So You Don't Have To`
- `TikTok Said These AI Tools Are Insane. I Tested Them`

Avoid defaulting to generic list titles like `10 AI Tools You Need` unless the user explicitly asks for a listicle.

## Required workflow
1. Find actual TikTok videos first. Do not use search-result placeholders as receipts.
2. For each TikTok, capture:
   - URL
   - creator
   - view count
   - like count
   - shares/reposts if available
   - comments if available
   - exact viral promise/claim
   - how Sharbel will test it with real operator work
3. Use `yt-dlp --dump-json <tiktok-url>` when possible to verify TikTok metadata. TikTok browser search may expose video links and like counts in the DOM even when logged out. Individual TikTok URLs often work better than search pages.
4. Start every segment with the TikTok receipt: `TikTok says this can do X. I am testing whether it survives Y.`
5. Then run a real test, not a homepage demo. Prefer tasks from Sharbel's actual workflow: build a page, research a video, create a thumbnail, audit sources, create production audio, turn notes into a brief, or automate a content workflow.
6. Give each segment a blunt verdict: Fake, Mid, Real, or Keeper.
7. Use a scoreboard across the video so retention has a visible game mechanic.
8. Only after the TikTok receipt list is verified should you write or update the Notion script page.

## YouTube format references from research
High-performing adjacent formats show the same retention pattern:
- Mrwhosetheboss: `I tested the most VIRAL TikTok gadgets!`, about 19.4M views
- Mrwhosetheboss: `I tested Viral TikTok Life Hacks - are they a SCAM!?`, about 10.4M views
- Mrwhosetheboss: `I Tested the Most Ridiculous TikTok Life Hacks`, about 9.9M views
- Nick DiGiovanni: `I Tried Every Viral TikTok Food Hack`, about 20.8M views
- Will Tennyson: `I Tried EVERY Viral TikTok "Life Hack"`, about 2.6M views

Transcript pattern:
- Cold open: TikTok claim plus challenge stakes.
- Watch the short claim before testing.
- State skepticism in plain language.
- Test visibly.
- Explain what actually happened.
- Score quickly.
- Escalate from plausible to ridiculous or high-stakes.

## Example verified TikTok AI receipts from session
These are useful references, but refresh before final scripting because TikTok freshness matters.

- Claude Code web designer: https://www.tiktok.com/@nathanhodgson.ai/video/7644171990961573142
  - 457.7K views, 26K likes, 5.3K shares
  - Claim: Claude Code can become a full web designer.
  - Test: give Claude Code a messy website redesign or landing page task.

- Claude Code token/context hack: https://www.tiktok.com/@duncanrogoff/video/7643929550732233998
  - 256.5K views, 15.5K likes, 2.1K shares
  - Claim: people waste Claude Code tokens without realizing it.
  - Test: run the same build with and without the hack, compare cost/speed/output.

- Manus AI agent: https://www.tiktok.com/@lucaswebq/video/7601237301963934998
  - 236.9K views, 13.3K likes, 1.5K shares
  - Claim: Manus is a powerful AI agent.
  - Test: have Manus research the video, rank the hacks, and create a filming brief.

- Lovable app builder: https://www.tiktok.com/@lovable.app/video/7530255867694943510
  - 334K views, 9.4K likes
  - Claim: build an app fast without technical skill.
  - Test: build a TikTok AI hack tracker app.

- Veo 3 image-to-video: https://www.tiktok.com/@sebastienjefferies/video/7525021018868469014
  - 274.9K views, 10K likes
  - Claim: world's best video model can turn images into video.
  - Test: turn a still image of Sharbel's setup into cinematic AI-agent B-roll.

- Google Opal/app builder: https://www.tiktok.com/@maxtalkstech/video/7610533021195832606
  - 101.9K views, 5.4K likes
  - Claim: Google changed app building.
  - Test: build the same app as Lovable and compare.

- Nano Banana/Gemini image: https://www.tiktok.com/@adrianvonarx/video/7550079351627189518
  - 31.9K views, 1.6K likes
  - Claim: Gemini image update is strong for product/design visuals.
  - Test: generate thumbnail concepts and judge if usable.

- Perplexity Comet browser: https://www.tiktok.com/@rpn/video/7528978052634660127
  - 99.6K views, 4.5K likes
  - Claim: browser can take actions for you.
  - Test: verify which TikTok AI hacks are real and build a ranked source-backed list.

- NotebookLM learning hack: https://www.tiktok.com/@rpn/video/7553768554168945951
  - 1.5M views, 134.3K likes, 30.1K shares
  - Claim: NotebookLM changes how you learn.
  - Test: feed all research into NotebookLM and ask for a final brief/ranking/audio overview.

- ElevenLabs AI voice: https://www.tiktok.com/@benkaluza/video/7455016774476533024
  - 2.1M views, 69.1K likes, 10.5K shares
  - Claim: usable AI voice generation.
  - Test: produce a fake ad read or narration for one segment and judge if production-ready.

## Pitfall
Do not tell Sharbel TikTok links are in the script when they are only search links or generic filming notes. If individual TikTok URLs cannot be verified, say so plainly and keep researching. Search links are not receipts.