# Workflow: weekly quiz and skill-model update

**Trigger:** the quiz day in `profile/schedule.md` (`routines/weekly-quiz.md`).

## Steps

1. Collect the week: concepts taught, drills done, scores, PRs or commits.
2. Build the quiz with `templates/quiz.md`: 5–8 questions across the week's tracks. Mix recall, "explain why", one debugging scenario, and one small design question. Weight toward the weak spots.
3. Send the quiz. Wait for answers. Don't answer for the user.
4. Score each answer 0–10 and give a total, using `templates/scoring-rubric.md`. Each answer gets one line of feedback.
5. **Update `profile/skill-model.md`:**
   - Move a level up only with new evidence: a quiz score of 7 or more on that area **plus** a drill or real work.
   - Move down if quiz answers contradict a claimed level.
   - Record the date, the score, and the evidence source (`QUIZ:YYYY-MM-DD`).
6. Plan next week: keep the rhythm, but put the weakest topic first on its track day.
7. If a durable fact changed (a level moved, a milestone was hit), queue a brain delta (`brain-delta.md`).
