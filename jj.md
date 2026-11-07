# jj / Git Cheatsheet

Closest workflows, not exact aliases. `@` = jj's working-copy commit; `@-` = its parent(s). `BASE` = remote branch, `FEATURE` = your branch/bookmark, `CHANGE` = commit/change ID.

jj snapshots edits when you run commands, with no staging area. New, non-ignored files are tracked automatically by default. `HEAD` and `@` are not interchangeable.

## LFS: fresh code-only checkout

Use a separate checkout, not one with downloaded LFS assets. With Git LFS already installed, replace `<repo-url>` and run:

```sh
GIT_LFS_SKIP_SMUDGE=1 git clone <repo-url> myrepo-jj
cd myrepo-jj
git lfs install --local --skip-smudge

git status --porcelain
git lfs ls-files
```

Status should be empty. LFS entries should show `-` (pointer), not `*` (downloaded content). If either check fails, stop before initializing jj. Then:

```sh
jj git init --colocate
jj status
```

Keep this checkout code-only. Do not run `git lfs pull` / `git lfs checkout`; leave LFS files and their tracking rules unchanged. Do asset work and Git pushes in a separate normal Git+LFS checkout. Skip-smudge does not give jj LFS filtering or upload support.

## Start

| Goal | Git | jj |
| --- | --- | --- |
| Clone (no LFS) | `git clone URL DIR` | `jj git clone URL DIR` |
| Enable jj in a Git repo (no LFS) | Already a Git repo | `jj git init --colocate` |
| Fetch | `git fetch origin` | `jj git fetch --remote origin` |
| Fetch one branch | `git fetch origin BASE` | `jj git fetch --remote origin --branch BASE` |
| Start work from a remote branch | `git switch -c FEATURE origin/BASE` | `jj new BASE@origin` |

## Inspect and edit

| Goal | Git | jj |
| --- | --- | --- |
| Status | `git status` | `jj status` |
| History graph | `git log --oneline --graph` | `jj log` |
| Current changes | `git diff HEAD` | `jj diff` |
| Inspect a commit | `git show CHANGE` | `jj show CHANGE` |
| Finish current work | `git add -A && git commit -m "Message"` | `jj commit -m "Message"` |
| Edit current message | `git commit --amend --only -m "Message"` | `jj describe -m "Message"` |
| Commit selected hunks | `git add -p && git commit` | `jj commit -i` |
| Pause work / return later | `git stash` / `git stash pop` | `jj new BASE@origin` / `jj edit CHANGE` |

`jj commit` describes `@`, then starts an empty child. `jj describe` stays on `@`. Before pausing, note its change ID. `jj edit CHANGE` resumes it in place; it does not apply it elsewhere like `stash pop`.

## Stacks

| Goal | Git | jj |
| --- | --- | --- |
| Edit an earlier commit | `git rebase -i CHANGE^` (choose `edit`) | `jj edit CHANGE`, then edit files |
| Fold current edits into parent | `git add -A && git commit --amend` | `jj squash` |
| Split an earlier commit | `git rebase -i CHANGE^` (manual split) | `jj split -r CHANGE` |
| Insert before a commit | `git rebase -i CHANGE^` (manual insertion) | `jj new --insert-before CHANGE` |
| Rebase current stack | `git rebase origin/BASE` | `jj rebase -b @ --onto BASE@origin` |
| Rebase from a chosen commit | `git rebase --onto origin/BASE CHANGE^ FEATURE` | `jj rebase -s CHANGE --onto BASE@origin` |

Fetch first: fetching does not rebase your stack. jj automatically rebases descendants when you edit a commit; `-s` includes every descendant. Coordinate before rewriting shared history.

For conflicts: `jj edit CHANGE`, fix the files, then `jj status`. There is no `add` or `--continue` step.

## Bookmarks and push

| Goal | Git | jj |
| --- | --- | --- |
| List local and remote names | `git branch -a` | `jj bookmark list --all-remotes` |
| Name current commit | `git branch FEATURE` | `jj bookmark set FEATURE -r @` |
| Move name to last finished commit | Branch advances on commit | `jj bookmark set FEATURE -r @-` (when `@` is empty) |
| Preview push | `git push --dry-run origin FEATURE` | `jj git push --remote origin --bookmark FEATURE --dry-run` |
| Push branch | `git push origin FEATURE` | `jj git push --remote origin --bookmark FEATURE` |

Bookmarks follow rewritten commits, not `jj new` or `jj commit`; move yours before pushing. jj push also supports rewrites with lease-style safety checks. Preview and coordinate first.

## Restore and undo

| Goal | Git | jj |
| --- | --- | --- |
| Discard a file's current changes | `git restore --source=HEAD --staged --worktree FILE` | `jj restore FILE` (from parent(s)) |
| Inspect recovery history | `git reflog` (per ref) | `jj op log` (repository operations) |
| Undo last operation | No single equivalent | `jj undo` |

`jj undo` restores local repository state; it does not undo a remote push.

Checked with jj 0.47.1. [jj command table](https://docs.jj-vcs.dev/latest/git-command-table/) · [jj reference](https://docs.jj-vcs.dev/latest/cli-reference/) · [LFS setup](https://github.com/git-lfs/git-lfs/blob/main/docs/man/git-lfs-install.adoc) · [LFS status markers](https://github.com/git-lfs/git-lfs/blob/main/docs/man/git-lfs-ls-files.adoc)
