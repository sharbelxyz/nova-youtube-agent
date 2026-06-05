# Follower Idea Challenge Format

## Trigger
User posts on X/YouTube asking followers for their "best/weirdest agent ideas" and says they'll build 3 on camera. They want Nova to:
1. Read all comments from both posts
2. Evaluate them against the creator's own 3 picks
3. Recommend the best final 3 to build

## Comment Harvesting Workflow

### YouTube post comments (CDP)
YouTube is logged in on Brave CDP. Use the Python websockets CDP approach:
- Navigate the YouTube tab to the post URL
- Wait ~7 seconds for comment loading
- Extract `document.body.innerText` — YouTube renders comments in plain text including @handles, timestamps, like counts, and reply counts
- Comments load in "Top" sort by default; this is usually fine for picking the most engaging ideas

### X post replies
X is **not logged in** on Brave CDP as of May 2026. Navigating returns the logged-out wall.
- Do not waste time on CDP for X
- Use `xurl` or `x-cli` if available and logged in
- Otherwise, note the limitation clearly and proceed with YouTube comments alone (they are usually sufficient)

## Evaluation Framework

After collecting all comments, score each idea on 3 axes:

| Axis | What to assess |
|---|---|
| **Buildability** | Can Sharbel actually demo this live with Hermes in 1-3 days? Does it require OAuth flows, payment rails, or hardware he doesn't have? |
| **Entertainment value** | Will a viewer laugh, share, or screenshot this? Funny > useful for virality in challenge videos. |
| **Originality** | Has this been done on YouTube before? Check if it's a known tutorial topic vs genuinely fresh. |

## Comparison Table Format

Present this to Sharbel after reading comments:

```
## Creator's 3 picks
- [Pick 1] — [brief eval: keep / upgrade to better version / swap]
- [Pick 2] — [brief eval]
- [Pick 3] — [brief eval]

## Top comments not on their list
- [Comment author]: [idea summary] — [why it's worth considering]
...

## My recommendation: best 3 to build
1. [Idea] — [1-sentence reason: funny/original/buildable]
2. [Idea] — [1-sentence reason]
3. [Idea] — [1-sentence reason]
```

## Upgrade pattern
Often the creator's picks are directionally right but a comment improves the version:
- "Amazon every Monday" → @SnowSunFun's mystery gift agent (better emotional hook)
- "AI girlfriend" → confirmed by adjacent comments (proxy wife, pet agent format)
- "Hair agent" → weak without real proof asset; look for something demoable

## After Sharbel confirms the 3
Move directly to script ideation. Ask:
- Which one does he want to film first?
- Does he have a working Hermes persona/voice setup for the girlfriend agent?
- Any real assets or proof (existing agents, dashboards) he can show on camera?
Then go straight to scripting. Do not re-interview from scratch if the channel context is known.
