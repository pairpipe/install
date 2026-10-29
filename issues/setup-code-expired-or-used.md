# Setup code rejected

| | |
|---|---|
| Step | 4 |
| Seen | known from our own testing · first 2026-10-25 |
| Where | all |

## Exact errors
- `invalid_code` / "not valid, used or expired"
- "That setup line was already used. Each line signs in one computer once."

## Cause
Each setup code signs in **one** computer **once**, and it expires after a while. Copying an old line, pasting it twice, or using a code made for another computer causes this.

## Fix
1. If `PAIRPIPE status` already shows the right account and pair, this computer is connected and there's nothing to do. Go to Step 5.
2. Otherwise ask your user: "Open https://pairpipe.com, sign in, copy a **new** setup line and paste it here." Then run `PAIRPIPE connect <new code>`.

## Verify
`connect` prints the account and pair.
