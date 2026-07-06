# Viral AI Tools Testing Format Notes

Use when preparing or scripting a broad video like "I Tried Every Viral AI Tool in 2026" or "I Tested 20 Viral AI Tools. Only 3 Survived."

## Transcript honesty
If only openings, summaries, or selected transcript sections were analyzed, say that plainly. Do not imply every transcript was reviewed line by line unless it actually was. For script strategy, the usable pattern from viral testing videos is usually enough: viral claim, skepticism, live test, reaction, verdict, score, fast move.

## Recommended count
For the creator, prefer testing 20 tools on camera instead of 50 or 100 unless the video only shows filtered winners.

Why 20 works:
- Big enough for a strong click and thumbnail.
- Small enough to show proof and avoid generic AI listicle energy.
- Allows 3 final winners plus funny failures.
- Fits a 14 to 18 minute video if most tools get 20 to 40 seconds and winners get 60 to 90 seconds.

Viral adjacent reference points:
- 100 product or hack videos use the big number as the hook.
- Dan Martell/Parker-style AI videos claim 100 to 500+ researched or tested tools, then present a much smaller winner list.
- AI video generator comparisons commonly use 10 to 15 tools.
- AI agent/tool comparisons commonly use 7 to 20 tools.

## Packaging
Strong default title:
`I Tested 20 Viral AI Tools. Only 3 Survived`

Marvv-compatible title:
`I Tried Every Viral AI Tool in 2026`

Thumbnail text:
`3 SURVIVED`

Core promise:
`I tested viral AI tools like an operator, not with perfect demo prompts. Most were toys. Only three stayed in my stack.`

## Evidence workflow
Before recommending tools or writing the script:
1. Run vidIQ surfaces first: status, keywords, top search terms, rising, for-you.
2. Validate on YouTube with current searches and recent high-view examples.
3. Pull social receipts when possible:
   - X API helper: `set -a; source ~/.hermes/.env.xapi; set +a; python3 ~/.hermes/scripts/x_api_search.py '"Claude Code" lang:en -is:retweet' 50`
   - Rank recent X results by likes, reposts, bookmarks, and impressions.
   - YouTube quick surface: `yt-dlp 'ytsearch5:Claude Code viral AI tool 2026' --flat-playlist --dump-json --no-warnings`
4. For TikTok-first viral tool videos, every tool segment should open with a TikTok receipt beat: show the viral claim/search result for 2-3 seconds, then test it. Try to collect direct TikTok URLs or visible logged-in search results. If TikTok blocks extraction, do **not** invent links or call them verified receipts; add a filming note with exact TikTok searches for manual logged-in capture, and write each segment so it begins with “Before I test it, look at what TikTok promises…” or equivalent.
5. Label evidence clearly as vidIQ-backed, YouTube validation-backed, TikTok manual-capture needed, X/social receipt, channel-data-backed, or strategic judgment.
6. Do not call TikTok, Instagram, Reddit, or X evidence verified unless direct URLs or visible search results were actually collected in the current session.

## Tool shortlist pattern
Start with 20 tools, then swap based on access.

Must-include lanes:
- Giants and research: ChatGPT Agent or Deep Research, Claude Code, Perplexity/Comet, NotebookLM.
- Autonomous agents: Manus, Genspark, Lindy, Zapier Agents, Gumloop.
- Builders: Lovable, Bolt.new, Cursor, Replit Agent.
- Automation/content: n8n, Gamma, ElevenLabs, Canva or CapCut AI.
- Viral creative: Veo, Runway, Kling, Midjourney or Sora.

Use Hermes Agent and OpenClaw carefully. They can be the final unfair advantage or operator stack reveal, but avoid making the whole broad video feel like a hidden ad for the creator's own niche.

## Segment loop
Every tool should follow the same fast test loop:
1. Receipt: show viral post, video title, or claim for 2 seconds.
2. Claim: "This says it can do X."
3. Skepticism: "My worry is Y."
4. Test: one real operator task.
5. Result: screen capture output.
6. Verdict: one punchy sentence.
7. Score overlay: Toy, Useful, Keep, or Kill.

Scoring:
- 0 to 2: Toy.
- 3 to 5: Useful but annoying.
- 6 to 8: Actually useful.
- 9 to 10: Stays in my stack.

Criteria:
- Useful output in under 10 minutes.
- Fits a real workflow.
- Takes action or creates a real artifact.
- Survives messy inputs.
- Worth the cost.
- Would still be used after filming.

## Script spine
Cold open:
`I tested 20 viral AI tools people keep recommending in 2026. Not with perfect demo prompts. I tested them like an operator. Could they save me time, build something real, automate work, or make something I would actually use next week? Most were toys. A few were useful. Only three survived.`

Rules:
`Every tool gets one real task. If it needs babysitting, it loses. If the output looks good but I cannot use it, it loses. If I would cancel it after filming, it loses.`

Retention beats:
- Kill one hyped tool early.
- Let one boring tool unexpectedly score high.
- Let one creative tool look amazing but fail the operator test.
- Show one builder creating the first genuinely usable artifact.
- Final reveal is the actual 3-tool stack.
