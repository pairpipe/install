# Claude desktop app (Code tab) notes

- The plugin commands must be typed by your user in the chat: `/plugin marketplace add <url>`, `/plugin install pairpipe@pairpipe`, `/reload-plugins`. You can't type slash commands.
- The app's plugin browser (**+** → Add plugins) also works once the marketplace is added.
- `claude` may not be on your shell PATH. That's expected; see [issues/claude-not-on-path-desktop-app.md](../issues/claude-not-on-path-desktop-app.md).
- New programs installed mid-session need a full app quit and reopen to be seen.
- Starting a new session works as well as `/reload-plugins` to load pairpipe.
