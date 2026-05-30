---
created: 2026-05-30 00:00:00
updated: 2026-05-30 23:14:18
---

# ZSH Configuration

A modular, hand-rolled ZSH setup. No oh-my-zsh, no prezto, no framework bloat.

Config lives in `~/.config/zsh/` and is loaded from `.zshrc`. See my full config at [.dotfiles/zsh/.config/zsh](https://github.com/psto/.dotfiles/tree/main/zsh/.config/zsh).

## Why Skip the Framework?

oh-my-zsh includes 300+ plugins, 140+ themes, and a slow `compinit` that adds **300-500ms** to every shell start. This config does the opposite:

| Concern | oh-my-zsh approach | This config |
|---|---|---|
| Plugin loading | Sources everything at once, blocking startup | Auto-clones and sources only what's needed |
| Completion init | Loads all completions upfront | Cached, daily compinit (`-C` flag after first run) |
| Features | 200+ plugins you didn't ask for | 4 plugins, each justified |
| Startup time | ~400ms+ | ~50ms |
| Maintenance | Opaque framework to learn | Flat files, trivial helpers, zero magic |

## Core Files

| File            | Purpose                                                                          |
| --------------- | -------------------------------------------------------------------------------- |
| `.zshrc`        | Main entrypoint: options, completions, sourcing, keybinds, external tool init    |
| `zsh-exports`   | PATH, environment variables, language runtimes (node, ruby, go, rust, deno, bun) |
| `zsh-aliases`   | 200+ aliases: git, packages, system, taskwarrior, yt-dlp, media, etc.            |
| `zsh-functions` | Plugin loader, FZF helpers, git helpers, download helpers, history widget        |
| `zsh-vim-mode`  | vi mode with per-mode cursor shape changes                                       |
| `zsh-prompt`    | Legacy prompt (currently unused in favor of starship)                            |

## Plugin Infrastructure

No plugin manager, just a single 6-line function:

```zsh
zsh_add_plugin() {
  PLUGIN_NAME=$(echo $1 | cut -d "/" -f 2)
  if [ -d "$ZDOTDIR/plugins/$PLUGIN_NAME" ]; then
    zsh_add_file "plugins/$PLUGIN_NAME/$PLUGIN_NAME.plugin.zsh" || \
    zsh_add_file "plugins/$PLUGIN_NAME/$PLUGIN_NAME.zsh"
  else
    git clone "https://github.com/$1.git" "$ZDOTDIR/plugins/$PLUGIN_NAME"
  fi
}
```

If the plugin isn't cloned yet, it auto-clones on first shell start. After that it's a no-op. A companion `zsh_add_completion` does the same for completion scripts.

## Plugins

- **[Aloxaf/fzf-tab](https://github.com/Aloxaf/fzf-tab)** - replaces ZSH's tab completion menu with an fzf interface. Must load before autosuggestions and syntax highlighting.
- **[zsh-users/zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions)** - suggests completions as you type based on history. Uses `(history match_prev_cmd)` strategy with a blue highlight (`fg=#668ac4`).
- **[zdharma-continuum/fast-syntax-highlighting](https://github.com/zdharma-continuum/fast-syntax-highlighting)** - real-time syntax highlighting as you type (faster than the original `zsh-syntax-highlighting`).
- **[hlissner/zsh-autopair](https://github.com/hlissner/zsh-autopair)** - auto-closes quotes, brackets, and parentheses.

## External Tools

Composed CLI tools, not ZSH plugins. They're installed once via the system package manager and wired in with a single `eval` or `source`.

### FZF History Widget with Delete

The standard `^R` is replaced with a custom `modified-fzf-history-widget` that:

1. Appends the current buffer to `$HISTFILE`
2. Loads a fresh history stack (so `^D` can delete from it)
3. Deduplicates entries via `awk`
4. Accepts a custom query (not just history selection)
5. **Deletes entries** with `^D` by writing `HISTORY_IGNORE` patterns

### Vim Mode with Cursor Shapes

```zsh
bindkey -v
export KEYTIMEOUT=1
```

Per-mode cursor changes:
- **Normal** (`vicmd`): block cursor (`\e[1 q`)
- **Insert** (`viins`): beam cursor (`\e[5 q`)

Cursor resets to beam on every new prompt via `preexec`.

### Smart `cd` Hook (`status-ls`)

```zsh
add-zsh-hook chpwd status-ls
```

On every directory change:
- Inside a git repo: `git status -sb`
- Otherwise: `eza` (directory listing)

### OSC-7 for Foot Terminal

The `osc7` hook emits an escape sequence so the foot terminal opens new windows in the current directory - not `$HOME`.

### Built-in ZSH Text Objects

No plugin needed. These are native ZSH:

```zsh
autoload -U select-quoted
autoload -U select-bracketed
```

Enables `ci'`, `ci"`, `ci(`, `ci{`, `ci<` and `di'`, `di(` etc. in visual mode.

### Clean History

20+ history `setopt`s including: append-only, no duplicates, no space-prefixed commands, share across terminals, immediate append, and command duration recording.
