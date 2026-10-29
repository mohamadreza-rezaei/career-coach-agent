# Workflow: Platform Sync (monthly checkpoint)

**Trigger:** the monthly routine (`routines/monthly-sync.md`), or a checkpoint date in `profile/roadmap.md`.

**Principle:** public surfaces show only `proven` skills. Each change is a **small patch the user approves**. No bulk rewrites.

## Steps

1. Diff the skill model against last month: what became `proven`?
2. Check the open items in `profile/contradictions.md`. Pick the ones this month's evidence resolves.
3. For each surface in `profile/surfaces.md`, draft a patch with `templates/surface-patch-proposal.md`:

| Surface type | How to change it | Mode |
|---|---|---|
| **Portfolio + CMS/DB** (e.g. a Supabase or Postgres content table, plus the site repo) | Exact row updates (table, row id, column, old → new); a repo PR for copy that lives in code | write-with-approval |
| **Code-host profile README** (e.g. `<user>/<user>` on GitHub) | A PR or commit with a minimal diff | write-with-approval |
| **LinkedIn** | Draft headline, about, and skills text for the user to paste; no edit API is assumed | hint-only |
| **Resume doc** (all language versions or tabs) | Suggestion-mode edits, or exact find/replace pairs per tab; keep the versions consistent | write-with-approval |
| **Link-in-bio** | List of link changes; if the user owns a short-link service in a repo, a PR there | hint-only, or write-with-approval for an owned repo |
| **Company or team profile** (the user's own row, plus its translation rows) | Row updates for every language together | write-with-approval |
| **Second brain / notes repo** | A delta file for the supervisor or writer agent | delta-only |

4. Send **one** message listing every patch (surface → change → evidence). The user approves all, some, or none.
5. Apply only the approved patches, on `write-with-approval` surfaces. Hand hint-only text to the user.
6. Mark the resolved contradictions `resolved (YYYY-MM-DD)` and add a line to `profile/changelog.md`.
7. Queue a brain delta summarising the sync.

## Before the first checkpoint
Only fix clear factual contradictions, and only with approval. Don't announce new skills yet.
