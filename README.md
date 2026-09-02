# homebrew-warmline

A [Homebrew](https://brew.sh) tap for
[claude-warmline](https://github.com/Miguel-Barroso/claude-warmline) — a
statusline, auditor and keep-warm policy that make Claude Code's prompt cache
state visible.

```sh
brew install Miguel-Barroso/warmline/warmline
```

One command. It puts `warmline` and `warmline-audit` on your `PATH` **and** wires
the statusline into Claude Code — `warmline status` shows the result.
`brew upgrade warmline` re-wires it at the new version, and `brew uninstall
warmline` unwires it before removing the commands.

Nothing happens behind your back: the wiring is `warmline setup`, which you can
also run yourself, and which prints every file it touches, backs up
`settings.json`, and refuses to replace a statusline that isn't warmline's unless
you pass `--force`.

**macOS only.** This is a cask rather than a formula because a formula's
`post_install` hook runs under a sandbox that denies reading `$HOME`, so it can't
wire anything — and casks don't exist on Linux. On Linux, use the project's
installer, which is one command and does the same two halves:

```sh
curl -fsSL https://raw.githubusercontent.com/Miguel-Barroso/claude-warmline/main/install.sh | bash
```

Everything else — what the fields mean, how the audit works, whether keep-warm
is worth it — lives in the
[main repository](https://github.com/Miguel-Barroso/claude-warmline). Issues and
pull requests belong there too, including changes to the cask:
[`packaging/homebrew/warmline.rb`](https://github.com/Miguel-Barroso/claude-warmline/blob/main/packaging/homebrew/warmline.rb)
is its source of truth, and this tap holds the published copy.

MIT, same as the project.
