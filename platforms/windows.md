# Windows notes

- Supported: Windows 10 1809+ / 11, 64-bit (x64 or ARM64). 32-bit Windows isn't supported by Claude Code.
- The default route needs **no Git, no admin, no winget**.
- Your shell tool may be **PowerShell** (no Git for Windows installed) or **Git Bash** (Git installed). START.md gives commands for both. In PowerShell, `~` works in paths, but `$HOME` is safer: `$HOME\.claude\plugins\cache\pairpipe\pairpipe`.
- Find the newest version folder: `Get-ChildItem "$HOME\.claude\plugins\cache\pairpipe\pairpipe" -Directory | Sort-Object { try { [version]($_.Name -replace '[-+].*$','') } catch { [version]'0.0' } }, { $_.Name -notmatch '-' } | Select-Object -Last 1 -ExpandProperty FullName` (sort numerically: a text sort puts 0.3.10 before 0.3.9)
- Anything you install while Claude runs (Git, Claude CLI) isn't seen until Claude fully restarts: tray icon → Quit, then reopen.
- WSL: plugins aren't available in the desktop app's WSL sessions. Inside a WSL terminal, follow the Linux notes and install Claude Code in WSL itself.
