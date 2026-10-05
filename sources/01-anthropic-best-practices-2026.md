Source: Best practices for prompt engineering (Claude blog) — https://claude.com/blog/best-practices-for-prompt-engineering
Topic tags: anatomy | techniques | models

Notes (own words):
- Core habits: be explicit, give the reason behind rules, be specific (constraints, audience, structure), use examples when format is easier shown than described, allow "I don't know".
- Examples are copied closely by current models, so they must model only wanted behavior. Start with one, add more only if needed.
- Advanced: prefill (API), chain of thought (extended thinking preferred when available), format control (say what TO do; prompt style leaks into output style), prompt chaining.
- Downgraded: XML tags and heavy role prompting are less needed with modern models; plain headings and explicit perspective often work as well.
- Has a symptom -> fix troubleshooting list and a "which technique for which need" table.
- Prompting is converging with context engineering on Claude 5-gen models: less scaffolding, more curation.
- Standing instructions belong in CLAUDE.md / skills, not repeated per prompt.
Follow-up to collect: the linked post on context engineering for Claude 5-generation models.
