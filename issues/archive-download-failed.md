# Plugin zip download fails

| | |
|---|---|
| Step | 2 |
| Seen | 0 (placeholder from the design) |

## Symptoms
- SHA-256 mismatch / download refused
- timeout downloading from github.com

## Causes and fixes
- **Timeout or proxy:** see [prerequisites/network.md](../prerequisites/network.md). The zip is about 19 MB, and Claude Code allows 120 s.
- **SHA-256 mismatch:** the catalog and the zip are out of step (our release mistake), or something on the network changed the file. Run `claude plugin marketplace update pairpipe` and try again. If it still fails, send the report with `"outcome": "stuck"` and include the error. We need to fix the release.

## Verify
`claude plugin install pairpipe@pairpipe` prints `Successfully installed`.
