# Linux notes

- Supported: x64 and ARM64 (Ubuntu 20.04+, Debian 10+, Fedora, Alpine 3.19+ for Claude Code).
- The default route needs no Git.
- Alpine (musl): Claude Code needs `apk add bash curl libgcc libstdc++ ripgrep` and `USE_BUILTIN_RIPGREP=0` (official docs).
- `Permission denied` running the program: [issues/program-wont-run.md#permission-denied](../issues/program-wont-run.md#permission-denied).
- WSL counts as Linux: install Claude Code inside WSL.
