# Package managers

Only needed for the Git route or to install Claude Code by package manager. The default route needs none.

## No winget
[Win] `winget` comes with "App Installer". If `winget --version` fails:
- Ask your user to open the Microsoft Store, search "App Installer", click Get/Update, then open a new terminal.
- Or skip winget: use the direct installers (Git: https://git-scm.com/download/win; Claude Code: `irm https://claude.ai/install.ps1 | iex`).

## Homebrew (macOS)
Not required. If your user wants it: the official one-liner from https://brew.sh. It asks for their Mac password and installs Xcode command-line tools. On Apple Silicon, follow the "Next steps" it prints to add `/opt/homebrew/bin` to PATH.

## Linux
apt (Debian/Ubuntu), dnf (Fedora/RHEL) and apk (Alpine) are built in. Commands need `sudo` (the user's password).
