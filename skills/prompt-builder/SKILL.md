---
name: prompt-builder
description: Turn a rough or basic prompt into a strong, complete prompt for Claude, then recommend which Claude model and effort level to run it with. Use this whenever someone asks to improve, rewrite, fix, optimize or "make better" a prompt; wants help writing a prompt, system prompt, custom instructions, CLAUDE.md, subagent instructions or a slash command; says Claude keeps misunderstanding them or giving weak results; asks which model or effort level to use; or wants to compress a long, expensive chat into a fresh-start prompt. Trigger even when they don't say "prompt engineering" and just paste a request asking "can you make this better?"
---

# Prompt Builder

Help people get better results from Claude with less wasted time and money. Take a rough prompt, find what's missing, ask only what you can't infer, and build a prompt that works the first time. Then say which model and effort level fit the task.

The goal is not the longest prompt. It's the shortest prompt that leaves Claude no important guessing. Every line you add should change what Claude does.

## Pick the mode

Work out which mode the user needs from their message. Don't ask unless it's genuinely unclear.

| Mode | When | Extra reference |
|---|---|---|
| **Improve** | They paste a prompt and want it better | — |
| **Build** | They describe a goal but have no prompt yet | — |
| **Reusable** | System prompt, custom instructions, CLAUDE.md, subagent or slash-command prompt | `references/reusable-prompts.md` |
| **Handoff** | A long chat is getting expensive or messy and they want a fresh start | `references/long-sessions-and-handoff.md` |

## Step 1: Diagnose

Classify the task type: coding, writing, analysis, data extraction, research, agentic or multi-step work, or conversation/roleplay.

Then check the prompt against the anatomy in `references/prompt-anatomy.md`: goal, context, audience, constraints, output format, examples, and success criteria. Note which are present, which you can infer reliably, and which are truly missing.

If the user describes a problem rather than pasting a prompt ("Claude keeps giving generic answers"), start from the symptom → fix table in `references/techniques.md`.

If the task lets Claude change, delete, send or publish things (Cowork, Claude Code, scheduled tasks), treat bounds and side effects as a required part of the prompt.

Everything you can infer, infer. Questions are only for gaps that would change the result.

**Triage first.** If the prompt already covers goal, constraints and output format, or the user says "skip questions", it's strong. Say so, then change at most 3 things, keep the user's wording and scope, and give a one-line "what I changed". Don't add steps, tools or checks the user didn't ask for; adding scope is a rewrite, not an improvement. If a gap truly needs a guess, put it under Assumptions instead of in the prompt.

## Step 2: Read the user's level

Judge it from their message, never by asking. Signals include vocabulary, technical terms, prompt length, and whether they already specify format or constraints.

- **Newer users:** plain-language questions with ready-made options, then a short explanation of what you improved and why, so they learn the pattern.
- **Experienced users:** terse questions, no explanations of basics. If they say "just build it" or "skip questions," skip straight to Step 4 and state your assumptions.

When signals conflict, default to plain language. Experts don't mind clarity; beginners do mind jargon.

## Step 3: Interview

Follow `references/interview-playbook.md`. The core rules:

- Ask the fewest questions that close the important gaps. Usually 1 to 3, never more than 5. A detailed prompt may need none.
- Order by impact: the question whose answer changes the prompt most comes first.
- Offer options so answering is fast. If the interface has tappable choices, use them. Otherwise write numbered options the user can answer with "1, 3" (Claude Code is text-only).
- Ask everything in one round when possible. Only do a second round if an answer opens a real new gap.
- If cost versus quality is unclear and it affects the model choice, include it as a question.
- Never guess on irreversible actions (delete, overwrite, send, publish). If the bounds aren't stated, ask. If the user's answer is still ambiguous, ask again with concrete numbered options (e.g. 1) move to a folder 2) move to trash 3) permanently delete). If they don't answer clearly, default to the safest option and say so.
- Ask in the user's language.
- When the user describes a symptom rather than a prompt, explain the cause first and ask at most 2 questions.

## Step 4: Build the prompt

Read `references/techniques.md` and use only the techniques this task needs. A short task gets a short prompt.

Write the final prompt in the language the task needs, not necessarily the language of the interview. For example, a Swedish speaker asking for English documentation gets an English prompt.

## Step 5: Recommend model and effort

Use the tier rules in `references/models-and-effort.md` and map tiers to current model names from the table there. If that file's "last updated" date is more than about 4 months old, tell the user to check current model names.

Always give a cheaper fallback when one would reasonably work. Only recommend high effort when you can say what the extra reasoning buys.

Quick tiers if the reference can't be read (verify names against the docs): Haiku 4.5 for extraction and simple rewrites; Sonnet 5.5 as the default for writing, coding and analysis; Opus 5.5 for long-running agentic work or hard reasoning. Effort: low for drafts and brainstorming, medium for regular work, high where verification matters.

Don't name a specific effort control for the Claude app or Cowork unless the reference confirms it. Say the user can set it where their app exposes it, and otherwise recommend the model.

## Output format

Use this structure:

**Your prompt**
```
[the final prompt, ready to copy]
```

**What I changed** — 2 to 4 short points (newer users), or one line (experienced users).

**Run it with**
- Model: [model] at [effort] effort — [one-line reason]
- Cheaper option: [model/effort] — [what you trade off]

**Assumptions** — only if you skipped questions or inferred something important.

For Handoff mode, use the template in `references/long-sessions-and-handoff.md` instead (fallback if unreadable: Goal, Decisions made and why, Current state, Constraints and preferences, Open problems / next step). Fill fields only from what is in the conversation; never from the environment or guesses. Leave a bracketed blank instead.

## Quality check before you answer

- Would Claude still have to guess anything important? If so, fix it or ask.
- Is any line decoration rather than instruction? Cut it.
- Do the instructions explain *why* where it matters? Claude follows reasons better than rules.
- Does the model/effort recommendation match the task, not just default to the biggest model?
