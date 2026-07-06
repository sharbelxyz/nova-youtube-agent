# vidIQ CDP Deep Research Techniques

## When to Use This

The `vidiq-bridge` structured commands (`keywords`, `keywords for-you`, `keywords rising`, etc.) often return the same cached page data regardless of which tab is requested. When you need **real outlier data** - multipliers, VPH, channel names, view counts - skip the bridge and go direct via CDP.

## Prerequisite

vidIQ must be open in Brave and Brave must have CDP active (`127.0.0.1:9222`). Check with `vidiq-bridge status`.

## The Reliable Pattern: Direct Tab URL Navigation

Use the Python `websockets` CDP approach. Navigate to a specific vidIQ tab URL, wait 8 seconds for render, extract `document.body.innerText`.

```python
import asyncio, json, urllib.request, websockets

async def get_vidiq_tab(url, wait=8):
    req = urllib.request.urlopen("http://127.0.0.1:9222/json", timeout=5)
    tabs = json.loads(req.read())
    vidiq_tab = next((t for t in tabs if "vidiq.com" in t.get("url", "")), None)
    if not vidiq_tab:
        return "No vidIQ tab"
    
    async with websockets.connect(vidiq_tab["webSocketDebuggerUrl"]) as ws:
        await ws.send(json.dumps({"id": 10, "method": "Page.navigate", "params": {"url": url}}))
        await asyncio.sleep(wait)
        await ws.send(json.dumps({"id": 11, "method": "Runtime.evaluate",
                                   "params": {"expression": "document.body.innerText", "returnByValue": True}}))
        for _ in range(20):
            try:
                msg = await asyncio.wait_for(ws.recv(), timeout=3)
                d = json.loads(msg)
                if d.get("id") == 11:
                    return d.get("result", {}).get("result", {}).get("value", "")
            except asyncio.TimeoutError:
                break
    return "timeout"

asyncio.run(get_vidiq_tab("https://app.vidiq.com/research/explore?tab=videos"))
```

## Key URLs to Hit

**Always check in the configured creator's preferred priority order: Top Search Terms first, Rising Keywords second, For You third, then keyword gaps/opportunities as an additional filter. YouTube autocomplete is only fallback or secondary validation when vidIQ is accessible.**

| URL | What You Get |
|---|---|
| `https://app.vidiq.com/research/explore?tab=keywords` | Full keyword list with search volume + competition level (Low/Medium/High). Use to identify keyword gaps. |
| `https://app.vidiq.com/research/explore?tab=keywords&keywordTab=rising` | Full rising keywords list with % change and competition. Filter manually for AI/agent niche - most rising keywords are off-niche (gaming, sports, TV). |
| `https://app.vidiq.com/research/explore?tab=keywords&keywordTab=search-terms` | Keywords currently driving views to the channel |
| `https://app.vidiq.com/research/explore` | Keywords for you, outlier videos, rising keywords preview, top search terms, Shorts outliers |
| `https://app.vidiq.com/research/explore?tab=videos` | Outlier videos with **multiplier score (e.g. 5.5x)**, VPH, channel name, subs, view count |
| `https://app.vidiq.com/research/explore?tab=shorts` | Shorts outliers with VPH, view counts, >100x scores |
| `https://app.vidiq.com/channels/<YOUR_CHANNEL_ID>/competition` | the creator's top competitor videos this week with outlier score + VPH |

**URLs that do NOT work (redirect to feed):**
- `/channels/…/keyword-gaps`
- `/channels/…/trending-keywords`
- `/research/keyword-gaps`
- `/research/rising-keywords`

Use the `?tab=` parameter versions above instead.

## What the Videos Tab Returns (Sample)

From live session 2026-05-26:

```
5.5x  53 VPH  Hermes Agent Masterclass: 1. Installation, Setup, Basic Commands
                Tonbi's AI Garage • 16K subscribers  •  37K views • 23 days ago

       58 VPH  Hermes Agent Setup for $8/Month Cost Reduction: No Claude Rate Limits
                Moe Lueker • 43K subscribers  •  26K views • 16 days ago

2.1x  23 VPH  Hermes Agent Full Setup Tutorial: How to Setup Your First AI Agent (Gemma 4)
                Bart Slodyczka • 68K subscribers  •  80K views • 2 months ago
```

This level of detail (VPH per channel, exact multiplier, recency) is NOT available from structured bridge commands. Only direct CDP tab navigation returns it.

## What the Shorts Tab Returns (Sample)

```
200 VPH   60 AI Agents Inside Claude Code (Free Setup Guide)
          Duncan Rogoff | AI Automation • 65K subscribers • 368K views • a month ago

>100x  115 VPH  Build an Agent with Microsoft Copilot Studio
                Roberto Nickson • 24K subscribers • 848K views • 10 months ago
```

## Top Search Terms (from explore main tab)

The "Top search terms" section on the main explore page shows what's actually driving views to the creator's channel right now. Example output may look like:

| Keyword | Views | Watch Time (min) |
|---|---|---|
| hermes agent | 4,141 | 17,543 |
| hermes | 1,669 | - |
| hermes vs openclaw | 1,477 | - |

This data updates each session. Check it before making any recommendations.

## Filtering Output

The raw `innerText` includes navigation chrome. Filter out boilerplate lines:

```python
skip = {'Skip to main content', 'New Chat', 'Feed', 'Optimize', 'Research',
        'Install Extension', 'More tools', 'History', 'View all', 'Boost',
        '<YOUR_VIDIQ_ACCOUNT_EMAIL>', 'Log in daily to keep earning free credits'}

lines = [l.strip() for l in text.split('\n')
         if l.strip() and len(l.strip()) > 3 and l.strip() not in skip]
```

## Keyword Gap Sample (2026-05-26)

From `?tab=keywords` - high volume, Low competition gaps not yet covered by the creator:

| Keyword | Volume | Competition |
|---|---|---|
| `hermes agent tutorial` | 128K | **Low** |
| `hermes agent use cases` | 147K | Medium |
| `claude code alternative` | 44K | **Low** |
| `hermes agent ollama` | 29K | **Low** |
| `openclaw vs hermes agent` | 20K | Medium |
| `hermes agent telegram` | 18K | **Low** |
| `hermes vs claude code` | 10K | **Low** |
| `hermes kanban` | 82K | Medium |
| `hermes setup` | 79K | Medium |
| `hermes agent free` | 40K | Medium |
| `hermes agent vps` | 38K | Medium |
| `hermes agent hostinger` | 47K | Medium |

Rising keyword relevant to niche from `?tab=keywords&keywordTab=rising`:
- `hermes desktop` - 150K, **+3,400%**, Medium competition (spiked May 2026)
- `grok agent mode` - 173K, +2,100%, Very low competition
- `gemini 3.5` / `gemini 3.5 flash` - 298K-484K, ~1,900%

## Pitfalls

- Wait at least 8 seconds after navigation before extracting. 5 seconds often returns partial content.
- The vidIQ tab must already be open in Brave. If it closed, navigate to `https://app.vidiq.com/research/explore` first and wait for login.
- The `competition` URL for the creator's channel is `/competition` not `/competitors`. Wrong URL silently redirects to the feed.
- Run all CDP reads in the same `async with websockets.connect(ws_url) as ws:` block to avoid repeated handshakes.
