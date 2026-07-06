# Notion To Film trigger notes

Use this when the creator moves a Notion Content Board item into `To Film/Write` and expects Nova to generate a filming validation brief.

## Local scripts

- Watcher: `~/.hermes/scripts/notion_to_film_watch.py`
- Research wrapper: `~/.hermes/scripts/notion_to_film_research.py`
- Scheduled cron job: Notion To Film Brief Watcher, every 10 minutes, origin delivery.

## Manual run pattern

If the creator says he just moved an idea and wants it processed immediately, run the research wrapper, not only the watcher:

```bash
python3 ~/.hermes/scripts/notion_to_film_research.py --force
```

Why: the watcher is stateful. Running the watcher alone can mark the transition as seen without generating or delivering a Nova brief. The wrapper calls the watcher, builds the Nova prompt, and appends or returns the filming validation brief.

## Expected brief shape

For each current or newly moved `To Film/Write` item, produce:

- FILM NOW / FILM LATER / KILL verdict
- operator-first reasoning
- evidence labels: vidIQ-backed, YouTube validation-backed, channel-data-backed, strategic judgment
- strongest title
- 3 backup titles
- first 30-second hook
- proof assets needed
- demo checklist
- what to avoid

## Pitfalls

- Do not call an idea vidIQ-backed unless vidIQ was actually checked in the current run.
- Do not append a broad generic brief if the title needs repackaging. Say KILL unless repackaged, then give the better angle.
- If multiple pages are already in `To Film/Write`, `--force` may process all current To Film items. Summarize verdicts clearly so the creator can see which one to film first.
- Do not use generic framing like “most people use.” Start from the creator’s real system, current setup, receipts, and concrete operator workflow.