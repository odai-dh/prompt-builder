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
claude plugin marketplace add odai-dh/prompt-builder#main
claude plugin install prompt-builder@odai-prompt-builder
```

Inside a Claude Code session the same two steps are `/plugin marketplace add odai-dh/prompt-builder#main` and `/plugin install prompt-builder@odai-prompt-builder`.

Then start a new session and ask Claude to improve a prompt, or run `/prompt-builder:prompt-builder`. To check it's installed, run `claude plugin list`.

Update with `claude plugin update prompt-builder@odai-prompt-builder`. Remove with `claude plugin uninstall prompt-builder@odai-prompt-builder`.

### For developers

To load the plugin from a local checkout instead (this session only, no install):

```
git clone --branch main https://github.com/odai-dh/prompt-builder.git
claude --plugin-dir ./prompt-builder
```

See [TESTERS.md](TESTERS.md) if you're helping test.

Status: v0.2.0. Tested in Claude Code; in testing for the Claude app and Cowork.
