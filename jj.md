# jj — Cheatsheet

`@` = current change; `@-` = parent. Replace `BASE` with an existing remote branch, `FEATURE` with your branch name, and `CHANGE` with an ID from `jj log`.

## Start

| Goal | Command |
| --- | --- |
| Install on macOS | `brew install jj` |
| Enable jj in a Git repo (once, at repo root) | `jj git init --colocate` |
| Fetch a branch | `jj git fetch --remote origin --branch BASE` |
| Start a change on that branch | `jj new BASE@origin` |

## Changes

| Goal | Command |
| --- | --- |
| Status / history | `jj status` / `jj log` |
| Current diff | `jj diff` |
| Describe current change | `jj describe -m "Add feature"` |
| Start next change | `jj new` |
| Edit an earlier change | `jj edit CHANGE` |
| Insert before a change | `jj new --insert-before CHANGE` |
| Rebase a change and its descendants | `jj rebase -s CHANGE --onto BASE@origin` |
| Undo last operation | `jj undo` |

## Push

| Goal | Command |
| --- | --- |
| List bookmarks | `jj bookmark list --all-remotes` |
| Name / move your branch to current change | `jj bookmark set FEATURE -r @` |
| Use parent instead when `@` is empty | `jj bookmark set FEATURE -r @-` |
| Preview push | `jj git push --remote origin --bookmark FEATURE --dry-run` |
| Push | `jj git push --remote origin --bookmark FEATURE` |

Edits save automatically. Bookmarks follow edits, not `jj new`; move yours before pushing. Fetch before rebasing. Coordinate before rewriting shared history.

[Command reference](https://docs.jj-vcs.dev/latest/cli-reference/).
