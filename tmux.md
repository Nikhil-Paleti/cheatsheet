# tmux — Cheatsheet

Uses my dotfiles `~/.tmux.conf`: `Prefix` is `Ctrl+A` (tmux default: `Ctrl+B`). Press it, release, then press the next key. Shell commands need Enter.

## Sessions

| Goal | Shell command / keys inside tmux |
| --- | --- |
| Create and enter `work` | Shell: `tmux new -s work` |
| List sessions on this machine | Shell: `tmux ls` |
| Kill a named session and stop its programs | Shell: `tmux kill-session -t <session-name>` (e.g. `tmux kill-session -t work`) |
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
| Go to window 1–9 (numbering starts at 1) | `Prefix, 1`–`9` |
| Rename current window | `Prefix, ,`, type name, Enter |
| Close window and its panes (confirm) | `Prefix, &` |

## Panes

| Goal | Keys inside tmux |
| --- | --- |
| Split left / right | `Prefix, %` |
| Split top / bottom | `Prefix, "` |
| Move left / down / up / right | `Prefix, h` / `j` / `k` / `l` (or Arrow keys) |
| Resize left / down / up / right by 5 cells | `Prefix, H` / `J` / `K` / `L` (Shift; repeat quickly without Prefix) |
| Show pane numbers (start at 1) | `Prefix, q` |
| Cycle through panes | `Prefix, o` |
| Zoom / restore current pane | `Prefix, z` |
| Cycle pane layouts | `Prefix, Space` |
| Close current pane (confirm) | `Prefix, x` |

Reload `~/.tmux.conf`: `Prefix, r`. Mouse support is enabled. All keybindings: `Prefix, ?`.
