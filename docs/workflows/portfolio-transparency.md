# Workflow: portfolio transparency section

**Trigger:** the user wants the portfolio to say how it is maintained, or a rollout step or Platform Sync was just approved and the section already exists.

Optional. Do not add it unless the user asks, or they already approved this section.

Examples here stay generic. Real names and URLs belong only on the user's own surface, never in this public repo.

## What the section contains

Title it **Content accuracy** or **How this portfolio is maintained**. Four parts:

1. **Last updated and changelog.** A date, plus a short log of surface updates (what changed, which surface, the date). The log is data-driven: only rows that match an approved, verified step in `profile/changelog.md`. No entries for drafts or rejected patches.
2. **The process.** Background intake, the platforms that are connected, quizzes, drills, and scoring, then small patches. The user approves every public change.
3. **Honesty notes.** Skill scores are calibrated self-assessments, not certifications. Results are measured or estimated. Estimated and `user-reported` results stay approximate (`docs/evidence-levels.md`).
4. **This agent.** A link to the public career-coach repo (`<CAREER_COACH_REPO_URL>`). Not a personal fork, a private notes repo, or an owner-specific package.

## Steps

1. Propose the exact copy with `templates/surface-patch-proposal.md`. Include only skills and results that are `proven` or explicitly `user-reported`.
2. Wait for a yes for this exact section.
3. Apply it under the change-safety setting in `profile/surfaces.md`.
4. After every later approved sync or rollout step, patch **only** the last-updated date and the new changelog line. Propose that one-line patch with the sync. Do not rewrite the section.

## Do not

- Name private tools, tokens, or platforms that are not connected.
- Claim a certification, an audit, or a third-party endorsement.
- Treat the section as a substitute for evidence on the skill model.
