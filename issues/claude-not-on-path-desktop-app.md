# `claude` not found inside the desktop app

| | |
|---|---|
| Step | 1b / 2 |
| Seen | 7 install reports · first 2026-10-25 · last 2026-11-27 |
| Where | Claude desktop app (Code tab), IDE extensions |
| Status | Expected; there's a workaround |

## Symptom
Running `claude --version` or `claude plugin ...` in your shell tool says the command isn't recognized. Or the user typed `/plugin marketplace add <url>` in the chat: the Plugins screen opened, but nothing was added and no error was shown.

## Cause
The desktop app runs its own copy of Claude Code, which isn't on the PATH your shell tool sees. In the desktop app, `/plugin` with arguments only opens the Plugins screen and drops the URL.

## Fix
Use the app's own copy. Agents found it in 4 of 7 reports with no user action:
- Inside a desktop session, the environment variable `CLAUDE_CODE_EXECPATH` is its full path (not documented by Anthropic, so check it exists).
- Otherwise search for it:
  - [Mac] `find ~/Library/Application\ Support/Claude/claude-code -type f -perm -u+x -name claude | sort -V | tail -1`
  - [Win] under `%LOCALAPPDATA%\Claude-Data\<id>\claude-code\<version>\<hash>\claude.exe` or `%APPDATA%\Claude\claude-code\<version>\claude.exe`; take the newest.

Run the default route with that path, for example `"$C" plugin marketplace add https://raw.githubusercontent.com/pairpipe/install/main/marketplace.json`, then `"$C" plugin install pairpipe@pairpipe`. Then continue at START.md Step 3.

**Last resort:** the user adds the marketplace by URL in the **Plugins** screen, then clicks **Install** on pairpipe.

## Verify
The folder `~/.claude/plugins/cache/pairpipe/pairpipe/` exists and has a version folder with `bin/`.
