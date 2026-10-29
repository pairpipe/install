# Maintaining this guide

## Rules
- Docs only: no programs, no scripts that run on download. Commands are shown inline, from official sources only.
- START.md stays under ~150 lines. Detail goes in `issues/` and `prerequisites/`.
- Every TROUBLESHOOTING line quotes the **exact** error text, so an agent can search for it.
- Issue pages use the same header table: Step, Seen (count · first · last), Where, Status.
- Never put keys, tokens, emails or personal data in this repo.

## On every plugin release
`marketplace.json` pins the plugin zip by URL and SHA-256. After releasing `vX.Y.Z` in pairpipe/plugin:
1. Build the zip from the tag, with the plugin at the zip root: `git -C <pairpipe-plugin clone> archive --format=zip -9 -o pairpipe-plugin-vX.Y.Z.zip vX.Y.Z:plugins/pairpipe`
2. `gh release upload vX.Y.Z pairpipe-plugin-vX.Y.Z.zip -R pairpipe/plugin`
3. Update `url` and `sha256` in `marketplace.json` (via PR), then test with `claude plugin marketplace update pairpipe && claude plugin update pairpipe@pairpipe`.

## Daily report job
Pull new `install-guide` reports → cluster by error text → update Seen counts / add issue pages / add index lines / fold repeated `smoother` ideas into START.md → one PR → notify the team about anything new or `stuck`.
