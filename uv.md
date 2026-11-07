# uv Cheatsheet

For uv 0.13.7. Run project commands from the project folder. uv manages `.venv` for you; `uv run` needs no manual activation.

## Start

Choose one template. Omit the directory name to initialize the current folder; it must not already contain a `pyproject.toml`.

| Goal | Command | Creates |
| --- | --- | --- |
| Packaged application (default) | `uv init my-app` | `src/my_app/`, a build system, and a `my-app` command |
| Simple scripts folder | `uv init --no-package my-app` | `main.py`, with no build system |
| Minimal setup in the current folder | `uv init --bare` | Only `pyproject.toml`; no source files, Python pin, or Git initialization |

`--no-package` still creates a README and `.python-version`. Plain `--bare` also omits the build system. Packaging enables imports and command entry points; it does not publish anything.

```sh
uv init --no-package demo
cd demo
uv add requests
uv run main.py
```

For the default packaged template, run `uv run my-app` inside `my-app/` instead.

## Dependencies and running

| Goal | Command |
| --- | --- |
| Add a runtime dependency | `uv add requests` |
| Add development tools | `uv add --dev pytest ruff` |
| Remove a runtime dependency | `uv remove requests` |
| Remove a development dependency | `uv remove --dev pytest` |
| Run a Python file | `uv run script.py` |
| Run project tests | `uv run pytest` |
| Run the project's linter | `uv run ruff check .` |

`add` / `remove` update `pyproject.toml`, `uv.lock`, and the environment. The `dev` group is included by default. `uv run` updates the lockfile and environment as needed before running the command.

## Lock and sync

| Goal | Command |
| --- | --- |
| Create or update `.venv` for the project | `uv sync` |
| Sync without changing the lockfile; fail if outdated or missing | `uv sync --locked` |
| Create or update `uv.lock` without syncing `.venv` | `uv lock` |
| Check that the lockfile matches the project | `uv lock --check` |
| Upgrade one package within allowed versions | `uv lock --upgrade-package requests` |
| Upgrade all packages within allowed versions | `uv lock --upgrade` |

After `uv lock`, run `uv sync` to apply changes. Ordinary syncs keep compatible locked versions. `--frozen` skips the freshness check, unlike `--locked`.

`uv sync` removes packages outside the selected project dependencies. Use `uv add` for project dependencies; `uv pip install` does not record them in `pyproject.toml` or `uv.lock`.

Commit `pyproject.toml`, `uv.lock`, and `.python-version` if present. Keep `.venv/` ignored.

## Python and standalone tools

| Goal | Command |
| --- | --- |
| Pin this project's Python version | `uv python pin 3.12` |
| See the Python used by the project | `uv run python --version` |
| Run a tool outside the project environment | `uvx ruff check .` |

Choose a Python version allowed by `requires-python` in `pyproject.toml`; pinning does not change that constraint. uv can download a missing interpreter automatically.

`uvx` is an alias for `uv tool run`: it uses an isolated tool environment, not your project's dependencies or locked tool version. Use `uv run pytest` for project tests and `uv run ruff check .` for the project's pinned Ruff.

Reference: [uv 0.13.7 project templates](https://github.com/astral-sh/uv/blob/0.13.7/docs/concepts/projects/init.md) · [locking and syncing](https://github.com/astral-sh/uv/blob/0.13.7/docs/concepts/projects/sync.md) · [tools](https://github.com/astral-sh/uv/blob/0.13.7/docs/guides/tools.md)
