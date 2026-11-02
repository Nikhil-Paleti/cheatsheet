# tmux — Beginner Cheatsheet

Keep terminal work running, split your screen, and reconnect later.

Assumes tmux is already available and uses the default **Ctrl+b** prefix. Custom configuration can change these keys.

## Start here

Run these in your shell, outside tmux:

```sh
tmux new -s work       # create and enter a session named work
tmux ls                # list sessions on this machine
tmux attach -t work    # return to an existing session
```

If `work` already exists, attach to it instead of creating it again.

**Read the keys:** `Ctrl+b, d` means hold Ctrl and press b, release both, then press d. Do not hold Ctrl for the second key. Commands typed in a shell need Enter.

## Sessions, windows, panes

- **Session:** a named workspace, such as `work`.
- **Window:** a tab inside a session.
- **Pane:** one terminal area inside a window.

Example: one `work` session → an editor window and a server window → two side-by-side panes in the editor window.

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

For `%` and `"`, type the symbol using Shift as needed on your keyboard.

## SSH: leave and return

Start tmux **on the remote machine** so the work stays there:

```sh
ssh user@server
tmux new -s work
# Start your editor or long-running command here.
```

Press **Ctrl+b, d** to detach. You are now back at the remote shell; `exit` closes SSH.

Later, from the same laptop or another computer:

```sh
ssh user@server
tmux ls
tmux attach -t work
```

A dropped SSH connection normally leaves remote tmux programs running. Reconnect to the **same server and user account**, then attach. tmux does not preserve work through a server reboot.

## Multiple machines

Sessions live on the machine where tmux runs; they do not sync between machines.

```sh
# Server A
ssh user@server-a
tmux attach -t work

# In a separate local terminal, Server B
ssh user@server-b
tmux attach -t work
```

These are two different `work` sessions. Use `hostname` in a pane to check the machine. To continue Server A's work from another laptop, SSH to Server A with the same account.

Two clients can attach to the same session and share its view. From outside tmux, `tmux attach -d -t work` attaches here and detaches the other clients.

## Detach versus finish

- **Come back later:** `Ctrl+b, d`. Programs continue running.
- **Finish a pane:** stop or quit its program, then type `exit` at its shell prompt. Closing the final pane closes that window; closing the final window ends the session.
- **Stop a foreground command:** usually `Ctrl+c`; this goes to the program, without a tmux prefix.

## Two-minute practice

1. Run `tmux new -s practice`.
2. Split left/right with `Ctrl+b, %`.
3. Move between panes with `Ctrl+b, Arrow key`.
4. Create a window with `Ctrl+b, c`; return with `Ctrl+b, p`.
5. Detach with `Ctrl+b, d`.
6. Run `tmux attach -t practice` to return.

## References

- [tmux Getting Started](https://github.com/tmux/tmux/wiki/Getting-Started)
- [tmux manual](https://man.openbsd.org/tmux)
