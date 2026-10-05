# Development

## Adding knowledge
1. Put raw notes in `sources/` (own words + link + topic tags).
2. Distill into `skills/prompt-builder/references/`. Only keep guidance that changes what the agent does.
3. Add or update an eval if the new knowledge should change behavior.

## Testing (evals)
- Run each prompt in `evals/evals.json` with the skill and without it, and compare side by side.
- Write specific feedback ("skipped the bounds question"), not vague ("not quite right").
- Change one thing per round, then re-run.
- Ship when the cases that matter clearly beat the no-skill baseline and known gaps are written down below.

## Known gaps
- How effort is set in the Claude app / Cowork: verify before publishing.
- Fable 5.1 pricing and default effort: fill from docs.
- Haiku 5.5 is announced; update models-and-effort.md when it ships.
- examples.md is empty; fill from good eval runs.

## Keeping models current
Re-check platform.claude.com/docs/en/models on every new model release and bump the date in models-and-effort.md.
