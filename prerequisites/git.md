# Git (fallback route only)

The default route (START.md Step 2) needs **no Git**. You need Git only if TROUBLESHOOTING sent you to the Git route, for example because your Claude Code can't use the default route.

CHECK: `git --version` prints `git version 2.x`. If it does, skip to [Use the Git route](#use-the-git-route).

## Install Git
Show each command to your user before running it.

### Windows
1. If `winget --version` works:
   ```
   winget install --id Git.Git -e --source winget --accept-package-agreements --accept-source-agreements
   ```
   Tell your user first: **"A Windows prompt will ask 'Do you want to allow this app to make changes?'. Click Yes, then tell me 'done'."** (The prompt can hide behind other windows. Check the taskbar.)
2. No winget → [package-managers.md#no-winget](package-managers.md#no-winget), or ask your user to download the installer from https://git-scm.com/download/win, run it with all defaults, and say "done".
3. No admin rights (the prompt asks for an admin password): ask your user to install "Portable Git" from https://git-scm.com/download/win into a folder in their user profile, then add its `cmd` folder to their user PATH. *(Not yet tested end to end; please report how it went.)*

### macOS
- `xcode-select --install`. A dialog appears. Tell your user: **"Click Install, accept, wait until it finishes (5-15 min), then tell me 'done'."**
- Or, if Homebrew is installed (`brew --version`): `brew install git`

### Linux
- Debian/Ubuntu: `sudo apt-get update && sudo apt-get install -y git`
- Fedora/RHEL: `sudo dnf install -y git`
- Alpine: `sudo apk add git`
`sudo` asks your user for their password in the terminal. Ask them to run the command themselves if you can't.

## Make Git visible (the step people miss)
A program installed while Claude is running is **not** seen until Claude restarts, because Claude keeps the PATH it started with.
- **[Win] desktop app:** ask your user to fully quit Claude (right-click the Claude icon in the taskbar tray → Quit; closing the window is not enough), open it again, start a new session, and paste the install line again. *(The friend's install on 2026-10-28 failed here; see [issues/git-missing-windows.md](../issues/git-missing-windows.md).)*
- **CLI:** close the terminal, open a new one, start `claude` again.
CHECK again: `git --version`.
- [Win] Still not found but `C:\Program Files\Git\cmd\git.exe` exists: the PATH didn't update. Sign out of Windows and back in.

## Use the Git route
```
claude plugin marketplace add pairpipe/plugin
claude plugin install pairpipe@pairpipe
```
In the desktop app: `/plugin marketplace add pairpipe/plugin` then `/plugin install pairpipe@pairpipe`, typed by your user.
If you already added the default marketplace, remove it first: `claude plugin marketplace remove pairpipe`.

## SSH errors
`SSH authentication failed` or `known_hosts`: Claude Code tries SSH to GitHub first. Force HTTPS (the repo is public, so no login is needed):
- PowerShell: `$env:CLAUDE_CODE_PLUGIN_PREFER_HTTPS = "1"` then re-run (CLI only).
- bash: `export CLAUDE_CODE_PLUGIN_PREFER_HTTPS=1` then re-run.
Source: code.claude.com/docs/en/plugins/host-marketplace.md
