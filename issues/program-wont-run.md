# The pairpipe program won't run

| | |
|---|---|
| Step | 3 |
| Seen | 1 install report (CRLF) · first 2026-11-27 · last 2026-11-27 |

## No folder
No `pairpipe` folder under `~/.claude/plugins/cache/`: the plugin didn't install. Go back to Step 2 and read its output. If `CLAUDE_CONFIG_DIR` is set, look under that folder instead of `~/.claude`.

## Permission denied
[Mac]/[Linux] `Permission denied` or `cannot execute`: the program lost its "executable" flag.
```
chmod +x ~/.claude/plugins/cache/pairpipe/pairpipe/*/bin/pairpipe ~/.claude/plugins/cache/pairpipe/pairpipe/*/bin/*/pairpipe
```
Then re-run `PAIRPIPE version`. Please report this in Step 7: it means our zip needs fixing.

## Blocked
**First confirm the program came from the checked install.** Only allow a blocked program if both are true:
- it's inside the plugin cache folder from Step 3 (`.../plugins/cache/pairpipe/pairpipe/<version>/bin/`), and
- Step 2 printed `Successfully installed plugin: pairpipe@pairpipe`, which means Claude Code verified the zip's SHA-256 pin.

If the program came from anywhere else (a download, an email, a chat), don't allow it: delete it and go back to Step 2.

Then:
- [Win] SmartScreen ("Windows protected your PC") or antivirus quarantined `pairpipe.exe`: ask your user to allow it, then re-install (Step 2).
- [Mac] "cannot be opened because the developer cannot be verified": ask your user to open System Settings → Privacy & Security, click **Open Anyway** for pairpipe, then re-run.

## CRLF
`bad interpreter: /bin/sh^M` on macOS or Linux. The first plugin v0.4.4 zip (before 2026-11-27) shipped with Windows line endings. It has been replaced.
- Fix: `claude plugin marketplace update pairpipe`, then `claude plugin update pairpipe@pairpipe`, then reload.
- Quick workaround: strip the CRs from the launcher and JSON files in the version folder: `sed -i '' $'s/\r$//' bin/pairpipe .mcp.json hooks/hooks.json` (Linux: `sed -i`).

## Verify
`PAIRPIPE version` prints `pairpipe <version>`.
