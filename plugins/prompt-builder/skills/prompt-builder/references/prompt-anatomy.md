# Prompt anatomy

Use this checklist in Step 1. For each part, decide: present, safely inferable, or missing. Only missing parts that would change the result become questions.

## The parts

**Goal.** What should exist when Claude is done? Look for a clear action verb (write, fix, analyze, extract). "Help with my essay" is missing a goal; "tighten the intro to under 100 words" has one.

**Context and reason.** Why this is needed and what it's for. Claude makes better judgment calls when it knows the purpose behind a rule, not just the rule. A bare "never use bullets" is weaker than saying the reader finds prose easier to follow.

**Audience.** Who reads or uses the output. Changes tone, depth and vocabulary more than almost anything else.

**Constraints.** Length, tone, format, deadline, budget, tech stack, must/must-not. Missing constraints are the most common cause of generic output.

**Output format.** What the result should look like (prose, table, JSON, diff, file). State what you want, not only what you don't want.

**Examples.** Only when the format or style is easier to show than describe. Claude copies examples closely, including their flaws, so one clean example beats three sloppy ones.

**Uncertainty handling.** For facts, data or analysis: tell Claude what to do when it doesn't know (say so, use null, flag it) instead of guessing.

**Bounds and side effects** (agentic tasks only). What Claude may change, delete or send, and what it must not touch. See techniques.md → Agentic safety.

## Why these matter (keep in mind when explaining changes)
- Claude continues patterns; it doesn't read minds. Whatever isn't stated gets filled with the most typical answer.
- Its knowledge stops at a cutoff. Anything recent or private must be in the prompt.
- Context helps until it overloads. Include what changes the result, cut the rest.

## Which parts matter most per task type

| Task | Usually critical | Usually inferable |
|---|---|---|
| Writing | Audience, goal, tone/length | Format |
| Coding | Goal, constraints (stack, scope), output format (diff/file) | Audience |
| Analysis | Goal, uncertainty handling, output format | Tone |
| Extraction | Output format, uncertainty handling | Audience, tone |
| Agentic / multi-step | Goal, bounds and side effects, done-criteria | Tone |
| Research | Goal, scope, source expectations | Format |
