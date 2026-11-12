# Routine prompt: monthly Platform Sync

Run `docs/workflows/platform-sync.md`.

- **Gate:** if the skill model hasn't changed since the last sync line in `profile/changelog.md` and nothing new shipped, stop. Send nothing (or one line if the user asked for this run).
- Surfaces come from `profile/surfaces.md`; never hard-code them here.
- List the skills that became `proven` since the last sync, with evidence, and the contradictions this resolves. Skip anything below `proven` or merely assumed. Leave a `user-reported` result as the user stated it (`~` or qualitative): do not drop it and do not upgrade it.
- Draft one small patch per surface with `templates/surface-patch-proposal.md`, after a secrets check.
- Send a single approval message, grouped by surface. Apply only approved patches on `write-with-approval` surfaces, then re-read to verify. For hint-only surfaces (often LinkedIn, link-in-bio), give exact copy-paste text per field.
- Update `profile/contradictions.md` and `profile/changelog.md`, and queue a brain delta.
- Follow change safety in `profile/surfaces.md`: snapshot and rollback before a write, unless this polish phase is opted out.
- If the portfolio has a transparency section, update its changelog from the sync log after the sync is verified (`docs/workflows/portfolio-transparency.md`).
- If this is before the first checkpoint in `profile/roadmap.md`, propose only factual contradiction fixes. Title alignment belongs to `docs/workflows/surface-rollout.md`.
