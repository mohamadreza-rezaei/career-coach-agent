# Integrations

The agent works with whatever's connected. Anything missing drops to **hint mode**: the agent drafts and the user applies. Secrets come from env vars or the platform's secret store only (names in `.env.example`).

| Need | Typical tool | Env var name(s) | Used for | Mode |
|---|---|---|---|---|
| Code host | GitHub API / MCP / `gh` | `GITHUB_TOKEN` | read repos and the profile README; PRs to allowed repos | read + write-with-approval |
| Portfolio and team-page CMS | Supabase (direct MCP or via Composio's Supabase toolkit), or any Postgres or headless CMS | `SUPABASE_ACCESS_TOKEN` or `COMPOSIO_API_KEY` | read-only SQL during audits; approved row updates at syncs | read + write-with-approval |
| Resume | Google Docs / Drive API | `GOOGLE_OAUTH_CREDENTIALS` | read all tabs; suggestion-mode edits | read + write-with-approval |
| Tasks | Todoist (or Linear, ClickUp, Things…) | `TODOIST_API_TOKEN` | the roadmap project, daily drill tasks, milestones | write |
| Mind map | FigJam (Figma), Excalidraw, Miro, Canva | `FIGMA_ACCESS_TOKEN` (optional) | tracks → skills → milestones map | write |
| LinkedIn | Official API or Composio LinkedIn | `LINKEDIN_ACCESS_TOKEN` or `COMPOSIO_API_KEY` | **read-only** profile basics; edits are hints | read / hint-only |
| Link-in-bio | Usually no API | — | hints, or PRs to a self-hosted short-link repo | hint-only |
| Notes / second brain | Git repo or vault | (read via `GITHUB_TOKEN`) | read protocol and career notes; hand over deltas | read + delta-only |
| Reports / pages | Any doc or page tool | — | baseline report, roadmap page | write |
| Scheduler | Platform cron / OpenClaw jobs / GitHub Actions | — | daily, weekly, monthly routines | — |
| Config | — | `COACH_TIMEZONE`, `COACH_LANGUAGE` | voice and time | — |

## Least privilege
- Write tokens only for surfaces marked `write-with-approval`.
- Database access: read-only by default. Writes are exact row updates after approval.
- Never pass tokens in prompts, task descriptions, commits, or logs.
