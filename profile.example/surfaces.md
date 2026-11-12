# Career surfaces

> Identifiers only: repo names, table names, doc IDs, URLs. **Never credentials.**

| Surface | Identifier | Read | Write mode | Notes |
|---|---|---|---|---|
| Portfolio site | <SITE_URL> | <yes/no> | write-with-approval | |
| Portfolio CMS/DB | <PROVIDER>: project <PROJECT_ID>, tables <TABLES> | | write-with-approval | read-only SQL during audits |
| Portfolio repo | <OWNER/REPO> | | write-with-approval | |
| Code-host profile README | <OWNER/OWNER> | | write-with-approval | |
| LinkedIn | <PROFILE_URL> | <API limits> | hint-only | |
| Resume doc | <DOC_ID>, tabs: <LANGS> | | write-with-approval (suggestions) | keep all language tabs in sync |
| Link-in-bio | <URL> | | hint-only | |
| Short-link service (if owned) | <OWNER/REPO> | | write-with-approval | |
| Company / team / studio profile | <PROVIDER>: <TABLE> + <TRANSLATION_TABLE>, row <ID> | | write-with-approval | the user's own row only |
| Second brain / notes | <OWNER/REPO or path> | | delta-only (writer: <AGENT_NAME>) | follow its protocol files |

## Decisions (record these; do not leave them implicit)

- **Change safety:** <snapshots (default) | opt-out for low-risk polish>
  - Snapshots mean a before-copy and a rollback (old text or a revert commit) before every surface write.
  - Opt out only for a named polish phase. Record the phase and the date: `<phase>, <YYYY-MM-DD>`. Approval and verify still apply.
- **Rollout:** <not started | MVP step <1–6> | phase-2 polish | done>. Order: `docs/workflows/surface-rollout.md`.
- **Title:** locked in `profile/profile.md`. If a surface cannot show the primary title, put the variant in that row's Notes (`title: <variant>`).
- **Portfolio transparency:** <off | on>. When on, its changelog follows approved steps (`docs/workflows/portfolio-transparency.md`).
