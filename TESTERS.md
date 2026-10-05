# Testing Prompt Builder

Thanks for helping test. This takes about 15 minutes.

## Install (Claude Code)

```
claude plugin marketplace add odai-dh/prompt-builder#main
claude plugin install prompt-builder@odai-prompt-builder
```

Inside a Claude Code session, use `/plugin marketplace add odai-dh/prompt-builder#main` and `/plugin install prompt-builder@odai-prompt-builder` instead. Then start a new session. To check it installed, run `claude plugin list`; you should see `prompt-builder@odai-prompt-builder` at version 0.2.0.

To pick up fixes during the test: `claude plugin update prompt-builder@odai-prompt-builder`.

Developers can instead load a local checkout for one session: `git clone --branch main https://github.com/odai-dh/prompt-builder.git`, then `claude --plugin-dir ./prompt-builder`.

## What to do

Try it on **2 or 3 real prompts you would actually use**, not made-up ones. Paste a rough prompt and say something like "make this better", or describe a task and ask for a prompt. It also handles CLAUDE.md files, system prompts, and long chats you want to continue in a fresh session.

Answer its questions as you normally would, then use the prompt it gives you and see how it performs.

## Feedback

Please reply with answers to these, per prompt if they differ:

1. Did it ask the right questions, too many, or too few?
2. Was the final prompt better than what you would have written yourself?
3. Did the model and effort suggestion make sense?
4. Anything confusing or annoying?
5. Would you keep using it?

Paste any output that surprised you, good or bad.
