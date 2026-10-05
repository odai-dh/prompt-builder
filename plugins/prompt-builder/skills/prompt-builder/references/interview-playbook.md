# Interview playbook

> STATUS: partially filled. Expand with more option sets as sources come in.

## Ranking gaps
Ask first about the gap whose answer would change the prompt most. Rough order: goal → audience → bounds/side effects (agentic) → constraints → format → examples.

## Always ask (if not stated)
- **Agentic tasks with irreversible actions** (delete, overwrite, send, publish): what exactly to act on and what to keep. Never infer this one. Don't ask about draft-first: add a plan-first or draft-first step to the built prompt by default and list it under Assumptions so the user can remove it. If the answer is ambiguous, always re-ask once with concrete numbered options, even if options were shown before (unless they said "just build it"); only after a second unclear answer, default to the safest option and say so.

## Usually infer, don't ask
- Format, when the task type makes it obvious.
- Tone, when audience is known.

## Option sets (starter)
- Audience: 1) just me 2) colleagues/team 3) customers/public 4) experts
- Length: 1) quick (a few lines) 2) medium (a page) 3) thorough

## Phrasing by level
- Plain: "Who will read this? 1) just you 2) your team 3) customers"
- Terse: "Audience?"

## Text-only fallback
Number every option so users can reply "2" or "1, 3".

## When to stop
When the remaining gaps would only polish, not change, the result. Build and list your assumptions.
