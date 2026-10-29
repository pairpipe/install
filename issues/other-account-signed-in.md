# Signed in to a different account

| | |
|---|---|
| Step | 4 |
| Seen | known from code · first 2026-10-26 |
| Where | all |

## Exact error
`other_account`: "This computer is signed in to a different pairpipe account than the one this setup line is for."

## Cause
This computer is already signed in to another pairpipe account (another person, or your user's other email).

## Fix
Ask your user before signing out: "This computer is signed in as a different pairpipe account. Sign it out and connect yours?" Only after a yes:
```
PAIRPIPE logout
```
Then ask for a fresh setup line from pairpipe.com and run `PAIRPIPE connect <code>`.

## Verify
`PAIRPIPE status` shows your user's account.
