# Maintaining this guide

## Rules
- Docs only: no programs, no scripts that run on download. Commands are shown inline, from official sources only.
- START.md stays under ~150 lines. Detail goes in `issues/` and `prerequisites/`.
- Every TROUBLESHOOTING line quotes the **exact** error text, so an agent can search for it.
- Issue pages use the same header table: Step, Seen (count · first · last), Where, Status.
- Never put keys, tokens, emails or personal data in this repo.

## Pinned versions (typical's condition, 2026-10-28)
Users never read `main`. The paste line and the pairpipe.com setup line point at a **full 40-character commit SHA**: `https://raw.githubusercontent.com/pairpipe/install/<sha>/START.md`. A SHA can't be moved, unlike a tag (typical's review, 2026-10-29). Every link inside the guide is relative, so one pin covers the whole read.
- Issue pages and fixes can merge to `main` any time. They reach users only with the next pin.
- When START.md, TROUBLESHOOTING.md or any linked page changes in a way users need: tag the reviewed `main` commit (`v2`, `v3`, ... for humans; a ruleset blocks updating or deleting `v*` tags), then open a **pin-bump PR** in the pairpipe repo that sets `GUIDE_REF` in `web/src/lib/setupLines.ts` to that commit's SHA, and update the README paste line here. That PR is reviewed like any other.
- Exception: `marketplace.json` is read from `main` (`https://raw.githubusercontent.com/pairpipe/install/main/marketplace.json`). Claude Code re-fetches the registered catalog URL on `marketplace update`, so a pinned catalog would freeze users on one plugin version. `main` is protected (PRs only), and the zip is pinned by SHA-256 inside the file. This is the same trust model as the old `pairpipe/plugin` Git marketplace on its default branch.

## On every plugin release
`marketplace.json` pins the plugin zip by URL and SHA-256. After releasing `vX.Y.Z` in pairpipe/plugin:
1. Build the zip from the tag, with the plugin at the zip root: `git -C <pairpipe-plugin clone> archive --format=zip -9 -o pairpipe-plugin-vX.Y.Z.zip vX.Y.Z:plugins/pairpipe`
2. `gh release upload vX.Y.Z pairpipe-plugin-vX.Y.Z.zip -R pairpipe/plugin`
3. Update `url` and `sha256` in `marketplace.json` (via PR), then test with `claude plugin marketplace update pairpipe && claude plugin update pairpipe@pairpipe`.

## Daily report job
Pull new `install-guide` reports → cluster by error text → update Seen counts / add issue pages / add index lines / fold repeated `smoother` ideas into START.md → one PR here → notify the team about anything new or `stuck`.
If that PR changes START.md or TROUBLESHOOTING.md: once it merges, tag it and open the pin-bump PR (commit SHA) in the pairpipe repo (see Pinned versions). Seen-count-only changes need no new tag.
