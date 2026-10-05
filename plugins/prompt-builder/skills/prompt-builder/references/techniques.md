# Techniques

A toolbox, not a checklist. Pick only what the task needs. Shorter prompts with the right parts beat long prompts with every technique.

**Current Claude models (5 generation) need less scaffolding than older ones.** They use judgement well, so describe the outcome you want instead of stacking rules, and don't repeat instructions. Reserve strict rules for things that would be costly or irreversible to get wrong.

## Core (use almost always)

**Be explicit.** Lead with the action. State what the output should include and how deep to go. If they want ambitious output, ask for it; Claude won't assume it.

**Give the reason.** Attach the why to important rules. It lets Claude handle cases the rule didn't cover.

**Be specific.** Add the constraints, audience and structure the task depends on.

**Allow uncertainty.** For facts and analysis, say what to do when information is missing instead of guessing.

## Situational

**Examples.** On current models, examples can narrow what Claude explores, so use them mainly to pin an exact output format or a voice that's hard to describe. Start with one, and make sure it shows only behavior you want. For open-ended or creative work, describe the goal instead.

**Rich references.** Point Claude at real material rather than describing it: a code sample, a test suite as the spec, an HTML mockup instead of a design description or screenshot, a rubric for "what good looks like".

**Thinking / step-by-step.** Current Sonnet and Opus think adaptively, so for harder reasoning recommend a higher effort level (see models-and-effort.md) rather than "think step by step". Ask for visible, structured reasoning only when the user needs to review it.

**Format control.** Describe the format you want rather than banning formats. The prompt's own style leaks into the response: a heavily bulleted prompt invites bullets.

**Prefill: don't recommend it.** Recent Opus models reject prefilled assistant messages. For exact formats, describe the format precisely or use structured outputs in the API.

**Prompt chaining.** Split a big task into focused steps (draft → review → revise). Costs more calls, but each step is more reliable. Suggest it when one prompt is asked to do many things.

**Long content.** Put the critical instruction at the start or end, not buried in the middle of a long document.

## Use sparingly on current models

**XML tags.** Only for prompts mixing several kinds of content where boundaries must be unmistakable. Otherwise clear headings and "using the data below…" are enough.

**Role prompting.** Usually better to state the perspective ("focus on risk and long-term growth") than to assign a persona. If a role helps (consistent voice across many outputs), keep it simple, never exaggerated.

## Agentic safety (Cowork, Claude Code, scheduled tasks)

- **Disambiguate destructive verbs.** "Cut", "update", "clean up", "remove" can mean very different actions. If the wrong reading is irreversible, spell out the action and what must survive: "remove the section from the draft, keep the file."
- **Name the bounds.** Which files or records, which time range, what not to touch, whether to message anyone. Clear bounds also make drift easy to spot.
- **Draft before acting** for anything unattended or not yet proven: draft for review instead of sending, publishing or deleting.
- **Define done.** Say what finished looks like so the agent stops at the right point.

## Symptom → fix (when the user describes a problem instead of pasting a prompt)

| Symptom | Likely fix |
|---|---|
| Too generic | Add specifics, audience, an example; ask explicitly for depth |
| Misses the point | State the real goal and why it matters |
| Inconsistent format | One example, or an exact format description |
| Unreliable on a big task | Chain it into smaller prompts |
| Unwanted preamble | Say how the reply should start, or "answer directly" |
| Makes things up | Permit "I don't know"; supply the facts |
| Suggests instead of doing | Use a direct action verb ("change this function") |
| Agent did more than intended | Add bounds and a draft-first step |

## Avoid
- Over-engineering: more words are not better.
- Every technique at once.
- Rules without reasons, and rules that contradict each other.
- Absolutes ("NEVER", "ALWAYS") for habits rather than real risks.
- Repeating standing preferences in every prompt; move them to custom instructions or CLAUDE.md (see reusable-prompts.md).
