---
created: 2022-08-26 18:34:48
updated: 2026-05-30 22:51:16
---

# Vim Plugins

Before installing a plugin try to do it the pure Vim way.

Plugins are managed with [lazy.nvim](https://github.com/folke/lazy.nvim). Configs live in `~/.config/nvim/lua/plugins/`.

## AI / Completion

- [Exafunction/windsurf.vim](https://github.com/Exafunction/windsurf.vim) — Codeium AI inline completions.
- [saghen/blink.cmp](https://github.com/saghen/blink.cmp) — fast auto-completion with LSP, snippets, buffer, and path sources.
- [saghen/blink.pairs](https://github.com/saghen/blink.pairs) — intelligent bracket pair management.
- [kylechui/nvim-surround](https://github.com/kylechui/nvim-surround) — quoting/parenthesizing made simple.
- [windwp/nvim-ts-autotag](https://github.com/windwp/nvim-ts-autotag) — auto-close and rename HTML/JSX tags.
- [L3MON4D3/LuaSnip](https://github.com/L3MON4D3/LuaSnip) — snippet engine.
- [psto/friendly-snippets](https://github.com/psto/friendly-snippets) — my fork of [rafamadriz/friendly-snippets](https://github.com/rafamadriz/friendly-snippets) curated collection of snippets.

## LSP / Language Support

- [neovim/nvim-lspconfig](https://github.com/neovim/nvim-lspconfig) — core LSP client configuration.
- [mason-org/mason.nvim](https://github.com/mason-org/mason.nvim) — portable package manager for LSP servers, DAP, linters, formatters.
- [mason-org/mason-lspconfig.nvim](https://github.com/mason-org/mason-lspconfig.nvim) — bridges mason and lspconfig.
- [WhoIsSethDaniel/mason-tool-installer.nvim](https://github.com/WhoIsSethDaniel/mason-tool-installer.nvim) — ensure tools are installed automatically.
- [j-hui/fidget.nvim](https://github.com/j-hui/fidget.nvim) — LSP progress and status updates.
- [folke/lazydev.nvim](https://github.com/folke/lazydev.nvim) — faster LuaLS setup for Neovim config.
- [folke/ts-comments.nvim](https://github.com/folke/ts-comments.nvim) — tree-sitter-based commenting.

## Debugging

- [mfussenegger/nvim-dap](https://github.com/mfussenegger/nvim-dap) — Debug Adapter Protocol client.
- [rcarriga/nvim-dap-ui](https://github.com/rcarriga/nvim-dap-ui) — UI for nvim-dap.
- [nvim-neotest/nvim-nio](https://github.com/nvim-neotest/nvim-nio) — async IO library for Neovim plugins.
- [jayp0521/mason-nvim-dap.nvim](https://github.com/jayp0521/mason-nvim-dap.nvim) — install DAP adapters via Mason.

## Git

- [lewis6991/gitsigns.nvim](https://github.com/lewis6991/gitsigns.nvim) — async git signs in the signcolumn.
- [sindrets/diffview.nvim](https://github.com/sindrets/diffview.nvim) — side-by-side diff viewer.
- [ThePrimeagen/git-worktree.nvim](https://github.com/ThePrimeagen/git-worktree.nvim) — git worktree management.

## Navigation

- [nvim-telescope/telescope.nvim](https://github.com/nvim-telescope/telescope.nvim) — Find, Filter, Preview, Pick.
- [nvim-telescope/telescope-fzf-native.nvim](https://github.com/nvim-telescope/telescope-fzf-native.nvim) — FZF sorter for telescope.
- [nvim-telescope/telescope-file-browser.nvim](https://github.com/nvim-telescope/telescope-file-browser.nvim) — file browser extension.
- [nvim-telescope/telescope-ui-select.nvim](https://github.com/nvim-telescope/telescope-ui-select.nvim) — UI select integration.
- [debugloop/telescope-undo.nvim](https://github.com/debugloop/telescope-undo.nvim) — visual undo tree in telescope.
- [alexghergh/nvim-tmux-navigation](https://github.com/alexghergh/nvim-tmux-navigation) — seamless navigation between tmux panes and vim splits.
- [dmtrKovalenko/fff.nvim](https://github.com/dmtrKovalenko/fff.nvim) — blazing fast fuzzy finder with native binary.
- [developedbyed/marko.nvim](https://github.com/developedbyed/marko.nvim) — marks UI and navigation.
- [nvim-neo-tree/neo-tree.nvim](https://github.com/nvim-neo-tree/neo-tree.nvim) — file tree explorer.

## Search / Replace

- [nvim-pack/nvim-spectre](https://github.com/nvim-pack/nvim-spectre) — search and replace across the project (like ripgrep + sed).

## Colors / Highlighting

- [nvim-treesitter/nvim-treesitter](https://github.com/nvim-treesitter/nvim-treesitter) — tree-sitter interface for Neovim (highlighting, indentation, incremental selection).
- [folke/tokyonight.nvim](https://github.com/folke/tokyonight.nvim) — a clean, dark colorscheme.
- [nvim-tree/nvim-web-devicons](https://github.com/nvim-tree/nvim-web-devicons) — pretty icons and colors.
- [brenoprata10/nvim-highlight-colors](https://github.com/brenoprata10/nvim-highlight-colors) — highlight color codes with their actual color.

## UI / Status

- [nvim-lualine/lualine.nvim](https://github.com/nvim-lualine/lualine.nvim) — blazing fast and easy to configure statusline.
- [folke/which-key.nvim](https://github.com/folke/which-key.nvim) — displays keybinding popups as you type.
- [folke/trouble.nvim](https://github.com/folke/trouble.nvim) — pretty diagnostics, references, telescope results, quickfix and location list.
- [akinsho/nvim-toggleterm.lua](https://github.com/akinsho/nvim-toggleterm.lua) — floating and split terminal manager.
- [lewis6991/satellite.nvim](https://github.com/lewis6991/satellite.nvim) — a scrollbar with diagnostics, git signs, marks, and search.
- [mini.indentscope](https://github.com/echasnovski/mini.indentscope) — indent scope visualization.
- [lukas-reineke/indent-blankline.nvim](https://github.com/lukas-reineke/indent-blankline.nvim) — indentation level lines.

## Formatting

- [stevearc/conform.nvim](https://github.com/stevearc/conform.nvim) — code formatting on save.

## Writing

- [folke/zen-mode.nvim](https://github.com/folke/zen-mode.nvim) — distraction-free writing.
- [folke/twilight.nvim](https://github.com/folke/twilight.nvim) — dims inactive parts of the buffer for hyperfocus.
- [gaoDean/autolist.nvim](https://github.com/gaoDean/autolist.nvim) — automatic list continuation and cycling.
- [MeanderingProgrammer/render-markdown.nvim](https://github.com/MeanderingProgrammer/render-markdown.nvim) — preview markdown in the buffer.
- [zk-org/zk-nvim](https://github.com/zk-org/zk-nvim) — Zettelkasten note-taking integration.

## Quality of Life

- [goolord/alpha-nvim](https://github.com/goolord/alpha-nvim) — fast, feature-rich dashboard / start screen.
- [m4xshen/hardtime.nvim](https://github.com/m4xshen/hardtime.nvim) — helps build good Vim habits by disabling bad movement patterns.
