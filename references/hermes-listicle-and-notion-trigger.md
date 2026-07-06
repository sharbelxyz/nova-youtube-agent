# Hermes listicle and Notion To Film trigger notes

Use this reference when the creator is planning Hermes Agent videos, especially listicles around 24/7 assistant workflows.

## Packaging preference

The creator rejected abstract packaging like "How I'd Set Up Hermes Agent as a Real Operating System" for this video class. Prefer a clear listicle frame:

- `10 Hermes Agent Hacks That Make It Feel Like a 24/7 Assistant`
- `10 Hermes Agent Hacks That Turn It Into a 24/7 Assistant`

Keep the story concrete: this started as an OpenClaw Mission Control setup, then Hermes gradually took over more workflows.

## Strong demo list

High-priority sections:

1. Mission Control, show the real dashboard and migration story.
2. `/goal`, teach how to write strong goals and how to ask Hermes to generate the best goal command.
3. Subagents as a research team, ideally for researching the video itself.
4. Telegram topics as separate workspaces, not generic "use Telegram".
5. Kanban as an agent task board, so work does not disappear into chat.
6. Cron jobs as scheduled intelligence drops.
7. Notion Content Board trigger, when an item moves to `To Film/Write`, Hermes validates it.
8. Skills as SOPs, showcase Nova and mention Sage/X agent, sponsor checker, lead qualifier, etc.
9. Specialist agents, different profiles, models, tools, memory, and access.
10. Memory/session search only if framed as a work diary and decision history, not generic memory.

## Notion To Film trigger pattern

For the creator's current Content Board:

- Database title: `Content Board`
- Database ID: `<YOUR_NOTION_CONTENT_BOARD_DATABASE_ID>`
- Title property: `Content`
- Status property: `Status`
- Target status: `To Film/Write`

A practical implementation can poll Notion every 10 minutes instead of relying on true Notion webhooks. Be honest in scripts: "Hermes watches my Notion board" rather than claiming instant native webhooks if the setup is polling.

Desired output when an item transitions into `To Film/Write`:

- FILM NOW / FILM LATER / KILL verdict
- operator-first reason
- strongest title
- backup titles
- first 30-second hook
- proof assets needed
- demo checklist
- what to avoid

Demo phrasing:

> This is one of my favorite Hermes hacks. When I move an idea in Notion from Ideas to To Film, Hermes automatically validates it before I waste a filming day.

## Skills section angle

Frame skills as SOPs for agents. Use Nova as proof:

- checks vidIQ
- reads posted videos
- checks rejected and approved ideas
- uses performance data
- writes scripts with the retention framework
- creates upload SEO packages
- knows the creator's voice and constraints

Sticky lines:

- If you've explained the same process to an AI more than three times, it probably belongs in a skill.
- Prompts are instructions for one task. Skills are instructions for every future version of that task.
