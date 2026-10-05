# Prompt Builder

Improve your prompts and write better ones for Claude.

Write a rough prompt and Prompt Builder turns it into a strong one. It works out what's missing, asks only the questions it can't answer itself, builds the final prompt, and tells you which Claude model and effort level to run it with, so you don't waste tokens, time or money.

**Modes**
- **Improve:** paste a prompt, get a better one
- **Build:** describe what you want, get a prompt from scratch
- **Reusable:** improve CLAUDE.md files, system prompts, custom instructions, subagents and slash commands
- **Handoff:** turn a long, expensive chat into a clean prompt for a fresh session

Built for the Claude app, Cowork and Claude Code.

## Install (Claude Code)

```
git clone https://github.com/odai-dh/prompt-builder.git
claude --plugin-dir ./prompt-builder
```

`--plugin-dir` loads the plugin for that session. Then ask Claude to improve a prompt, or run `/prompt-builder:prompt-builder`. To check it loaded, run `claude plugin validate ./prompt-builder`. See [TESTERS.md](TESTERS.md) if you're helping test.

Status: v0.2.0. Tested in Claude Code; in testing for the Claude app and Cowork.
