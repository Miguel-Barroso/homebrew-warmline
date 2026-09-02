# homebrew-warmline

A [Homebrew](https://brew.sh) tap for
[claude-warmline](https://github.com/Miguel-Barroso/claude-warmline) — a
statusline, auditor and keep-warm policy that make Claude Code's prompt cache
state visible.

```sh
brew install Miguel-Barroso/warmline/warmline
warmline setup
```

`brew install` puts `warmline` and `warmline-audit` on your `PATH` and stops
there. `warmline setup` is the half that touches Claude Code — it installs the
statusline into your config dir and wires `settings.json`, with a backup, and it
refuses to replace someone else's statusline unless you pass `--force`. Re-run it
after `brew upgrade warmline`; `warmline setup --remove` unwires it again.

Everything else — what the fields mean, how the audit works, whether keep-warm
is worth it — lives in the
[main repository](https://github.com/Miguel-Barroso/claude-warmline). Issues and
pull requests belong there too, including changes to the formula:
[`packaging/homebrew/warmline.rb`](https://github.com/Miguel-Barroso/claude-warmline/blob/main/packaging/homebrew/warmline.rb)
is its source of truth, and this tap holds the published copy.

MIT, same as the project.
