# Git workflow tracker

Git workflows to cover while learning jj. Add more to this list as they come up.

Use these as independent examples in an initialized jj repository with `origin` and author identity configured. Replace uppercase `*_ID` placeholders with change IDs from `jj log`, and sample file paths with yours. For the ten-commit examples, `nikhil/feature` points at `J`, the latest commit. Bookmark creation examples use names that do not already exist.

In jj, bookmarks publish as Git branches. `@` is the working-copy change; `@-` is its parent. These examples rewrite your own mutable changes. Resolve any conflicts before pushing.

## 1. Fetch a branch from `origin`.

**Example:** A teammate has pushed `nikhil/search` to `origin`. Fetch it so you can inspect that branch and its latest commits locally.

```sh
jj git fetch --remote origin --branch nikhil/search
jj bookmark track nikhil/search@origin
jj new nikhil/search
```

The last command starts a new change on top of the fetched branch.

## 2. Create a local branch and push it to `origin`.

**Example:** Start a local branch named `nikhil/search`, add your search-bar changes, then push that branch to `origin`.

```sh
jj new main@origin
# Edit your files.
jj commit -m "Add search bar"
jj bookmark create nikhil/search -r @-
jj git push --remote origin --bookmark nikhil/search
```

`jj commit` leaves a new empty `@`, so the bookmark points to the completed commit at `@-`.

## 3. Cherry-pick a commit to my branch.

**Example:** Another branch has a commit that fixes a search crash. Copy just that commit onto `nikhil/search`, without bringing over the rest of the other branch.

```sh
jj new nikhil/search
jj duplicate SOURCE_ID --insert-before @
jj bookmark set nikhil/search -r @-
```

`SOURCE_ID` is the commit to copy. The original stays unchanged; the bookmark moves to the copied commit.

## 4. In a chain of 10 commits, make a change and amend it into the relevant commit.

**Example:** Your 10-commit chain is `A → B → C → D → E → F → G → H → I → J`, oldest to newest. Commit `C` adds validation. Make a validation fix and fold it into `C`, keeping `D` through `J` after it.

```sh
jj new nikhil/feature
# Make the validation fix in src/validation.py.
jj squash --into C_ID -u src/validation.py
```

This moves that file's fix into `C` and keeps `C`'s existing message. Later changes are rebased automatically.

## 5. In a chain of 10 commits, drop the 2nd commit or edit the 2nd commit.

**Example:** In the same `A`-through-`J` chain, the 2nd commit, `B`, adds debug logging. Drop `B` to remove that logging, or edit `B` to keep only the useful log statements.

Drop `B`:

```sh
jj abandon B_ID
```

Or edit `B` instead:

```sh
jj edit B_ID
# Edit the files changed by B and save them.
jj new nikhil/feature
```

The final command snapshots the edits and starts a new change at the updated stack tip.

## 6. In a chain of 10 commits, insert a commit in 6th place.

**Example:** Add a new commit `X` between `E` and `F`: `A → B → C → D → E → X → F → G → H → I → J`. `X` is now the 6th commit.

```sh
jj new --insert-before F_ID -m "Add missing validation"
# Make and save the new change in your editor.
jj new nikhil/feature
```

The new change is inserted before the old 6th commit, `F`. The final command returns to the updated stack tip.

## 7. Shuffle or move changes within a chain.

**Example:** Your chain is `API → UI → tests → logging`. Move the independent logging change earlier: `API → logging → UI → tests`.

Here `A_ID` is API, `C_ID` is tests, and `D_ID` is logging. Assume `nikhil/feature` initially points at `D`.

```sh
jj rebase -r D_ID --insert-after A_ID
jj bookmark set nikhil/feature -r C_ID
jj log -r 'main@origin..nikhil/feature'
```

The order becomes `A → D → B → C`. The bookmark follows the moved `D`, so explicitly move it to `C`, the new tip.

## 8. Rebase a `nikhil/feature` branch on top of `origin/main` or `origin/develop`.

**Example:** Your `nikhil/feature` branch has three search commits based on an older `origin/main`. Main now includes a bug fix. Rebase your three commits onto the latest `origin/main` so the bug fix sits underneath your work.

```sh
jj git fetch --remote origin --branch main
jj rebase -b nikhil/feature --onto main@origin
```

For `origin/develop`, replace `main` with `develop` in both commands.

## 9. Create multiple PRs from a chain of changes.

**Example:** Your chain is `A (API) → B (UI) → C (tests)`. Put `nikhil/api` at `A`, `nikhil/ui` at `B`, and `nikhil/tests` at `C`. Open three stacked PRs: `nikhil/api` into `main`, `nikhil/ui` into `nikhil/api`, and `nikhil/tests` into `nikhil/ui`, so each PR shows its own part of the chain.

First publish the three stack boundaries:

```sh
jj bookmark create nikhil/api -r API_ID
jj bookmark create nikhil/ui -r UI_ID
jj bookmark create nikhil/tests -r TESTS_ID
jj git push --remote origin \
  --bookmark nikhil/api \
  --bookmark nikhil/ui \
  --bookmark nikhil/tests
```

For GitHub, use `gh` with an already signed-in account and replace `OWNER/REPO` with the repository:

```sh
gh pr create --repo OWNER/REPO --draft \
  --base main --head nikhil/api \
  --title "Add API" --body "API layer."
gh pr create --repo OWNER/REPO --draft \
  --base nikhil/api --head nikhil/ui \
  --title "Add UI" --body "UI layer; depends on the API PR."
gh pr create --repo OWNER/REPO --draft \
  --base nikhil/ui --head nikhil/tests \
  --title "Add tests" --body "Tests; depends on the UI PR."
```

Each later PR targets the preceding branch, rather than `main`, so it shows only its part of the stack.

**Verification:** jj examples tested with version 0.47.1 in disposable repositories, including pushes to local test remotes. GitHub CLI flags were checked against installed help; no real PRs were submitted.
