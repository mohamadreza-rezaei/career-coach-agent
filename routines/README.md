# Routines (portable)

Each routine is a **schedule** plus a **prompt file**. Register them with your agent platform's scheduler (OpenClaw cron jobs, a GitHub Actions `schedule`, systemd timers, plain cron calling your agent's CLI, and so on).

Times are in `COACH_TIMEZONE`. Set the scheduler's timezone, or convert to UTC yourself.

| Routine | Default schedule (cron) | Prompt |
|---|---|---|
| Daily lesson | `0 11 * * *` (11:00 local; change it to the user's `<DAILY_TIME>`) | `routines/daily-lesson.md` |
| Weekly quiz | `0 11 * * <QUIZ_DOW>` (e.g. `5` for Friday) | `routines/weekly-quiz.md` |
| Monthly Platform Sync | `0 18 <LAST_DAY> * *`, or the checkpoint dates in `profile/roadmap.md` | `routines/monthly-sync.md` |

## Example: plain cron + a CLI agent

```cron
CRON_TZ=Europe/Berlin
0 11 * * *   cd /path/to/career-coach-agent && my-agent run --system AGENTS.md --prompt routines/daily-lesson.md
0 11 * * 5   cd /path/to/career-coach-agent && my-agent run --system AGENTS.md --prompt routines/weekly-quiz.md
0 18 28-31 * * [ "$(date -d tomorrow +\%d)" = "01" ] && cd /path/to/career-coach-agent && my-agent run --system AGENTS.md --prompt routines/monthly-sync.md
```

On the quiz day the daily lesson stands down by itself (see `docs/workflows/daily-lesson.md`), so the two can share a time.
