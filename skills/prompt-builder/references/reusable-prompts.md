# Reusable prompts

Prompts that load on every message: custom instructions, system prompts, CLAUDE.md, skills, subagent and slash-command prompts. Every line costs tokens on every request, and mistakes repeat everywhere. On Claude 5 models, the usual fix is to cut, not add.

## Principles for Claude 5 models

**Judgement over rules.** For each absolute rule ("never…", "always…"), ask: does it prevent a real disaster, or just correct a habit? Keep disaster rules. Rewrite habit rules as one sentence describing the outcome ("match the style of the surrounding code").

**Say it once, in the right place.** Repetition across layers is no longer needed and creates conflicts. Tool guidance goes in the tool description; project facts in CLAUDE.md; procedures in skills.

**Look for conflicts between layers.** A system prompt, a skill and a user request that disagree ("document as needed" vs "no comments") force Claude to spend effort resolving them. Flag contradictions to the user.

**Progressive disclosure.** Don't front-load everything Claude *might* need. Keep the always-loaded file short and point to separate files or skills that load when relevant.

**Rich references beat descriptions.** A test suite, a code sample, an HTML mockup or a rubric gives Claude clearer guidance than prose or a screenshot.

## CLAUDE.md
- One or two lines on what the repo is for.
- Spend the rest on gotchas Claude can't see: unusual conventions, traps, "types live only in X".
- Leave out anything obvious from the file tree or code.
- Long procedures (verification, release steps) → their own skill, referenced from CLAUDE.md.
- Don't use it as a memory dump; current Claude saves relevant memories automatically.
- In Claude Code, `/doctor` can help trim CLAUDE.md and skills.

## Custom instructions / system prompts
- State who the user is and the context Claude can't infer.
- Phrase preferences with their reason.
- Remove instructions the current model already follows by default.

## Skills
- Lightweight guides that encode opinions and know-how specific to the user, team or product.
- Strict wording only where the stakes are high.
- Split long skills into files loaded as needed.

## Subagents and slash commands
- One clear job per prompt, with the inputs it receives and what it must return.
- Bounds for anything that edits, deletes or sends (see techniques.md → Agentic safety).

## What the plugin should do in Reusable mode
1. Ask what file it is and where it runs, if not obvious.
2. Mark lines as: keep / rewrite as outcome / move elsewhere / delete.
3. Show the trimmed version plus a short list of what moved or was cut and why.
4. Mention the per-message token saving in plain terms.
