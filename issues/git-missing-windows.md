# Plugin install fails: Git missing

| | |
|---|---|
| Step | 2 (old Git route) |
| Seen | 2 installs · first 2026-10-28 · last 2026-10-28 |
| Where | Windows 11, Claude desktop app, no Git installed |
| Status | Fixed by default: the new route needs no Git |

## Symptom
Adding the pairpipe marketplace fails right away. In the desktop app the plugin step does nothing useful, or shows an error.

## Exact error
```
Failed to clone marketplace repository: Command 'git' not found or is in an unsafe location
```
(Official error text from code.claude.com/docs/en/plugins/troubleshooting.md.)

## Cause
`/plugin marketplace add pairpipe/plugin` (GitHub `owner/repo` form) makes Claude Code run `git clone`. Claude Code itself runs fine without Git, so everything looks OK until this step. A fresh Windows PC has no Git.

## Fix
1. Use the default route from START.md Step 2 instead (a `marketplace.json` URL plus a zip; no Git needed):
   ```
   claude plugin marketplace add https://raw.githubusercontent.com/pairpipe/install/main/marketplace.json
   claude plugin install pairpipe@pairpipe
   ```
   or, typed by the user in the desktop app: `/plugin marketplace add https://raw.githubusercontent.com/pairpipe/install/main/marketplace.json` then `/plugin install pairpipe@pairpipe`.
2. If a half-added `pairpipe` marketplace is in the way, remove it first: `claude plugin marketplace remove pairpipe` (or `/plugin marketplace remove pairpipe`).
3. Only if you must use the Git route: [prerequisites/git.md](../prerequisites/git.md). Remember the full app restart after installing Git.

## Verify
`claude plugin list` shows `pairpipe@pairpipe` enabled, or Step 3's `PAIRPIPE version` prints a version.

## Notes
- Verified 2026-10-28: the default route installed and ran with Git removed from PATH (Windows 11, Claude Code 2.1.310).
- In this case no install report was sent, because the old guide had no report step that worked before sign-in. That's why START.md Step 7 now runs even after a failure.
