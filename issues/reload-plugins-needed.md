# pairpipe installed but tools missing / messages held

| | |
|---|---|
| Step | 3, 5 |
| Seen | known from our own audits · first 2026-10-25 |
| Where | all |
| Status | Expected; the user must reload once |

## Symptom
- `pairpipe` isn't a command yet, or
- the `pairpipe_*` tools aren't loaded, or
- the program says "messages are held … Nothing was read."

## Cause
A newly installed plugin loads only after `/reload-plugins` or a new session. Claude can't type slash commands, and the reload gives Claude no turn.

## Fix
- Before the reload: run the program by its full path (START.md Step 3).
- Ask your user to type `/reload-plugins`, press Enter and say "done". In the desktop app, starting a new session also works.

## Verify
`pairpipe status` works without a full path, and the `pairpipe_status` tool exists.
