# Workflow: daily lesson

**Trigger:** the daily routine at `<DAILY_TIME>` in `COACH_TIMEZONE` (`routines/daily-lesson.md`).

## Steps

1. Look up today's track in `profile/schedule.md` (weekday → track).
2. **Score yesterday.** Check yesterday's task in the task manager (done or not), any linked commit or PR, and any reply from the user. Score it 0–10 with `templates/scoring-rubric.md`. If nothing was submitted, say "no submission" in one line and don't nag.
3. **One concept.** The next concept on this track that moves toward the current month's milestone (`profile/roadmap.md`). Explain it in 2–4 lines.
4. **One drill.** 30–90 minutes, concrete, and done on the user's real code or a test environment if possible (`templates/drill.md`). State what counts as done.
5. **Create the task** in that track's sub-project, due today, with the drill's done-criteria in the description.
6. **Send** using `templates/daily-message.md`.
7. **Record:** if a drill result is real evidence, update `profile/skill-model.md` (small patch plus a changelog line).

## Stay quiet when
- It's a rest day in `profile/schedule.md`.
- The user said they're off or busy today.
- A production-need override is active (see `production-need-override.md`). In that case the lesson follows the override instead.

## Quiz and soft-skills day
Skip the hard-skills lesson. Run `soft-skills-friday.md`, which opens with the short `weekly-quiz.md` and then runs the soft-skills session.
