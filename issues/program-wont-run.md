# The pairpipe program won't run

| | |
|---|---|
| Step | 3 |
| Seen | 0 from users (risks known from our release notes) |

## No folder
No `pairpipe` folder under `~/.claude/plugins/cache/`: the plugin didn't install. Go back to Step 2 and read its output. If `CLAUDE_CONFIG_DIR` is set, look under that folder instead of `~/.claude`.

## Permission denied
[Mac]/[Linux] `Permission denied` or `cannot execute`: the program lost its "executable" flag.
```
chmod +x ~/.claude/plugins/cache/pairpipe/pairpipe/*/bin/pairpipe ~/.claude/plugins/cache/pairpipe/pairpipe/*/bin/*/pairpipe
```
Then re-run `PAIRPIPE version`. Please report this in Step 7: it means our zip needs fixing.

## Blocked
- [Win] SmartScreen ("Windows protected your PC") or antivirus quarantined `pairpipe.exe`. Ask your user to allow it, then re-install (Step 2).
- [Mac] "cannot be opened because the developer cannot be verified": ask your user to open System Settings → Privacy & Security, click **Open Anyway** for pairpipe, then re-run.

## Verify
`PAIRPIPE version` prints `pairpipe <version>`.
