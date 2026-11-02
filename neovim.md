# LazyVim / Neovim — Cheatsheet

Start in Normal mode (`Esc`). Keys are sequential unless joined by `+`; uppercase means Shift. `Leader` is Space in my LazyVim config. Commands starting with `:`, `/`, or `?` need Enter.

## Modes and typing

| Goal | Keys |
| --- | --- |
| Normal mode / cancel | `Esc` |
| Type before / after cursor | `i` / `a` |
| Type at first nonblank / end of line | `I` / `A` |
| New line below / above | `o` / `O` |
| Select characters / lines / rectangle | `v` / `V` / `Ctrl+v` |

## Movement and search

| Goal | Keys |
| --- | --- |
| Left / down / up / right | `h` / `j` / `k` / `l` |
| Next / previous word; end of word | `w` / `b`; `e` |
| Next / previous whitespace-separated word | `W` / `B` |
| Line start / first nonblank / line end | `0` (zero) / `^` / `$` |
| First / last line; line 42 | `gg` / `G`; `42G` |
| Paragraph forward / backward; matching bracket | `}` / `{`; `%` |
| Find next `x` on line / stop before it | `fx` / `tx` |
| Find previous `x` / stop after it | `Fx` / `Tx` |
| Repeat character find / reverse | `;` / `,` |
| Half-screen down / up; center cursor line | `Ctrl+d` / `Ctrl+u`; `zz` |
| Jump back / forward | `Ctrl+o` / `Ctrl+i` |
| Search forward / backward | `/text` / `?text` |
| Next / previous match | `n` / `N` (LazyVim: forward / backward) |
| Search word under cursor forward / backward | `*` / `#` |
| Clear highlights | `:noh` (LazyVim also clears with `Esc`) |
| Literal search | `/\Vfoo.bar` |
| Replace whole word throughout file, confirm each | `:%s/\<old\>/new/gc` |

## Editing and selection

| Goal | Keys |
| --- | --- |
| Change word / line contents / through line end | `ciw` / `cc` / `C`, type, `Esc` |
| Delete character / line / through line end | `x` / `dd` / `D` |
| Replace one character with z | `rz` |
| Copy line / three lines | `yy` / `3yy` |
| Paste after / before (whole lines: below / above) | `p` / `P` |
| Undo / redo; repeat last edit | `u` / `Ctrl+r`; `.` |
| Join next line; duplicate current line | `J`; `yyp` |
| Select three lines / whole file | `V2j` / `ggVG` |
| Copy / cut / replace selection | `y` / `d` / `c` |
| Reselect last selection | `gv` |
| Comment / uncomment current line (Normal mode) | `gcc` |
| Comment / uncomment selected lines (Visual Line mode) | `V`, extend with `j` / `k`, then `gc`; reselect and `gc` to uncomment |
| Indent / unindent current line | `>>` / `<<` |
| Indent / unindent current and next line | `>j` / `<j` |
| Indent / unindent selection | `>` / `<` (LazyVim keeps it selected) |
| Indent lines 8–9 / unindent | `:8,9>` / `:8,9<` |
| Copy / delete lines 10–15 | `:10,15y` / `:10,15d` |
| Copy / paste system clipboard | `"+y` / `"+p` (clipboard support required) |
| Delete line without replacing copied text | `"_dd` |

Counts repeat actions: `5j` moves five lines. `V2j` selects three because the starting line counts.

## Text objects

Use `v` to select, `c` to change, `d` to delete, or `y` to copy, followed by a target:

| Target | Example: change |
| --- | --- |
| Inside word / word plus adjacent whitespace | `ciw` / `caw` |
| Inside double / single quotes | `ci"` / `ci'` |
| Inside parentheses / brackets / braces | `ci(` / `ci[` / `ci{` |
| Inside paragraph | `cip` |

`ci"` keeps the quotes; `ca"` includes them. After `c`, type the replacement and press `Esc`.

Wrap whole lines in braces without a plugin: select with `V`, then `Esc` → backtick then `>` → `o`, type `}`, `Esc` → backtick then `<` → `O`, type `{`, `Esc`. Use `]` / `[` for brackets.

## LazyVim files and code

These are LazyVim defaults in my current config, not stock Neovim mappings. No personal keymap overrides are configured.

| Goal | Keys |
| --- | --- |
| Find files / search project text | `Leader, f, f` / `Leader, s, g` |
| File explorer (project root) | `Leader, e` |
| Previous / next buffer | `Shift+h` / `Shift+l` |
| Close buffer | `Leader, b, d` |
| Split below / right | `Leader, -` / `Leader, \|` |
| Move to left / lower / upper / right window | `Ctrl+h` / `Ctrl+j` / `Ctrl+k` / `Ctrl+l` |
| Definition / references (LSP) | `gd` / `gr` |
| Rename symbol / code action (LSP) | `Leader, c, r` / `Leader, c, a` |
| Format file / selection (formatter required) | `Leader, c, f` |
| Next / previous diagnostic | `]d` / `[d` |
| Save / save all | `:w` / `:wa` |
| Save and quit window / quit window | `:wq` / `:q` |

In VS Code, use its file/window actions; Ctrl keys may be intercepted. `=` uses VS Code formatting there; in terminal Neovim it reindents.

[Neovim reference](https://neovim.io/doc/user/quickref/) · [LazyVim keymaps](https://www.lazyvim.org/keymaps)
