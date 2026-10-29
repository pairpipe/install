# Troubleshooting index

Links are relative to this file's URL: keep the same tag in the URL as START.md. Find the line that matches your **exact error text** (search for a distinctive part of it), then open only that page. Each line: error → page. Seen counts are in each page.

If nothing matches: try the closest page once. If it still fails, send the Step 7 report with `"outcome": "stuck"` (see START.md).

## Step 1: prerequisites
| Error / symptom | Page |
|---|---|
| `claude` : The term 'claude' is not recognized / `claude: command not found` (in a terminal) | [prerequisites/claude-code.md#claude-not-found](prerequisites/claude-code.md#claude-not-found) |
| `claude` not found in the desktop app | [issues/claude-not-on-path-desktop-app.md](issues/claude-not-on-path-desktop-app.md) |
| healthz check times out, `Could not resolve host`, SSL/certificate errors | [prerequisites/network.md](prerequisites/network.md) |
| `winget` is not recognized | [prerequisites/package-managers.md#no-winget](prerequisites/package-managers.md#no-winget) |

## Step 2: plugin install
| Error / symptom | Page |
|---|---|
| `Failed to clone marketplace repository: Command 'git' not found or is in an unsafe location` | [issues/git-missing-windows.md](issues/git-missing-windows.md) |
| `git: command not found` / `'git' is not recognized` during a plugin command | [issues/git-missing-windows.md](issues/git-missing-windows.md) |
| A marketplace named `pairpipe` already exists / old pairpipe install | [issues/marketplace-name-taken.md](issues/marketplace-name-taken.md) |
| `Unknown source type` / `archive` not supported / `Invalid input` on source | [prerequisites/claude-code.md#update](prerequisites/claude-code.md#update) (Claude Code older than 2.1.224) |
| `SHA-256 mismatch` / download refused | [issues/archive-download-failed.md](issues/archive-download-failed.md) |
| Download timed out / `ETIMEDOUT` / proxy errors on github.com | [prerequisites/network.md](prerequisites/network.md) |
| `SSH authentication failed` / `known_hosts` (Git route only) | [prerequisites/git.md#ssh-errors](prerequisites/git.md#ssh-errors) |

## Step 3: program
| Error / symptom | Page |
|---|---|
| No `pairpipe` folder under `plugins/cache` | [issues/program-wont-run.md#no-folder](issues/program-wont-run.md#no-folder) |
| `pairpipe` not found before reload | [issues/reload-plugins-needed.md](issues/reload-plugins-needed.md) |
| `Permission denied` / `cannot execute binary file` (Mac/Linux) | [issues/program-wont-run.md#permission-denied](issues/program-wont-run.md#permission-denied) |
| Windows SmartScreen / antivirus blocked `pairpipe.exe`; macOS "cannot be opened" | [issues/program-wont-run.md#blocked](issues/program-wont-run.md#blocked) |

## Step 4: sign in
| Error / symptom | Page |
|---|---|
| `invalid_code`, "not valid, used or expired", "That setup line was already used" | [issues/setup-code-expired-or-used.md](issues/setup-code-expired-or-used.md) |
| `other_account`: "signed in to a different pairpipe account" | [issues/other-account-signed-in.md](issues/other-account-signed-in.md) |

## Step 5-6: turn on and verify
| Error / symptom | Page |
|---|---|
| "messages are held", tools `pairpipe_*` missing, nothing arrives | [issues/reload-plugins-needed.md](issues/reload-plugins-needed.md) |
