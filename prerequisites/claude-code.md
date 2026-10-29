# Claude Code

pairpipe needs Claude Code **2.1.224 or newer** (that's when zip plugins arrived). Either the Claude desktop app's Code tab or the `claude` CLI works. Claude Code itself needs no Git and no Node (native installer).
Requirements (official): Windows 10 1809+ (64-bit), macOS 13+, Ubuntu 20.04+ / Debian 10+ / Alpine 3.19+, 4 GB RAM. Source: code.claude.com/docs/en/setup.md

## Install
Show the command first. None of these needs admin rights.
- [Win] PowerShell: `irm https://claude.ai/install.ps1 | iex`  (or `winget install Anthropic.ClaudeCode`)
- [Mac]/[Linux]/WSL: `curl -fsSL https://claude.ai/install.sh | bash`  (or [Mac] `brew install --cask claude-code`)
Then check: `claude --version` and `claude doctor`.

## claude not found
After installing, the program is at `%USERPROFILE%\.local\bin\claude.exe` [Win] or `~/.local/bin/claude` [Mac/Linux].
- Open a **new** terminal first (PATH changes need one).
- [Mac]/[Linux] still missing: `echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.zshrc && source ~/.zshrc` (use `~/.bashrc` on Linux bash, `~/.bash_profile` on macOS bash).
- [Win] still missing: run it by full path `& "$env:USERPROFILE\.local\bin\claude.exe" --version`, and add `%USERPROFILE%\.local\bin` to the user PATH (Settings → System → About → Advanced system settings → Environment Variables → user `Path` → New). Then open a new terminal.
- [Win] an old Claude desktop app can shadow `claude`. Update the desktop app.
- **In the desktop app** `claude` may not exist at all. That's fine: use the slash-command route in START.md Step 2.

## Update
`claude update`, then `claude --version`. In the desktop app: update the app (it updates its Claude Code).
Older than 2.1.224 and can't update → use the [Git route](git.md#use-the-git-route) (needs Git).

Troubleshooting (official): code.claude.com/docs/en/troubleshoot-install.md
