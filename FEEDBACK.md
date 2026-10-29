# Install reports

Every install, whether it worked, failed or got stuck, ends with START.md Step 7: Claude sends one short report to `POST https://api.pairpipe.com/v1/install-feedback`.

## What's in a report
OS, CPU, shell, desktop app or CLI, Claude Code and plugin versions, which prerequisites were already there or had to be installed, the step that failed, the exact error, the workaround, the minutes taken, and **`smoother`**: what would have made the install smoother and easier, in as much detail as is comfortable. Every report must have it, even when everything worked.

## What's never in a report
Emails, names, file paths, setup codes, keys or passwords. The server also strips paths and emails before storing anything, and doesn't store IP addresses.

## How reports improve this guide
A daily job groups new reports by error, then opens a pull request here:
- a known problem → its page's "Seen" count and dates go up;
- a new problem → a new `issues/<id>.md` page plus one line in TROUBLESHOOTING.md;
- `smoother` ideas that repeat → edits to START.md or the product.
`stuck` reports go to a person the same day. People review every pull request before it merges.

No network or no endpoint? START.md Step 7 has a fallback (the program's own report, or a GitHub issue your user can post).
