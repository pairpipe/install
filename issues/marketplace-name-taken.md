# A marketplace named "pairpipe" already exists

| | |
|---|---|
| Step | 2 |
| Seen | expected for anyone who tried the old Git route · first 2026-10-28 |
| Where | all |

## Symptom
Adding the default marketplace fails or does nothing because `pairpipe` is already registered (often from a failed earlier attempt with `pairpipe/plugin`). Claude Code allows one marketplace per name.

## Fix
```
claude plugin marketplace remove pairpipe
claude plugin marketplace add https://raw.githubusercontent.com/pairpipe/install/main/marketplace.json
claude plugin install pairpipe@pairpipe
```
Desktop app: the user types the same lines with `/plugin` in front instead of `claude plugin`.
Removing the marketplace also uninstalls the old plugin. That's fine, because sign-in is stored outside the plugin.

## Verify
`claude plugin list` shows `pairpipe@pairpipe` enabled.
