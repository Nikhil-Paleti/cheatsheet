# tmux — Cheatsheet

```sh
tmux new -s work       # create and enter a session named work
tmux ls                # list sessions on this machine
tmux attach -t work    # return to an existing session
```

| Goal | Keys inside tmux |
| --- | --- |
| Detach and leave programs running | `Ctrl+b, d` |
| Choose a session | `Ctrl+b, s` |
| Create a window | `Ctrl+b, c` |
| Next / previous window | `Ctrl+b, n` / `Ctrl+b, p` |
| Choose a window | `Ctrl+b, w` |
| Go to window 0 | `Ctrl+b, 0` |
| Rename current window | `Ctrl+b, ,`, type name, Enter |
| Split into left and right panes | `Ctrl+b, %` |
| Split into top and bottom panes | `Ctrl+b, "` |
| Move to another pane | `Ctrl+b, Arrow key` |
| Zoom current pane / restore layout | `Ctrl+b, z` |
| Show keybindings | `Ctrl+b, ?` |
