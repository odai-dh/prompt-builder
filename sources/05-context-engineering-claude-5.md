Source: The new rules of context engineering for Claude 5 generation models (claude.dev, Thariq Shihipar, 2026-07-24) — https://claude.dev/blog/the-new-rules-of-context-engineering-for-claude-5-generation-models/
Topic tags: techniques | reusable | anatomy

Notes (own words):
- Anthropic cut most of Claude Code's system prompt for Claude 5 models without losing eval performance. Older guidance over-constrained the model.
- Six reversals: rules -> judgement; examples -> well-designed interfaces; everything upfront -> progressive disclosure; repetition -> say it once in the right place; manual memory in CLAUDE.md -> auto-memory; thin specs -> rich references (code, tests, HTML mockups, rubrics).
- Conflicting instructions across system prompt, skills and user request make Claude spend effort resolving them.
- CLAUDE.md: short purpose line, then spend tokens on codebase gotchas; skip what Claude can see in the repo; link out to skills for detailed procedures.
- Skills: lightweight guides with your own opinions/know-how; split long ones into files.
- Code-form references (HTML mockup, test suite) beat prose descriptions or screenshots.
- `/doctor` in Claude Code helps trim skills and CLAUDE.md.
