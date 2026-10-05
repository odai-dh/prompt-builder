# Models and effort

Last updated: 2026-10-05  <!-- update whenever the table changes; check platform.claude.com/docs/en/models -->

## Tier rules (stable)

| Tier | Use for |
|---|---|
| Fast | Extraction, classification, formatting, simple rewrites, high volume, chat backends |
| Balanced | Most writing, coding and knowledge work. The default |
| Frontier | Long-running agentic work, hard reasoning, high-stakes code |
| Top | The hardest problems where you want the best single attempt and cost/speed matter least |

## Current Claude models (verified 2026-10-05)

| Tier | Model | Context | Price in/out per MTok | Thinking | Default effort |
|---|---|---|---|---|---|
| Fast | Claude Haiku 4.5 | 200K | $1 / $5 | Manual extended thinking | No effort setting |
| Balanced | Claude Sonnet 5.5 | 1M | $2 / $10 | Adaptive | high |
| Frontier | Claude Opus 5.5 | 1M | $4 / $20 | Adaptive, always on | medium |
| Top | Claude Fable 5.1 | 1M | see docs | Adaptive | see docs |

Note: Haiku 5.5 has been announced but not released as of this date. When it ships, update the Fast row.

Note: Sonnet 5.5 scores close to Opus 5.5 on a lot of real-world knowledge work at half the price. Default to Sonnet unless the task is long-running agentic work or genuinely hard.

## Effort levels

Effort sets how much verification, edge-case testing and independent judgement Claude spends. It mostly fixes *missed cases*, not a *wrong approach*; a wrong approach needs a better prompt, not more effort.

| Effort | Use for |
|---|---|
| low | Quick, in-the-loop work: brainstorming, sketches, easy edits, first drafts to iterate on |
| medium | Regular work, e.g. building a feature from a clear spec |
| high | Anything where verification matters: bug fixes in existing code, edge-case-heavy logic, reviews |
| xhigh | Hard problems with many hidden edge cases (security, parsers, performance) |
| max | Fully autonomous work on difficult problems where you want the best one-shot result and can wait |

Signals for higher effort: security, hardware, ML, science, data correctness, production code. Signals that effort won't help much: rulebook-style admin or operations tasks, simple content.

On vague tasks, higher effort means Claude makes more decisions for the user. If the user wants control, recommend a better spec at lower effort instead.

## A loop worth recommending for builds
1. Have Claude interview you to fill gaps in the spec.
2. Build on low effort.
3. Review and iterate on low.
4. Verify and test on high.

## Where effort is set
- Claude Code: `/effort` (can change mid-conversation).
- API: the effort parameter on models that support it (not Haiku 4.5).
- Claude app / Cowork: TODO — verify the current control and its name before publishing.
