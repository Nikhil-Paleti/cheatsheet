# Git — Cheatsheet

Run inside your repo (except clone). Replace `<file>`, `<branch>`, and `<commit>` with real names or IDs; omit the angle brackets. Examples use `main` and remote `origin`.

## Check changes

| Goal | Command |
| --- | --- |
| See branch, changed files, and staging state | `git status` |
| See unstaged changes to tracked files | `git diff` |
| See staged changes (next commit) | `git diff --staged` |
| See recent commits and branch graph | `git log --oneline --graph --decorate -15` |
| Inspect a commit | `git show <commit>` |

## Stage and commit

| Goal | Command |
| --- | --- |
| Stage one file (including a new file or deletion) | `git add -- <file>` |
| Choose individual changes to stage | `git add -p` |
| Unstage a file; keep its edits | `git restore --staged -- <file>` |
| Commit staged changes | `git commit -m "Describe the change"` |

## Branches

| Goal | Command |
| --- | --- |
| List local branches and their upstreams | `git branch -vv` |
| Create and switch to a branch | `git switch -c <branch>` |
| Switch to an existing branch | `git switch <branch>` |
| Return to main | `git switch main` |
| Merge a branch into the current branch | `git merge <branch>` |
| Delete a local branch (checks it is merged) | `git branch -d <branch>` |

Commit your work before switching or merging. If a merge conflicts, edit the marked files, `git add -- <file>`, then `git merge --continue`. Cancel that merge with `git merge --abort`.

## Remote and sync

| Goal | Command |
| --- | --- |
| Download a repo for the first time | `git clone <repo-url>` |
| Show remote URLs | `git remote -v` |
| Fetch remote updates without changing your files | `git fetch origin` |
| List remote branches after fetching | `git branch -r` |
| Update current branch from its upstream, only if fast-forward | `git pull --ff-only` |
| First push of current branch; set its upstream | `git push -u origin HEAD` |
| Push later commits to that upstream | `git push` |

Use pull with a clean working tree and an upstream set. If `--ff-only` refuses, local and remote history have diverged; inspect the log before deciding how to combine them.

## Undo a committed change

| Goal | Command |
| --- | --- |
| Undo a regular commit with a new commit (keeps history) | `git revert <commit>` |
| Finish a revert after resolving conflicts and staging files | `git revert --continue` |
| Cancel an in-progress revert | `git revert --abort` |

Start a revert with a clean working tree. Use `git log` to find the commit ID; merge commits need special handling.

[Git command reference](https://git-scm.com/docs)
