# tmux — Cheatsheet

`Prefix` is `Ctrl+B` by default: press it, release, then press the next key. Shell commands need Enter.

## Sessions

| Goal | Shell command / keys inside tmux |
| --- | --- |
| Create and enter `work` | Shell: `tmux new -s work` |
| List sessions on this machine | Shell: `tmux ls` |
| Attach to `work` | Shell: `tmux attach -t work` |
| Attach here, detach other clients | Shell: `tmux attach -d -t work` |
| Detach; keep programs running | `Prefix, d` |
| Choose a session | `Prefix, s` |
| Rename current session | `Prefix, $`, type name, Enter |

## Windows

| Goal | Keys inside tmux |
| --- | --- |
| Create a window | `Prefix, c` |
| Next / previous window | `Prefix, n` / `Prefix, p` |
| Choose a window | `Prefix, w` |
| Go to window 0–9 | `Prefix, 0`–`9` |
| Rename current window | `Prefix, ,`, type name, Enter |
| Close window and its panes (confirm) | `Prefix, &` |

## Panes

| Goal | Keys inside tmux |
| --- | --- |
| Split left / right | `Prefix, %` |
| Split top / bottom | `Prefix, "` |
| Move to another pane | `Prefix, Arrow key` |
| Cycle through panes | `Prefix, o` |
| Zoom / restore current pane | `Prefix, z` |
| Cycle pane layouts | `Prefix, Space` |
| Close current pane (confirm) | `Prefix, x` |

All keybindings: `Prefix, ?`.
