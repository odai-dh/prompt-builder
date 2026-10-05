# Long sessions and handoff

> STATUS: partially filled.

## Why sessions degrade
The context window is fixed. Extra context helps until it starts crowding out what matters, and every message re-sends the whole history, so cost grows with length.

## Signs to restart
- Claude repeats earlier mistakes or forgets decisions.
- Responses slow down or the user mentions cost.
- The conversation has drifted across several unrelated tasks.

## Handoff template
Goal:
Decisions made (and why):
Current state:
Constraints and preferences:
Open problems / next step:

## Keep sessions cheap
- One task per session where possible.
- Put standing preferences in custom instructions / CLAUDE.md, not in chat.
