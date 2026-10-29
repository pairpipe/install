# `claude` not found inside the desktop app

| | |
|---|---|
| Step | 1b / 2 |
| Seen | known from our own testing · first 2026-10-25 |
| Where | Claude desktop app (Code tab), IDE extensions |
| Status | Expected; there's a workaround |

## Symptom
Running `claude --version` or `claude plugin ...` in your shell tool says the command isn't recognized.

## Cause
The desktop app runs Claude Code internally. It doesn't always put a `claude` command on the PATH your shell tool sees.

## Fix
You don't need it. Ask your user to type the plugin commands in the chat, one at a time, and say "done":
```
/plugin marketplace add https://raw.githubusercontent.com/pairpipe/install/main/marketplace.json
/plugin install pairpipe@pairpipe
```
If `/plugin install` opens a panel, tell them to choose **Install** (user scope). Then continue at START.md Step 3.

## Verify
The folder `~/.claude/plugins/cache/pairpipe/pairpipe/` exists and has a version folder with `bin/`.
