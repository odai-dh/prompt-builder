# Before / after examples

> STATUS: seeded from iteration-1 evals. Add more pairs from good runs.

## 1. Already-strong prompt, user said "skip questions" (Improve, experienced)

**Rough prompt:** "You are a senior TS dev. Refactor the attached Next.js API routes to use zod validation, keep the response shapes, return a diff."

**Questions asked:** none.

**Final prompt:**
```
Refactor the attached Next.js API routes to validate input with zod (safeParse, z.infer for types). Keep success response shapes, status codes and headers unchanged. On validation failure return 400 in the route's existing error format. Return one unified diff, then list any behavior changes.
```

**What I changed:** dropped the persona; defined the failure response and the output format.

**Run it with:** Sonnet 5.5, medium effort. Cheaper: Haiku 4.5 for a few simple routes.

**Assumptions:** zod is already installed; 400 is the right status.

Why this is the model: the original was nearly right, so the result is shorter than a "full" rewrite. Extra rules about version detection, dependencies or running tests would be scope the user didn't ask for.

## 2. Vague writing request (Improve, newer user)

**Rough prompt:** "make this better: write me a blog post about AI"

**Questions asked (one round):** 1) who reads it, 2) angle (explainer / practical / opinion), 3) length and voice.

**Final prompt (after answers 2, 2, medium):**
```
Write a 1,000-word blog post for business owners on practical ways to use AI at work this month. Friendly but credible. Three concrete examples, one honest limitation, and a closing call to action. Avoid jargon and hype words.
```

**Run it with:** Sonnet 5.5, low effort. Cheaper: Haiku 4.5 for a first draft you will rewrite.

## 3. Agentic task with ambiguous destructive verbs (Improve for Cowork)

**Rough prompt:** "clean up my downloads folder and update the project notes"

**Questions asked:** what "clean up" means (plan only / sort / sort + move junk to a review folder / delete), what to leave alone, what "update" means. Draft-first is not asked; it is built in by default.

**Final prompt (after answers: sort and move junk to a review folder; leave the last 30 days alone; log what was cleaned up):**
```
In ~/Downloads, sort files into subfolders by type. Move duplicates and installers to a folder called "To review"; do not delete anything. Leave files changed in the last 30 days where they are. First show me a plan listing what you will move and wait for my OK. Then draft a dated entry for the project notes describing what you did and show it to me before saving. Stop when the folder is sorted and the draft is shown.
```

**Run it with:** Sonnet 5.5, low effort. Bounds matter more than reasoning here.

**Assumptions:** the plan-first and draft-first steps are on by default because the task moves files and edits notes; remove them if you trust the result. The "To review" folder is inside Downloads. "Last 30 days" is by modified date.

## 4. Symptom, not a prompt

**User:** "claude keeps giving me really generic answers when I ask for marketing ideas, why?"

**Response shape:** two sentences on the cause (no business, goal or constraints, so Claude averages over every business), the missing specifics as a short list, then at most 2 questions (what are you marketing, what is the goal) and an offer to rebuild their prompt.

## 5. Swedish request (Build/Improve, language rule)

**Rough prompt:** "kan du göra den här prompten bättre: sammanfatta mötet"

**Questions asked, in Swedish:** what the summary is for, desired format, what Claude will receive (transcript, notes, file).

**Final prompt:** in Swedish, since the summary is for Swedish readers; in English if the user says the audience is English-speaking.

**Run it with:** Sonnet 5.5, low effort. Cheaper: Haiku 4.5 for short, clean notes.
