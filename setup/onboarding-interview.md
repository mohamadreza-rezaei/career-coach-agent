# Onboarding interview (first run)

Run this once, before the audit. Ask **one question at a time**, in the user's language, and keep each question short. Write the answers into `profile/` (copied from `profile.example/`) as you go.

1. **Goal:** "Where do you want to be on <DEADLINE>? A specific role or company type, or your own thing? One sentence." → `profile.md` (target role, deadline, reason)
2. **Prior material:** "Any earlier research, career notes, or AI chats about your positioning I should read first?" Read it critically: separate what the user actually said from what a tool filled in.
3. **Self-assessment per area:** for each area (backend, language X, frontend, DevOps, specialisation, databases), "Honest level, and where can I see proof?" → `skill-model.md` with `self-rated` / `claimed`
4. **Real work:** "What runs in production today that you built or own? Who uses it?" → `profile.md`, plus evidence leads
5. **Surfaces:** "Where do you present yourself? Portfolio (and where its content lives), code host, LinkedIn, resume (which languages), link-in-bio, company or team page, notes repo." For each: the identifier, plus who may write → `surfaces.md`
6. **Notes repo writer:** "Do you have a second brain? Who is allowed to write it?" → `surfaces.md` (delta-only, writer)
7. **Tracks and rhythm:** "Which 3–5 tracks? Which weekday for each? Quiz day? Daily time and timezone?" → `schedule.md`. Default: parallel tracks.
8. **Constraints:** hours per day, days off, devices, work rules (e.g. a test environment only for infra practice) → `profile.md`, `schedule.md`
9. **Publishing stance:** "Should public surfaces change now, or only after skills are proven?" Default: after proof, at monthly checkpoints → `roadmap.md`
10. **Integrations:** check which tools from `integrations.md` are connected. List what's missing in one message.

Then say, in one or two lines, what you'll do next (audit, then roadmap), and start `docs/workflows/onboarding-audit.md`.
