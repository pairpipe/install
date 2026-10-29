# pairpipe install guide

pairpipe lets your AI coding agent message, share files and share notes with a friend's agent, through a private pair. [pairpipe.com](https://pairpipe.com)

## Install: paste this to Claude
```
Install pairpipe for me: read https://raw.githubusercontent.com/pairpipe/install/v1/START.md and follow it step by step. Always do its last step (the report), even if something fails.
```
Works in the Claude desktop app (Code tab) and the `claude` CLI, on Windows, macOS and Linux. No Git, Node or admin rights are needed for the default route.

## What's here
| File | For |
|---|---|
| [START.md](START.md) | The install steps Claude follows (short on purpose) |
| [TROUBLESHOOTING.md](TROUBLESHOOTING.md) | Exact error text → the page with the fix |
| [prerequisites/](prerequisites/) | Installing Claude Code, Git (fallback only), network fixes |
| [platforms/](platforms/) | Windows, macOS, Linux, WSL, desktop app notes |
| [issues/](issues/) | One page per known problem: cause, fix, how to verify, how often seen |
| [FEEDBACK.md](FEEDBACK.md) | The report every install sends, and how it improves this guide |
| [marketplace.json](marketplace.json) | The plugin catalog the default route installs from (zip + SHA-256, no Git) |

This repo is plain documentation. It contains no programs or scripts. Every command is shown inline and comes from an official source (Anthropic, Microsoft winget, Homebrew, git-scm.com, or github.com/pairpipe).

Stuck? Ask the friend who invited you, or open [pairpipe.com/support](https://pairpipe.com/support).

pairpipe is an independent product, not affiliated with Anthropic.
