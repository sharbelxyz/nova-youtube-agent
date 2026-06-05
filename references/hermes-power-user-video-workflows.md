# Hermes power-user video workflow notes

Use this reference when Sharbel is planning a Hermes Agent video, especially a power-user list, Mission Control walkthrough, or operator workflow video.

## Positioning that worked

Frame the video as a real migration and operating system, not a generic feature tour.

Strong narrative:

> This started as the Mission Control I built for OpenClaw. As I used Hermes more, I migrated more of the operating layer into Hermes. Now most of the system is run by Hermes.

Avoid generic framing like:

> Most people use Hermes like ChatGPT in a terminal, I use it like an operating system.

Sharbel reacted negatively to that style because it sounds AI-generated. Prefer grounded lines based on actual use:

> I do not care what Hermes can technically do. I care what I would rebuild immediately if I had to start over.

> This is my real Hermes setup. Not the install guide, not the feature tour. The workflows that actually survived.

## Strong list architecture

The strongest list is not random hacks. It should show how one assistant becomes an operating system.

Recommended core items:

1. Mission Control, the HQ view and OpenClaw to Hermes migration story.
2. `/goal`, long-running objectives and how to write great goals.
3. Subagents, research team mode.
4. Telegram topics, category-specific workspaces rather than generic messaging.
5. Kanban, visible task management for agent work.
6. Cron jobs, scheduled incoming intelligence.
7. Webhooks, event-triggered agents.
8. Skills, SOPs for the agent.
9. Memory plus session search, only if framed as a work diary that explains past decisions.
10. Specialist agents using different profiles, models, tools, memory, and permissions.

If the video must be shorter, cut memory/session search first. The strongest eight are Mission Control, `/goal`, subagents, Telegram topics, Kanban, cron, webhooks, and skills. Specialist agents can become the closing philosophy.

## Cron vs webhooks distinction

Cron means time triggered.

Examples:

- Every morning, find fresh AI stories worth reacting to.
- Every Friday, summarize the best video ideas.
- Every day, check competitors for outliers.
- Every Monday, audit the Notion content board.

Webhooks mean event triggered.

Examples:

- Notion item moves from Idea to To Film.
- Lead form submitted.
- GitHub PR opened.
- Stripe payment received.
- Competitor video detected by a script.

Say:

> Cron is what Hermes does on a schedule. Webhooks are what Hermes does when something happens somewhere else.

## Notion To Film webhook demo

Best demo for Sharbel:

Trigger: a Notion Content Board item moves from Idea to To Film.

Hermes action: validate the idea before filming.

Prompt pattern:

```text
A YouTube idea was moved to To Film in Notion:

Title: {title}
Notion URL: {notion_url}

Before this becomes a filming task, validate it.

Check:
1. Is this too close to a posted video?
2. Is there current YouTube or vidIQ demand?
3. What is the strongest title?
4. What proof assets do we need?
5. What should the first 30 seconds show?
6. Should this be filmed now, later, or killed?

Return a filming verdict and update the Notion page with a short research brief.
```

If direct Notion webhook support is inconvenient, use Notion automation, Make, or Zapier to send a webhook to Hermes. Do not claim native Notion webhooks are available unless verified in the current session.

## `/goal` mini masterclass

Explain that a normal prompt asks for one response, while `/goal` gives Hermes an objective and lets it continue until the goal is satisfied, paused, interrupted, or budgeted out.

Five-part goal formula:

```text
/goal [Outcome] for [context], using [sources/tools], with [constraints], ending in [deliverable].
```

Example:

```text
/goal Pick the strongest Hermes video for me to film this week for my YouTube channel, using vidIQ, YouTube outliers, competitor transcripts, my posted videos, and Nova memory. Avoid repeated angles, avoid generic AI-guru framing, and end with a filming-ready title, hook, demo list, and proof assets.
```

Prompt to get Hermes to write the goal:

```text
I want to use /goal, but I do not want to write a vague goal.

Interview me with only the questions you need, then turn my answers into the strongest possible /goal command.

The goal should include:
1. the exact outcome
2. the context Hermes needs
3. tools and sources to use
4. constraints and things to avoid
5. the final deliverable
6. when Hermes should stop
```

## Kanban framing

Do not frame Kanban as a normal to-do list. Frame it as visibility for agent work.

Say:

> The moment agents start doing real work, chat becomes the worst possible task manager. Kanban gives the agent a board, ownership, dependencies, logs, and a way for me to see what is actually happening.

Demo board:

```text
Board: Hermes Mission Control Video

Tasks:
1. Research Hermes outliers
2. Pull transcripts from top competitor videos
3. Analyze past Hermes videos
4. Draft strongest feature list
5. Build Mission Control demo assets
6. Write /goal demo prompt
7. Create Notion filming brief
8. Generate thumbnail concepts
9. Prepare upload SEO package
```

## Skills as SOPs

Frame skills as operating procedures, not as generic add-ons.

A strong skill includes:

1. Trigger, when Hermes should use it.
2. Inputs, what Hermes needs.
3. Required context, files, tools, docs, or memory to check.
4. Workflow, step-by-step process.
5. Rules, what never to do.
6. Output format.
7. Pitfalls.
8. Verification.

Good demo: create a `filming-brief` skill that validates a YouTube idea, checks posted videos, identifies the viewer promise, generates titles, lists proof assets, writes the first 30 seconds, and returns a recording checklist.

Key line:

> I am not prompting from scratch. I am giving Hermes the playbook.

## Specialist agents framing

Sharbel liked this analogy:

> You do not want your accountant to be your dentist. You do not want your dentist to be your pilot. So why would every AI agent have the same model, tools, memory, and job?

Specialists can differ by model cost, tools, permissions, memory, and context.

Example setup:

- Nova, YouTube strategist: strong reasoning model, vidIQ, Notion Content Board, YouTube memory, script rules.
- Research Agent: browser and transcript tools, no posting permissions.
- Coding Agent: repo, terminal, tests, GitHub, code review skill.
- Admin Agent: calendar, reminders, email, approval required before sending anything.
- Monitoring Agent: cheap fast model, cron jobs, alerts, sends summaries only.

Main benefit: reduce chaos and cost by matching each agent's brain, tools, and memory to the job.
