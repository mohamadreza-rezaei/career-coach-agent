# Workflow: surface rollout (first alignment)

**Trigger:** the user asks to align public surfaces, or the audit found title and fact drift they want fixed. New skills still wait for `proven` evidence (`docs/workflows/platform-sync.md`).

**Principle:** one surface at a time. Propose the exact diff, get a yes for that diff, apply it, verify it. Then the next surface.

## Title lock (do this first)

Decide once, write it in `profile/profile.md`, and use it everywhere.

- **Primary title:** the honest official job title plus a short focus descriptor: `<OFFICIAL_TITLE> · <FOCUS_AREA>`.
- Do not inflate the title. No seniority, scope, or role the user does not hold.
- A per-surface variant is allowed only when that field is shorter or more formal. Record each variant in `profile/profile.md`. If a surface can show the primary title, it shows the primary title.
- After the lock, a title mismatch is a contradiction to fix toward the lock, not a new branding idea.

## Change safety

Default: before every surface write, save a before-snapshot and a rollback (the exact old text, or a revert commit). Tell the user where the snapshot lives.

The user may opt out for a named low-risk polish phase. Record the choice, the phase, and the date in `profile/surfaces.md`. Opt-out does not skip approval or the verify step.

## MVP pass (this order)

1. **Identity.** Lock the title and the one-line positioning. No other copy yet.
2. **Portfolio.** Make it the detailed source of truth for projects, skills, and results. The other surfaces follow it. Optional transparency section: `docs/workflows/portfolio-transparency.md`. Learning roadmaps on the portfolio follow the rules in `docs/workflows/roadmap-builder.md`.
3. **LinkedIn.** Headline, about, experience, skills. Skill names follow the LinkedIn skills section in `docs/workflows/platform-sync.md`.
4. **Code-host profile** (the profile README).
5. **Company, team, or studio profile, and link-in-bio.** Align the public row and the short links together.
6. **Resume.** One page, every language version in parallel. Rules: the resume section in `docs/workflows/platform-sync.md`.

## Each step

1. Draft the exact diff with `templates/surface-patch-proposal.md`.
2. Wait for an explicit yes for **this** diff.
3. Apply only that diff. Snapshot first, unless this phase is opted out in `profile/surfaces.md`.
4. Re-read the live surface and verify the words and the links. On a resume, also verify page count and styling (see platform sync).
5. Log the step in `profile/changelog.md`. If the portfolio has a transparency changelog, update it from that log (`docs/workflows/portfolio-transparency.md`).

Stop after the step you finished. Do not start the next surface in the same turn unless the user already approved that diff too.

## Phase 2 (polish, before applications)

A second pass over the same order for consistency, tone, and anything the MVP left rough. Still one approved diff at a time. Low-risk wording and formatting may use the change-safety opt-out if the user recorded it.

When phase 2 is verified, run the final-phase checklist in `docs/workflows/roadmap-builder.md`. That checklist does not include sending applications.
