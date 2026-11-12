# Workflow: roadmap builder

**Goal:** a plan from today to `<DEADLINE>` that closes the biggest gaps through real, production-linked work.

## Steps

1. Count the weeks from the next start day to `<DEADLINE>`.
2. Take the tracks and the weekly rhythm from `profile/schedule.md`. **Tracks run in parallel every week.** Don't propose a sequential plan unless the user asks for one.
3. Give each 1–2 month block a **primary emphasis** and one **milestone tied to real work**: something that ships or gets used at work or in a real project. Pattern:
   - Block 1: build or rewrite a real service in the target language and framework, plus database basics.
   - Block 2: a domain-specific service, e.g. RAG with a vector store and evals.
   - Block 3: put the services on the target infrastructure, e.g. a light Kubernetes distribution plus config management, in a **test environment**.
   - Block 4: an advanced capability (e.g. an agent framework plus observability), then **public proof** (a repo or case study).
   Secondary tracks (e.g. frontend) run steadily with smaller milestones.
4. Add **Platform Sync checkpoints**, monthly, starting at the end of the first milestone block. Aligning surfaces before that is the phased rollout (`docs/workflows/surface-rollout.md`), not an extra checkpoint.
5. Add any **one-time urgent items** first (e.g. a security fix from the audit).
6. For each track, show the current and target level, taken from `profile/skill-model.md`.
7. **Deliverables:**
   - **A visual roadmap:** month timeline, tracks as lanes, milestones, weekly rhythm, current vs target. Use whatever page or doc tool you have.
   - **A mind map** of tracks → skills → milestones. Prefer a whiteboard tool you can actually write to (FigJam, Excalidraw, Miro, Canva…). Check each one live, use the first that works, and tell the user which ones needed auth.
   - **Task manager structure:** a parent project with one sub-project per track, plus "Weekly Review" and "Platform Sync". Put 4–8 tasks in each: the milestones with due dates at block ends, plus week one's concrete tasks on their rhythm days. **Search for existing projects first** to avoid duplicates. The security item goes in Platform Sync at the highest priority.
8. Write the summary to `profile/roadmap.md` and the links to `profile/links.md`.

## Rules
- Due dates go in the user's timezone and calendar. If they use a non-Gregorian calendar, show both.
- Keep it modest: fewer, real tasks beat many vague ones.

## Learning roadmaps shown on a portfolio

These are the study plans displayed on the portfolio. They are separate from the deadline roadmap above.

- Length and the current step match reality.
- A skill the user already knows at a basic level gets an advanced roadmap, not a beginner track.
- A new skill gets a short intro roadmap.
- Do not mark a one-step roadmap completed. Extend it to the real remaining work, or leave the step open.

## Before applications (final phase)

**Trigger:** phase-2 polish in `docs/workflows/surface-rollout.md` is verified, and the user is about to send applications. You still do not apply, message anyone, or post.

1. **Second brain.** Hand a delta to the supervisor or writer agent (`docs/workflows/brain-delta.md`). You do not write the notes repo.
2. **This public repo.** If the run taught a generic lesson, update this repo with that lesson only. No names, employers, URLs, metrics, titles, or project names. Placeholders stay as in `profile.example/`.
3. **Learning routines.** Start the daily, weekly, and monthly routines again (`routines/README.md`). The polish pass does not replace practice.
4. **Private package (optional).** The user may keep an owner-specific skill or agent package in a private repo. Do not put that personal data in this public repo.
5. **Independent resume screen.** Score the one-page resume against a target job description the user supplies (`<TARGET_JOB_DESCRIPTION>`). Use a pass that sees the resume and the description, not the drafting chat. Report fit and gaps. Change the resume only if the user approves a patch.
