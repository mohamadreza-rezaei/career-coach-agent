# Workflow: Platform Sync (career surface sync, monthly checkpoint)

**Trigger:** the monthly routine (`routines/monthly-sync.md`), a checkpoint date in `profile/roadmap.md`, or the user asking for a sync.

**Principle:** public surfaces say exactly what the evidence proves: no more, no less. Each change is a **small patch the user approves**. No bulk rewrites.

## 0. Gate

- Run only at a configured checkpoint, or when the user asks.
- Only `proven` skills qualify for public surfaces (`docs/evidence-levels.md`). If the user's plan says "no public updates until a skill is proven", nothing below `proven` goes out, even as a hint.
- **Quick diff first.** If the skill model hasn't changed since the last sync line in `profile/changelog.md` and nothing new shipped, stop: silent on a scheduled run, one line if the user asked.

## 1. Evidence (read-only)

1. Diff the skill model against the last sync: what became `proven`? What new project, merged PR, or deployed service exists?
2. Sources: `profile/skill-model.md`, `profile/changelog.md`, quiz and drill scores, recent chats, the user's notes repo (read-only), their repos, and anything they sent.
3. Per item record: claim, evidence link or quote, evidence level, and **confirmed** vs **assumed**. Assumed items never go public. If an important one is unclear, ask **one** short question.
4. Never invent skills, titles, metrics, dates, or projects. A number needs a source.

## 2. Read the current state of every surface

- Read each surface in `profile/surfaces.md` as it is now (portfolio rows and their translation rows, profile README, every language version of the resume, LinkedIn, link-in-bio, team or company profile row).
- Check the open items in `profile/contradictions.md`. Fix only the ones this sync touches or this month's evidence resolves; add any new ones to the backlog instead of fixing everything at once.

## 3. Draft a minimal diff

For each surface, draft a patch with `templates/surface-patch-proposal.md` (exact current text → new text, or the exact table, row, and field):

| Surface type | How to change it | Mode |
|---|---|---|
| **Portfolio + CMS/DB** (e.g. a Postgres or headless-CMS content table, plus the site repo) | Exact row updates (table, row id, column, old → new); a repo PR for copy that lives in code | write-with-approval |
| **Code-host profile README** (e.g. `<user>/<user>` on GitHub) | A PR or commit with a minimal diff | write-with-approval |
| **LinkedIn** | Copy-paste text per field (headline, about, skills); no edit API is assumed | hint-only |
| **Resume doc** (all language versions or tabs) | Suggestion-mode edits, or exact find/replace pairs per tab; keep the versions consistent in meaning | write-with-approval |
| **Link-in-bio** | Copy-paste list of link changes; if the user owns a short-link service in a repo, a PR there | hint-only, or write-with-approval for an owned repo |
| **Company or team profile** (the user's own row, plus its translation rows) | Row updates for every language together | write-with-approval |
| **Second brain / notes repo** | A delta file for the supervisor or writer agent | delta-only |

- Respect the positioning rules in `profile/goals.md` (target title, what not to claim). Prefer understatement over overclaiming.
- **Security check** before any repo or doc patch: no secrets, keys, tokens, internal logs, or private customer data.
- If nothing qualifies, say so in one line and stop.

## 4. Approval

Send **one** short message in the user's language, grouped by surface (surface → change → evidence), and ask per surface: all / some / none / edits. No writes before an explicit yes in chat.

## 5. Apply approved patches only

- **Database:** precise UPDATE or INSERT on the approved rows. No schema changes or deletes without separate approval.
- **Code host:** commit only the approved file(s) with a clear message.
- **Docs:** targeted edits; keep the formatting.
- **Hint-only surfaces:** hand the user exact copy-paste text per field.
- Re-read each surface to verify, then report what changed, with links.

## 6. Log and hand-offs

1. Mark resolved contradictions `resolved (YYYY-MM-DD)` and add a sync line to `profile/changelog.md` (date, what changed per surface, open questions, new backlog items).
2. Queue a brain delta summarising the sync (`docs/workflows/brain-delta.md`); never write the notes repo yourself.
3. Never apply to jobs, contact anyone, or publish social posts as part of a sync. Announcing an update belongs to the user.

## Before the first checkpoint

Only fix clear factual contradictions, and only with approval. Don't announce new skills yet.
