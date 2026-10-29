# Career Coach Agent

A portable, evidence-first **career coach and mentor** for software engineers, packaged as plain Markdown so that any LLM agent can run it. That includes OpenClaw, Claude/Codex-style coding agents, Cursor background agents, custom LangGraph bots, and others.

Give an agent this repo, and once you've finished onboarding it will:

- **Audit** your public career surfaces (portfolio, GitHub, LinkedIn, resume, link-in-bio, team page, notes) and build a **skill model backed by evidence**. Every claim gets a source and an evidence level.
- **Build a roadmap** to your deadline: parallel weekly tracks, monthly milestones tied to real work, and a mind map plus task-manager structure.
- **Teach daily.** It scores yesterday's work, teaches one concept, and gives one drill, then logs the drill as a task.
- **Quiz weekly.** It updates the skill model with direct scores.
- **Coach soft skills weekly.** After a short quiz, it covers one topic with a real framework, a role-play, and a real-world exercise. Topics include demoing to non-technical teams, driving adoption, boundaries, feedback, workplace conduct, technical leadership and founder pitching.
- **Run monthly Platform Syncs** that put *only proven* skills on your public surfaces, as small patches you approve.
- **Propose updates** to your second brain or notes repo via a supervisor/writer agent. It never writes there directly.
- **Handle security findings** found during audits, such as committed secrets, without opening or leaking them.

It will never apply for jobs, do outreach, publish anything, invent skills or metrics, or commit secrets.

## Repo layout

| Path | What it is |
|---|---|
| `AGENTS.md` | **The system prompt.** Load this first. It covers role, scope, hard rules, voice and the decision loop. |
| `setup/onboarding-interview.md` | First-run interview that fills your `profile/` from the templates |
| `profile.example/` | Templates with placeholders (`<YOUR_NAME>`, `<TARGET_ROLE>`, `<DEADLINE>`, `<SURFACES>`…). Copy to `profile/` |
| `docs/evidence-levels.md` | How claims are graded |
| `docs/voice.md` | Tone, length, language, examples |
| `docs/workflows/` | Step-by-step procedures: onboarding audit, roadmap builder, daily lesson, weekly quiz, soft-skills day, platform sync, brain delta, production-need override, security findings |
| `routines/` | Portable schedules (cron lines + prompts): daily lesson, weekly quiz, soft-skills day, monthly sync |
| `templates/` | Scoring rubric 0–10, drill, quiz, role-play, skill-model entry, surface patch proposal, brain delta, daily message |
| `integrations.md` | Which tools the agent needs and the env var **names** it expects |
| `.env.example` | Env var names only. Real values never go in git |

## Quick start

1. **Fork or clone** this repo into the agent's workspace.
2. Copy the templates: `cp -r profile.example profile`. The `profile/` folder is git-ignored by default, so your personal data stays local. Remove that line from `.gitignore` only if your fork is private and you want it versioned.
3. Set the env vars from `.env.example` in the agent's runtime or secret store, never in files.
4. Load `AGENTS.md` as the agent's system prompt or instructions file.
5. Send the agent: **"Start onboarding."** It runs `setup/onboarding-interview.md`, then `docs/workflows/onboarding-audit.md`, then `docs/workflows/roadmap-builder.md`.
6. Install the routines from `routines/`, using your agent platform's scheduler or plain cron.

### OpenClaw

- Put this repo in the agent's workspace. Point the agent's instructions or system prompt at `AGENTS.md`. Most OpenClaw setups read `AGENTS.md` at the workspace root automatically.
- Keep `profile/` in the same workspace so the agent can read and update it.
- Register the three routines from `routines/README.md` as scheduled jobs (cron syntax plus the prompt file).
- Connect the integrations you have (see `integrations.md`). Anything missing degrades to "hint mode", where the agent drafts the change and you apply it.

### Other agents

Any agent that can (a) read files, (b) call a few tools and (c) run on a schedule can host this. Use `AGENTS.md` as the system prompt and give it read access to the repo. If your platform has no scheduler, trigger the routine prompts from cron with a CLI call.

## Principles in one breath

Evidence over vibes. Small patches over rewrites. Teach and score; don't flatter. Stay quiet when nothing is new. Nothing public without your yes. Secrets live in env vars only.

## License

MIT. See `LICENSE`.
