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
- Eval 2: on complete prompts the skill makes minimal edits but rarely states "already strong" up front.
- Eval 4: an unrequested approval gate appeared in 1 of 3 runs; watch for it in tester feedback.
- Untested in the Claude app and Cowork, including tappable options and the app's effort control.
- How effort is set in the Claude app / Cowork: still unverified. SKILL.md tells the skill not to name a control until this is confirmed; confirm, then update models-and-effort.md and drop that line.
- Fable 5.1 pricing and default effort: fill from docs.
- Haiku 5.5 is announced; update models-and-effort.md when it ships.
- examples.md is seeded from iteration-1 eval cases (written by hand, not captured from runs); replace with real good runs.

## Keeping models current
Re-check platform.claude.com/docs/en/models on every new model release and bump the date in models-and-effort.md.
