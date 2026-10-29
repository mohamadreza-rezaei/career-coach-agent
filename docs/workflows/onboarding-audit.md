# Workflow: onboarding audit (read-only)

**Goal:** an evidence-graded baseline of the user's skills and of every career surface, with **no changes anywhere**.

## Inputs
- `profile/surfaces.md` (filled during `setup/onboarding-interview.md`)
- What the user said in chat: their self-assessment, real work, goals

## Steps

1. **Access check.** For each surface, confirm what you can read and what you could write, using harmless read calls. Record it in a table: `surface | read? | write? | identifier | blocker`. Missing access is a blocker you report, not a reason to guess.
2. **Read every surface:**
   - **Portfolio site + its CMS/DB:** read the live site and the content tables, with read-only queries (`SELECT` only). Note title, summary, skill list, project list, and metrics.
   - **Code host (e.g. GitHub):** profile README; list all repos (language, last push, stars, private or public). For the key repos, look at structure, tests, CI, Docker, README quality, and commit cadence. Note template-generated folders.
   - **LinkedIn:** read whatever the API allows (often only name and headline). Public pages are often blocked. Say so.
   - **Resume doc:** every tab or language version.
   - **Link-in-bio / short-link service:** where each link points.
   - **Company or team profile:** the user's own row only, in every translation.
   - **Second brain / notes:** read the protocol files first (`AGENTS.md`, `BRAIN.md` or equivalent), then the career, goals, and profile notes. Read-only.
3. **Build the skill matrix.** One row per area (e.g. backend, language X, frontend, DevOps, specialisation, automation, databases, ownership), each with a level estimate, an evidence level (`docs/evidence-levels.md`), the key proof, and source tags.
4. **Build the project inventory:** name, what it is, stack, status, public or private, evidence link.
5. **Surface consistency table:** what each surface says for title, summary, and skills.
6. **Contradictions list:** titles, dates, numbers, roles, versions, and project names that disagree. Write them to `profile/contradictions.md` with status `open`.
7. **Gaps vs goals:** the 5–8 biggest, ranked.
8. **Fixes per surface:** copy suggestions only. Nothing is applied during the audit.
9. **Security scan (names only).** If you see committed files whose names suggest secrets, user data, or logs, list the paths and **don't open them**. Then follow `security-findings.md`.
10. **Deliver:**
    - a report the user can come back to (a page, doc, or Markdown file);
    - `profile/skill-model.md` filled using `templates/skill-model-entry.md`;
    - a short chat summary with the verdict, top 5 contradictions, access problems, and any security flag.

## Rules
- Never invent. Unknown means "not found", plus where you looked.
- Tag every claim with its source.
- Mark AI-written or unsourced metrics as **unverified**.
