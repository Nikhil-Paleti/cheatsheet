# Bash — Cheatsheet

Default Bash / Readline Emacs bindings at the command prompt, not inside Neovim or other programs. `Alt` shortcuts require the terminal to send Meta; `Esc`, then the letter also works.

## Move

| Goal | Keys |
| --- | --- |
| Start / end of line | `Ctrl+A` / `Ctrl+E` |
| Back / forward one word | `Alt+B` / `Alt+F` |

## Edit

| Goal | Keys |
| --- | --- |
| Cut from cursor to start of line | `Ctrl+U` |
| Cut from cursor to end of line | `Ctrl+K` |
| Cut previous whitespace-separated word | `Ctrl+W` |
| Cut next word | `Alt+D` |
| Paste back cut text (not the system clipboard) | `Ctrl+Y` |
| Undo an edit | `Ctrl+_` |

Example: at the end of a long command, `Ctrl+U` cuts the line; `Ctrl+Y` brings it back.

## History and prompt

| Goal | Keys |
| --- | --- |
| Search history backward | `Ctrl+R`, type text; repeat `Ctrl+R` for older matches |
| Previous / next command | `Up` / `Down` |
| Complete a command or filename | `Tab` |
| Clear/redraw the screen; keep current input | `Ctrl+L` |
| Cancel input / interrupt a running command | `Ctrl+C` |

## Inside TuiOS

With my `Ctrl+A` leader, press `Ctrl+A` twice to send it to Bash and jump to the start of the line. TuiOS can capture other keys too, such as `Ctrl+P` for its command palette; use `Up` for previous-command history.

[Bash line editing](https://www.gnu.org/software/bash/manual/html_node/Bindable-Readline-Commands.html) · [TuiOS keybindings](https://tuios.dev/docs/keybindings)
