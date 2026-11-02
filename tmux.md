# tmux — Cheatsheet

Default prefix: `Ctrl+b`, release, then the next key. Shell commands need Enter.

## Sessions

| Goal | Shell command / keys inside tmux |
| --- | --- |
| Create and enter `work` | Shell: `tmux new -s work` |
| List sessions on this machine | Shell: `tmux ls` |
| Attach to `work` | Shell: `tmux attach -t work` |
| Attach here, detach other clients | Shell: `tmux attach -d -t work` |
| Detach; keep programs running | `Ctrl+b, d` |
| Choose a session | `Ctrl+b, s` |
| Rename current session | `Ctrl+b, $`, type name, Enter |

## Windows

| Goal | Keys inside tmux |
| --- | --- |
| Create a window | `Ctrl+b, c` |
| Next / previous window | `Ctrl+b, n` / `Ctrl+b, p` |
| Choose a window | `Ctrl+b, w` |
| Go to window 0–9 | `Ctrl+b, 0`–`9` |
| Rename current window | `Ctrl+b, ,`, type name, Enter |
| Close window and its panes (confirm) | `Ctrl+b, &` |

## Panes

| Goal | Keys inside tmux |
| --- | --- |
| Split left / right | `Ctrl+b, %` |
| Split top / bottom | `Ctrl+b, "` |
| Move to another pane | `Ctrl+b, Arrow key` |
| Cycle through panes | `Ctrl+b, o` |
| Zoom / restore current pane | `Ctrl+b, z` |
| Cycle pane layouts | `Ctrl+b, Space` |
| Close current pane (confirm) | `Ctrl+b, x` |

All keybindings: `Ctrl+b, ?`.
