# Workflow: Platform Sync (career surface sync, monthly checkpoint)

**Trigger:** the monthly routine (`routines/monthly-sync.md`), a checkpoint date in `profile/roadmap.md`, or the user asking for a sync.

**Principle:** public surfaces say exactly what the evidence proves: no more, no less. Each change is a **small patch the user approves**. No bulk rewrites.

The first alignment of the title and existing facts is a phased rollout (`docs/workflows/surface-rollout.md`), not this monthly sync. This workflow updates public copy when evidence has moved. User-stated results stay `user-reported` (`docs/evidence-levels.md`): `~` or qualitative, never embellished, never relabeled as measured.

## 0. Gate

- Run only at a configured checkpoint, or when the user asks.
- Only `proven` skills qualify for public surfaces (`docs/evidence-levels.md`). If the user's plan says "no public updates until a skill is proven", nothing below `proven` goes out, even as a hint. A `user-reported` result may stay, approximate (`~`) or qualitative, only when the user approves that exact wording. Do not add a result they did not state, and do not relabel it as measured.
- **Quick diff first.** If the skill model hasn't changed since the last sync line in `profile/changelog.md` and nothing new shipped, stop: silent on a scheduled run, one line if the user asked.

## 1. Evidence (read-only)

1. Diff the skill model against the last sync: what became `proven`? What new project, merged PR, or deployed service exists?
2. Sources: `profile/skill-model.md`, `profile/changelog.md`, quiz and drill scores, recent chats, the user's notes repo (read-only), their repos, and anything they sent.
3. Per item record: claim, evidence link or quote, evidence level, and **confirmed** vs **assumed**. Assumed items never go public. If an important one is unclear, ask **one** short question.
4. Never invent skills, titles, metrics, dates, or projects. A number needs a source. A result the user states stays `user-reported`: keep the `~` or the qualitative wording, and do not embellish it.

## 2. Read the current state of every surface

- Read each surface in `profile/surfaces.md` as it is now (portfolio rows and their translation rows, profile README, every language version of the resume, LinkedIn, link-in-bio, company, team, or studio profile row).
- Check the open items in `profile/contradictions.md`. Fix only the ones this sync touches or this month's evidence resolves; add any new ones to the backlog instead of fixing everything at once.

## 3. Draft a minimal diff

For each surface, draft a patch with `templates/surface-patch-proposal.md` (exact current text → new text, or the exact table, row, and field):

| Surface type | How to change it | Mode |
|---|---|---|
| **Portfolio + CMS/DB** (e.g. a Postgres or headless-CMS content table, plus the site repo) | Exact row updates (table, row id, column, old → new); a repo PR for copy that lives in code | write-with-approval |
| **Code-host profile README** (e.g. `<user>/<user>` on GitHub) | A PR or commit with a minimal diff | write-with-approval |
| **LinkedIn** | Copy-paste text per field (headline, about, skills). Skill names follow [LinkedIn skills](#linkedin-skills) below. No edit API is assumed | hint-only |
| **Resume doc** (all language versions or tabs) | Suggestion-mode edits, or exact find/replace pairs per tab. Follow [Resume](#resume) below | write-with-approval |
| **Link-in-bio** | Copy-paste list of link changes; if the user owns a short-link service in a repo, a PR there | hint-only, or write-with-approval for an owned repo |
| **Company, team, or studio profile** (the user's own row, plus its translation rows) | Row updates for every language together | write-with-approval |
| **Second brain / notes repo** | A delta file for the supervisor or writer agent | delta-only |

- Respect the user's positioning (target role in `profile/goals.md`, anything they asked you not to claim). Prefer understatement over overclaiming.
- **Security check** before any repo or doc patch: no secrets, keys, tokens, internal logs, or private customer data.
- If nothing qualifies, say so in one line and stop.

### Resume

One page is a hard limit, on every language version.

- Keep the language versions in parallel: same meaning, edited together, each still one page.
- After every edit, including a font or spacing change, check the rendered page count (print preview or export). Do not trust the editor's zoom.
- A font or spacing change can reset bold weights or drop links without changing the words. Re-check styling and links after those edits.
- If a change spills onto a second page, cut or tighten until each version is one page again, then re-check. Do not shrink the font blindly and call it done.

### LinkedIn skills

Hint-only. Draft the text; the user applies it.

- Name **capabilities**, not vendor products or tool brands. Write `Workflow Automation`, not the automation product. Write `Large Language Models (LLM)`, not the gateway product.
- Frameworks and widely recognized protocols may be skills. They name a way of working, not one vendor's console.
- Pick the string from LinkedIn's own suggestions so the saved name matches the product.
- **Top Skills** mix the core foundation (for example backend) with the target direction, and they match the locked title in `profile/profile.md`.
- On each experience and each project, tag 4–7 relevant skills. Not the whole inventory.
- Keep skills that already exist, so endorsements stay attached. Add or retitle; do not delete a skill only to tidy the list.
- LinkedIn may only let the user curate **Top Skills**, not reorder the full list. Say so in the hint. Do not propose a full-list order the UI cannot save.

## 4. Approval

Send **one** short message in the user's language, grouped by surface (surface → change → evidence), and ask per surface: all / some / none / edits. No writes before an explicit yes in chat.

## 5. Apply approved patches only

- **Change safety.** Save a before-snapshot and a rollback first, unless `profile/surfaces.md` records an opt-out for this low-risk polish phase. Tell the user where the snapshot is.
- **Database:** precise UPDATE or INSERT on the approved rows. No schema changes or deletes without separate approval.
- **Code host:** commit only the approved file(s) with a clear message.
- **Docs:** targeted edits; keep the formatting.
- **Hint-only surfaces:** hand the user exact copy-paste text per field.
- Re-read each surface and verify the words and the links. On a resume, verify rendered page count, bold, and links on every language version.
- If the portfolio has a transparency section, propose its new changelog line in this same approval (`docs/workflows/portfolio-transparency.md`). Apply that line only after this sync is verified (step 6).

## 6. Log and hand-offs

1. Mark resolved contradictions `resolved (YYYY-MM-DD)` and add a sync line to `profile/changelog.md` (date, what changed per surface, open questions, new backlog items).
2. Queue a brain delta summarising the sync (`docs/workflows/brain-delta.md`); never write the notes repo yourself.
3. Never apply to jobs, contact anyone, or publish social posts as part of a sync. Announcing an update belongs to the user.
4. If a portfolio transparency changelog line was approved with this sync, apply that one line now (`docs/workflows/portfolio-transparency.md`).

## Before the first checkpoint

Only fix clear factual contradictions, and only with approval. Don't announce new skills yet. Title and fact alignment belongs to the phased rollout (`docs/workflows/surface-rollout.md`), not to a second pass here, unless the user asks.
