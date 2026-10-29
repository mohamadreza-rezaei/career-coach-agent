# Workflow: brain delta proposal

Many users keep a second brain (an Obsidian vault, notes repo, or wiki) with **one designated writer**: a supervisor agent or the user. You never write there. You hand over a delta.

## Steps

1. Read the notes repo's protocol files (e.g. `AGENTS.md`, `BRAIN.md`, `INDEX.md`, the change log) and follow their conventions: language, frontmatter, links, folder roles, no duplicates, no secrets, raw chat only in its raw-source folder.
2. Search for existing notes on each subject. **Patch before you create.**
3. Write a delta file with `templates/brain-delta.md`. For each target, give:
   - the exact path,
   - the action (new or patch),
   - for a patch: the exact anchor (heading or line) and the replacement text,
   - for a new note: the full content in the repo's language and format.
4. Keep facts apart from assumptions. Mark unverified metrics as unverified.
5. If the user asked for a chat archive, put it in the repo's **raw-source** folder (e.g. `exports/`), with distilled notes linking to it, never as a regular note.
6. Send the delta to the writer agent through whatever channel the user set up (a file path, an issue, a message). Tell the user what's proposed in 3–5 lines.

## Typical targets after onboarding
- skill model (new note)
- learning roadmap (new note)
- contradictions backlog (new note)
- goals (small patch)
- career path (an evidence callout on the metrics)
- the platform-update decision (a decision note)
- active tasks (the security item)
- the index and change log
