# Neovim in VS Code — Beginner Cheatsheet

Move, select, and edit with Neovim while keeping VS Code's editor features.

> **Lost? Press `Esc`.** Then `i` to type, `u` to undo, or `:w` followed by `Enter` to save.

This guide assumes the **VSCode Neovim** extension (`asvetliakov.vscode-neovim`) and default mappings. VSCodeVim is a different extension. Custom mappings may change these keys.

## Start here: your first ten commands

| Do this | Keys |
| --- | --- |
| Return to Normal mode | `Esc` |
| Start typing | `i` |
| Move left / down / up / right | `h` / `j` / `k` / `l` |
| Find text | `/text` then `Enter` |
| Change the word under the cursor | `ciw`, type replacement, `Esc` |
| Select whole lines | `V`, then `j` or `k` |
| Copy selected text | `y` |
| Delete selected text | `d` |
| Paste after the cursor or below the line | `p` |
| Save | `:w` then `Enter` |

## How to read the keys

- `ciw` means press `c`, then `i`, then `w`; do not hold them together.
- `Ctrl+r` means hold `Ctrl` and press `r`.
- Uppercase matters: `v` and `V` do different things. Use `Shift+v` for `V`.
- Start in **Normal mode** unless a row says otherwise. Press `Esc` first if unsure.
- Commands beginning with `:` and searches beginning with `/` or `?` need `Enter`.
- Counts repeat actions: `5j` moves down five lines; `3dd` deletes three lines.

## 1. Modes: move, type, select, command

| Mode | Purpose | Enter it |
| --- | --- | --- |
| Normal | Navigate and run editing commands | `Esc` |
| Insert | Type normally | `i`, `a`, `o`, and the variants below |
| Visual | Select characters | `v` |
| Visual Line | Select complete lines | `V` |
| Visual Block | Select a rectangle | `Ctrl+v` if routed to Neovim |
| Command-line | Save or run an Ex command | `:` |

`Esc` leaves Insert or Visual mode and cancels a pending command. Check the mode indicator if letters unexpectedly edit or move the cursor.

| Begin typing… | Keys |
| --- | --- |
| Before cursor / after cursor | `i` / `a` |
| At first nonblank character / end of line | `I` / `A` |
| On a new line below / above | `o` / `O` |

## 2. Navigation

| Destination | Keys |
| --- | --- |
| Left / down / up / right | `h` / `j` / `k` / `l` |
| Next word start / previous word start | `w` / `b` |
| End of word | `e` |
| Next / previous whitespace-separated WORD | `W` / `B` |
| Start of current line (column 1, including indentation) | `0` (zero) |
| First nonblank character of current line (skip indentation) | `^` |
| End of current line (last character) | `# Neovim in VS Code — Beginner Cheatsheet

Move, select, and edit with Neovim while keeping VS Code's editor features.

> **Lost? Press `Esc`.** Then `i` to type, `u` to undo, or `:w` followed by `Enter` to save.

This guide assumes the **VSCode Neovim** extension (`asvetliakov.vscode-neovim`) and default mappings. VSCodeVim is a different extension. Custom mappings may change these keys.

## Start here: your first ten commands

| Do this | Keys |
| --- | --- |
| Return to Normal mode | `Esc` |
| Start typing | `i` |
| Move left / down / up / right | `h` / `j` / `k` / `l` |
| Find text | `/text` then `Enter` |
| Change the word under the cursor | `ciw`, type replacement, `Esc` |
| Select whole lines | `V`, then `j` or `k` |
| Copy selected text | `y` |
| Delete selected text | `d` |
| Paste after the cursor or below the line | `p` |
| Save | `:w` then `Enter` |

## How to read the keys

- `ciw` means press `c`, then `i`, then `w`; do not hold them together.
- `Ctrl+r` means hold `Ctrl` and press `r`.
- Uppercase matters: `v` and `V` do different things. Use `Shift+v` for `V`.
- Start in **Normal mode** unless a row says otherwise. Press `Esc` first if unsure.
- Commands beginning with `:` and searches beginning with `/` or `?` need `Enter`.
- Counts repeat actions: `5j` moves down five lines; `3dd` deletes three lines.

## 1. Modes: move, type, select, command

| Mode | Purpose | Enter it |
| --- | --- | --- |
| Normal | Navigate and run editing commands | `Esc` |
| Insert | Type normally | `i`, `a`, `o`, and the variants below |
| Visual | Select characters | `v` |
| Visual Line | Select complete lines | `V` |
| Visual Block | Select a rectangle | `Ctrl+v` if routed to Neovim |
| Command-line | Save or run an Ex command | `:` |

`Esc` leaves Insert or Visual mode and cancels a pending command. Check the mode indicator if letters unexpectedly edit or move the cursor.

| Begin typing… | Keys |
| --- | --- |
| Before cursor / after cursor | `i` / `a` |
| At first nonblank character / end of line | `I` / `A` |
| On a new line below / above | `o` / `O` |

## 2. Navigation

| Destination | Keys |
| --- | --- |
| Left / down / up / right | `h` / `j` / `k` / `l` |
| Next word start / previous word start | `w` / `b` |
| End of word | `e` |
| Next / previous whitespace-separated WORD | `W` / `B` |
 |
| Start of file (first line) | `gg` |
| End of file (last line) | `G` |
| Line 42 | `42G` or `:42` then `Enter` |
| Next / previous paragraph boundary | `}` / `{` |
| Matching bracket | `%` |
| Next `x` on this line / just before it | `fx` / `tx` |
| Previous `x` on this line / just after it | `Fx` / `Tx` |
| Repeat character find / reverse it | `;` / `,` |
| Roughly half a screen down / up | `Ctrl+d` / `Ctrl+u` |
| Center cursor line on screen | `zz` |
| Previous jump / forward again | `Ctrl+o` / `Ctrl+i` |

**Line navigation:** press `Esc`, then `0` to jump to the beginning of the current line or `# Neovim in VS Code — Beginner Cheatsheet

Move, select, and edit with Neovim while keeping VS Code's editor features.

> **Lost? Press `Esc`.** Then `i` to type, `u` to undo, or `:w` followed by `Enter` to save.

This guide assumes the **VSCode Neovim** extension (`asvetliakov.vscode-neovim`) and default mappings. VSCodeVim is a different extension. Custom mappings may change these keys.

## Start here: your first ten commands

| Do this | Keys |
| --- | --- |
| Return to Normal mode | `Esc` |
| Start typing | `i` |
| Move left / down / up / right | `h` / `j` / `k` / `l` |
| Find text | `/text` then `Enter` |
| Change the word under the cursor | `ciw`, type replacement, `Esc` |
| Select whole lines | `V`, then `j` or `k` |
| Copy selected text | `y` |
| Delete selected text | `d` |
| Paste after the cursor or below the line | `p` |
| Save | `:w` then `Enter` |

## How to read the keys

- `ciw` means press `c`, then `i`, then `w`; do not hold them together.
- `Ctrl+r` means hold `Ctrl` and press `r`.
- Uppercase matters: `v` and `V` do different things. Use `Shift+v` for `V`.
- Start in **Normal mode** unless a row says otherwise. Press `Esc` first if unsure.
- Commands beginning with `:` and searches beginning with `/` or `?` need `Enter`.
- Counts repeat actions: `5j` moves down five lines; `3dd` deletes three lines.

## 1. Modes: move, type, select, command

| Mode | Purpose | Enter it |
| --- | --- | --- |
| Normal | Navigate and run editing commands | `Esc` |
| Insert | Type normally | `i`, `a`, `o`, and the variants below |
| Visual | Select characters | `v` |
| Visual Line | Select complete lines | `V` |
| Visual Block | Select a rectangle | `Ctrl+v` if routed to Neovim |
| Command-line | Save or run an Ex command | `:` |

`Esc` leaves Insert or Visual mode and cancels a pending command. Check the mode indicator if letters unexpectedly edit or move the cursor.

| Begin typing… | Keys |
| --- | --- |
| Before cursor / after cursor | `i` / `a` |
| At first nonblank character / end of line | `I` / `A` |
| On a new line below / above | `o` / `O` |

## 2. Navigation

| Destination | Keys |
| --- | --- |
| Left / down / up / right | `h` / `j` / `k` / `l` |
| Next word start / previous word start | `w` / `b` |
| End of word | `e` |
| Next / previous whitespace-separated WORD | `W` / `B` |
| Start of current line (column 1, including indentation) | `0` (zero) |
| First nonblank character of current line (skip indentation) | `^` |
| End of current line (last character) | `# Neovim in VS Code — Beginner Cheatsheet

Move, select, and edit with Neovim while keeping VS Code's editor features.

> **Lost? Press `Esc`.** Then `i` to type, `u` to undo, or `:w` followed by `Enter` to save.

This guide assumes the **VSCode Neovim** extension (`asvetliakov.vscode-neovim`) and default mappings. VSCodeVim is a different extension. Custom mappings may change these keys.

## Start here: your first ten commands

| Do this | Keys |
| --- | --- |
| Return to Normal mode | `Esc` |
| Start typing | `i` |
| Move left / down / up / right | `h` / `j` / `k` / `l` |
| Find text | `/text` then `Enter` |
| Change the word under the cursor | `ciw`, type replacement, `Esc` |
| Select whole lines | `V`, then `j` or `k` |
| Copy selected text | `y` |
| Delete selected text | `d` |
| Paste after the cursor or below the line | `p` |
| Save | `:w` then `Enter` |

## How to read the keys

- `ciw` means press `c`, then `i`, then `w`; do not hold them together.
- `Ctrl+r` means hold `Ctrl` and press `r`.
- Uppercase matters: `v` and `V` do different things. Use `Shift+v` for `V`.
- Start in **Normal mode** unless a row says otherwise. Press `Esc` first if unsure.
- Commands beginning with `:` and searches beginning with `/` or `?` need `Enter`.
- Counts repeat actions: `5j` moves down five lines; `3dd` deletes three lines.

## 1. Modes: move, type, select, command

| Mode | Purpose | Enter it |
| --- | --- | --- |
| Normal | Navigate and run editing commands | `Esc` |
| Insert | Type normally | `i`, `a`, `o`, and the variants below |
| Visual | Select characters | `v` |
| Visual Line | Select complete lines | `V` |
| Visual Block | Select a rectangle | `Ctrl+v` if routed to Neovim |
| Command-line | Save or run an Ex command | `:` |

`Esc` leaves Insert or Visual mode and cancels a pending command. Check the mode indicator if letters unexpectedly edit or move the cursor.

| Begin typing… | Keys |
| --- | --- |
| Before cursor / after cursor | `i` / `a` |
| At first nonblank character / end of line | `I` / `A` |
| On a new line below / above | `o` / `O` |

## 2. Navigation

| Destination | Keys |
| --- | --- |
| Left / down / up / right | `h` / `j` / `k` / `l` |
| Next word start / previous word start | `w` / `b` |
| End of word | `e` |
| Next / previous whitespace-separated WORD | `W` / `B` |
 |
| Start of file (first line) | `gg` |
| End of file (last line) | `G` |
| Line 42 | `42G` or `:42` then `Enter` |
| Next / previous paragraph boundary | `}` / `{` |
| Matching bracket | `%` |
| Next `x` on this line / just before it | `fx` / `tx` |
| Previous `x` on this line / just after it | `Fx` / `Tx` |
| Repeat character find / reverse it | `;` / `,` |
| Roughly half a screen down / up | `Ctrl+d` / `Ctrl+u` |
| Center cursor line on screen | `zz` |
| Previous jump / forward again | `Ctrl+o` / `Ctrl+i` |

 to jump to its end. Use `^` to skip indentation. `0` is the digit zero; on a US keyboard, `^` is `Shift+6` and `# Neovim in VS Code — Beginner Cheatsheet

Move, select, and edit with Neovim while keeping VS Code's editor features.

> **Lost? Press `Esc`.** Then `i` to type, `u` to undo, or `:w` followed by `Enter` to save.

This guide assumes the **VSCode Neovim** extension (`asvetliakov.vscode-neovim`) and default mappings. VSCodeVim is a different extension. Custom mappings may change these keys.

## Start here: your first ten commands

| Do this | Keys |
| --- | --- |
| Return to Normal mode | `Esc` |
| Start typing | `i` |
| Move left / down / up / right | `h` / `j` / `k` / `l` |
| Find text | `/text` then `Enter` |
| Change the word under the cursor | `ciw`, type replacement, `Esc` |
| Select whole lines | `V`, then `j` or `k` |
| Copy selected text | `y` |
| Delete selected text | `d` |
| Paste after the cursor or below the line | `p` |
| Save | `:w` then `Enter` |

## How to read the keys

- `ciw` means press `c`, then `i`, then `w`; do not hold them together.
- `Ctrl+r` means hold `Ctrl` and press `r`.
- Uppercase matters: `v` and `V` do different things. Use `Shift+v` for `V`.
- Start in **Normal mode** unless a row says otherwise. Press `Esc` first if unsure.
- Commands beginning with `:` and searches beginning with `/` or `?` need `Enter`.
- Counts repeat actions: `5j` moves down five lines; `3dd` deletes three lines.

## 1. Modes: move, type, select, command

| Mode | Purpose | Enter it |
| --- | --- | --- |
| Normal | Navigate and run editing commands | `Esc` |
| Insert | Type normally | `i`, `a`, `o`, and the variants below |
| Visual | Select characters | `v` |
| Visual Line | Select complete lines | `V` |
| Visual Block | Select a rectangle | `Ctrl+v` if routed to Neovim |
| Command-line | Save or run an Ex command | `:` |

`Esc` leaves Insert or Visual mode and cancels a pending command. Check the mode indicator if letters unexpectedly edit or move the cursor.

| Begin typing… | Keys |
| --- | --- |
| Before cursor / after cursor | `i` / `a` |
| At first nonblank character / end of line | `I` / `A` |
| On a new line below / above | `o` / `O` |

## 2. Navigation

| Destination | Keys |
| --- | --- |
| Left / down / up / right | `h` / `j` / `k` / `l` |
| Next word start / previous word start | `w` / `b` |
| End of word | `e` |
| Next / previous whitespace-separated WORD | `W` / `B` |
| Start of current line (column 1, including indentation) | `0` (zero) |
| First nonblank character of current line (skip indentation) | `^` |
| End of current line (last character) | `# Neovim in VS Code — Beginner Cheatsheet

Move, select, and edit with Neovim while keeping VS Code's editor features.

> **Lost? Press `Esc`.** Then `i` to type, `u` to undo, or `:w` followed by `Enter` to save.

This guide assumes the **VSCode Neovim** extension (`asvetliakov.vscode-neovim`) and default mappings. VSCodeVim is a different extension. Custom mappings may change these keys.

## Start here: your first ten commands

| Do this | Keys |
| --- | --- |
| Return to Normal mode | `Esc` |
| Start typing | `i` |
| Move left / down / up / right | `h` / `j` / `k` / `l` |
| Find text | `/text` then `Enter` |
| Change the word under the cursor | `ciw`, type replacement, `Esc` |
| Select whole lines | `V`, then `j` or `k` |
| Copy selected text | `y` |
| Delete selected text | `d` |
| Paste after the cursor or below the line | `p` |
| Save | `:w` then `Enter` |

## How to read the keys

- `ciw` means press `c`, then `i`, then `w`; do not hold them together.
- `Ctrl+r` means hold `Ctrl` and press `r`.
- Uppercase matters: `v` and `V` do different things. Use `Shift+v` for `V`.
- Start in **Normal mode** unless a row says otherwise. Press `Esc` first if unsure.
- Commands beginning with `:` and searches beginning with `/` or `?` need `Enter`.
- Counts repeat actions: `5j` moves down five lines; `3dd` deletes three lines.

## 1. Modes: move, type, select, command

| Mode | Purpose | Enter it |
| --- | --- | --- |
| Normal | Navigate and run editing commands | `Esc` |
| Insert | Type normally | `i`, `a`, `o`, and the variants below |
| Visual | Select characters | `v` |
| Visual Line | Select complete lines | `V` |
| Visual Block | Select a rectangle | `Ctrl+v` if routed to Neovim |
| Command-line | Save or run an Ex command | `:` |

`Esc` leaves Insert or Visual mode and cancels a pending command. Check the mode indicator if letters unexpectedly edit or move the cursor.

| Begin typing… | Keys |
| --- | --- |
| Before cursor / after cursor | `i` / `a` |
| At first nonblank character / end of line | `I` / `A` |
| On a new line below / above | `o` / `O` |

## 2. Navigation

| Destination | Keys |
| --- | --- |
| Left / down / up / right | `h` / `j` / `k` / `l` |
| Next word start / previous word start | `w` / `b` |
| End of word | `e` |
| Next / previous whitespace-separated WORD | `W` / `B` |
 |
| Start of file (first line) | `gg` |
| End of file (last line) | `G` |
| Line 42 | `42G` or `:42` then `Enter` |
| Next / previous paragraph boundary | `}` / `{` |
| Matching bracket | `%` |
| Next `x` on this line / just before it | `fx` / `tx` |
| Previous `x` on this line / just after it | `Fx` / `Tx` |
| Repeat character find / reverse it | `;` / `,` |
| Roughly half a screen down / up | `Ctrl+d` / `Ctrl+u` |
| Center cursor line on screen | `zz` |
| Previous jump / forward again | `Ctrl+o` / `Ctrl+i` |

 is `Shift+4`.

**Move and start typing:** `I` enters Insert mode at the first nonblank character; `A` enters Insert mode after the end of the line. Use `0i` to type before indentation.

**File navigation:** `gg` goes to the first line and `G` to the last line. Use `gg0` or `G# Neovim in VS Code — Beginner Cheatsheet

Move, select, and edit with Neovim while keeping VS Code's editor features.

> **Lost? Press `Esc`.** Then `i` to type, `u` to undo, or `:w` followed by `Enter` to save.

This guide assumes the **VSCode Neovim** extension (`asvetliakov.vscode-neovim`) and default mappings. VSCodeVim is a different extension. Custom mappings may change these keys.

## Start here: your first ten commands

| Do this | Keys |
| --- | --- |
| Return to Normal mode | `Esc` |
| Start typing | `i` |
| Move left / down / up / right | `h` / `j` / `k` / `l` |
| Find text | `/text` then `Enter` |
| Change the word under the cursor | `ciw`, type replacement, `Esc` |
| Select whole lines | `V`, then `j` or `k` |
| Copy selected text | `y` |
| Delete selected text | `d` |
| Paste after the cursor or below the line | `p` |
| Save | `:w` then `Enter` |

## How to read the keys

- `ciw` means press `c`, then `i`, then `w`; do not hold them together.
- `Ctrl+r` means hold `Ctrl` and press `r`.
- Uppercase matters: `v` and `V` do different things. Use `Shift+v` for `V`.
- Start in **Normal mode** unless a row says otherwise. Press `Esc` first if unsure.
- Commands beginning with `:` and searches beginning with `/` or `?` need `Enter`.
- Counts repeat actions: `5j` moves down five lines; `3dd` deletes three lines.

## 1. Modes: move, type, select, command

| Mode | Purpose | Enter it |
| --- | --- | --- |
| Normal | Navigate and run editing commands | `Esc` |
| Insert | Type normally | `i`, `a`, `o`, and the variants below |
| Visual | Select characters | `v` |
| Visual Line | Select complete lines | `V` |
| Visual Block | Select a rectangle | `Ctrl+v` if routed to Neovim |
| Command-line | Save or run an Ex command | `:` |

`Esc` leaves Insert or Visual mode and cancels a pending command. Check the mode indicator if letters unexpectedly edit or move the cursor.

| Begin typing… | Keys |
| --- | --- |
| Before cursor / after cursor | `i` / `a` |
| At first nonblank character / end of line | `I` / `A` |
| On a new line below / above | `o` / `O` |

## 2. Navigation

| Destination | Keys |
| --- | --- |
| Left / down / up / right | `h` / `j` / `k` / `l` |
| Next word start / previous word start | `w` / `b` |
| End of word | `e` |
| Next / previous whitespace-separated WORD | `W` / `B` |
| Start of current line (column 1, including indentation) | `0` (zero) |
| First nonblank character of current line (skip indentation) | `^` |
| End of current line (last character) | `# Neovim in VS Code — Beginner Cheatsheet

Move, select, and edit with Neovim while keeping VS Code's editor features.

> **Lost? Press `Esc`.** Then `i` to type, `u` to undo, or `:w` followed by `Enter` to save.

This guide assumes the **VSCode Neovim** extension (`asvetliakov.vscode-neovim`) and default mappings. VSCodeVim is a different extension. Custom mappings may change these keys.

## Start here: your first ten commands

| Do this | Keys |
| --- | --- |
| Return to Normal mode | `Esc` |
| Start typing | `i` |
| Move left / down / up / right | `h` / `j` / `k` / `l` |
| Find text | `/text` then `Enter` |
| Change the word under the cursor | `ciw`, type replacement, `Esc` |
| Select whole lines | `V`, then `j` or `k` |
| Copy selected text | `y` |
| Delete selected text | `d` |
| Paste after the cursor or below the line | `p` |
| Save | `:w` then `Enter` |

## How to read the keys

- `ciw` means press `c`, then `i`, then `w`; do not hold them together.
- `Ctrl+r` means hold `Ctrl` and press `r`.
- Uppercase matters: `v` and `V` do different things. Use `Shift+v` for `V`.
- Start in **Normal mode** unless a row says otherwise. Press `Esc` first if unsure.
- Commands beginning with `:` and searches beginning with `/` or `?` need `Enter`.
- Counts repeat actions: `5j` moves down five lines; `3dd` deletes three lines.

## 1. Modes: move, type, select, command

| Mode | Purpose | Enter it |
| --- | --- | --- |
| Normal | Navigate and run editing commands | `Esc` |
| Insert | Type normally | `i`, `a`, `o`, and the variants below |
| Visual | Select characters | `v` |
| Visual Line | Select complete lines | `V` |
| Visual Block | Select a rectangle | `Ctrl+v` if routed to Neovim |
| Command-line | Save or run an Ex command | `:` |

`Esc` leaves Insert or Visual mode and cancels a pending command. Check the mode indicator if letters unexpectedly edit or move the cursor.

| Begin typing… | Keys |
| --- | --- |
| Before cursor / after cursor | `i` / `a` |
| At first nonblank character / end of line | `I` / `A` |
| On a new line below / above | `o` / `O` |

## 2. Navigation

| Destination | Keys |
| --- | --- |
| Left / down / up / right | `h` / `j` / `k` / `l` |
| Next word start / previous word start | `w` / `b` |
| End of word | `e` |
| Next / previous whitespace-separated WORD | `W` / `B` |
 |
| Start of file (first line) | `gg` |
| End of file (last line) | `G` |
| Line 42 | `42G` or `:42` then `Enter` |
| Next / previous paragraph boundary | `}` / `{` |
| Matching bracket | `%` |
| Next `x` on this line / just before it | `fx` / `tx` |
| Previous `x` on this line / just after it | `Fx` / `Tx` |
| Repeat character find / reverse it | `;` / `,` |
| Roughly half a screen down / up | `Ctrl+d` / `Ctrl+u` |
| Center cursor line on screen | `zz` |
| Previous jump / forward again | `Ctrl+o` / `Ctrl+i` |

 for the very first or very last character.

Lowercase `w` treats punctuation as boundaries; uppercase `W` groups everything between spaces. With wrapped lines, `gj` and `gk` move by displayed line.

## 3. Search and replace

| Action | Keys |
| --- | --- |
| Search forward / backward | `/text` / `?text`, then `Enter` |
| Next match in search direction / opposite direction | `n` / `N` |
| Search word under cursor forward / backward | `*` / `#` |
| Clear search highlighting | `:noh` then `Enter` |
| Replace every whole-word match, confirming each | `:%s/\<old\>/new/gc` then `Enter` |

Searches use regular expressions. To search punctuation literally, start with `\V`, for example `/\Vfoo.bar` then `Enter`.

In the replacement command, `%` means the whole file, `g` means every match on each line, and `c` asks for confirmation. Answer `y` to replace, `n` to skip, or `q` to stop. Start with a single edit while learning.

### Example: change `dlpack` to `from_dlpack` near the top

1. Press `Esc`, then `gg` to go to the top.
2. Type `/\<dlpack\>` and press `Enter`.
3. Use `n` or `N` until the intended occurrence is under the cursor. Search can wrap around the file.
4. Press `ciw`, type `from_dlpack`, then press `Esc`.
5. Save with `:w` then `Enter`.

For a nearby match, repeat the search with `n`, verify the target, then press `.` to repeat the change.

## 4. Editing, copying, and undo

| Action | Keys |
| --- | --- |
| Delete character under cursor | `x` |
| Replace one character with `z` | `rz` |
| Delete current line / three lines | `dd` / `3dd` |
| Copy current line / three lines | `yy` / `3yy` |
| Delete to end of line | `D` or `d$` |
| Change to end of line | `C` or `c$`, type, `Esc` |
| Replace line contents | `cc`, type, `Esc` |
| Paste after / before cursor | `p` / `P` |
| Join current line with next | `J` |
| Undo / redo | `u` / `Ctrl+r` |
| Repeat last change | `.` |

**Yank means copy.** Delete normally also stores the removed text in a register, like a cut operation. With whole-line text, `p` pastes below and `P` pastes above. With character text, they paste after or before the cursor.

Use `"_dd` to delete a line without replacing your usual yank/delete register. Vim registers and the system clipboard are distinct; see the VS Code notes below.

## 5. Select several lines and act on them

Start on the first line, press `V`, then move with `j` or `k`. The starting line is already selected: **`V2j` selects three lines**.

| With a selection active… | Keys |
| --- | --- |
| Copy / delete (cut) | `y` / `d` |
| Replace selected text | `c`, type replacement, `Esc` |
| Indent / unindent | `>` / `<` |
| Format selection through VS Code | `=` |
| Swap cursor to other end | `o` |
| Cancel selection | `Esc` |
| Reselect the last Visual region, from Normal mode | `gv` |

### Useful recipes

| Goal | Sequence from Normal mode |
| --- | --- |
| Copy three lines | `V2jy`, or simply `3yy` |
| Cut three lines, then move them | `V2jd`, navigate to destination, `p` |
| Duplicate current line below itself | `yyp` |
| Select from here through end of file | `VG` |
| Select the whole file | `ggVG` |
| Indent three lines | `V2j>` |
| Indent that region again | `gv>` |
| Delete lines 10 through 15 | `:10,15d` then `Enter` |
| Copy lines 10 through 15 | `:10,15y` then `Enter` |

After `y` or `d`, you return to Normal mode. When replacing several selected lines, `c` replaces the selection as one region; it does not create one cursor per line.

### Rectangular edits

For aligned columns, press `Ctrl+v`, extend the rectangle with motions, then use `y` or `d`. To insert the same prefix on each selected row, press `I`, type it, and press `Esc`; Neovim applies it to the block's rows. Begin with a simple aligned block in a scratch file. VS Code's native multiple-cursor editing is another option; it has different selection behavior.

## 6. Text objects: edit a meaningful chunk

Read a command as **action + target**: `d` deletes, `c` changes, `y` copies, and `v` selects. Inside a text object, `i` means **inner**, not Insert mode. `a` usually includes the surrounding delimiter or whitespace.

| Target | Select | Change | Delete | Copy |
| --- | --- | --- | --- | --- |
| Inner word | `viw` | `ciw` | `diw` | `yiw` |
| A word, with adjacent whitespace | `vaw` | `caw` | `daw` | `yaw` |
| Inside double quotes | `vi"` | `ci"` | `di"` | `yi"` |
| Inside single quotes | `vi'` | `ci'` | `di'` | `yi'` |
| Inside parentheses | `vi(` | `ci(` | `di(` | `yi(` |
| Inside square brackets | `vi[` | `ci[` | `di[` | `yi[` |
| Inside braces | `vi{` | `ci{` | `di{` | `yi{` |
| Inner paragraph | `vip` | `cip` | `dip` | `yip` |

Place the cursor inside the intended object. For `"hello world"`, `ci"` replaces the contents while preserving the quotes; `ca"` replaces the quoted object including the quotes. After a change command, type the replacement and press `Esc`.

You can also combine actions with motions: `dw` deletes toward the next word start, `d$` deletes through line end, and `yG` copies through the final line. Text objects such as `ciw` are convenient when the cursor is in the middle of a word.

## 7. Save and close

| Action | Keys from Normal mode |
| --- | --- |
| Save current file | `:w` then `Enter` |
| Save all | `:wa` then `Enter` |
| Save and close current editor | `:wq` then `Enter` |
| Close current editor | `:q` then `Enter` |

For an untitled file, use VS Code's **File → Save As** and choose a path. On Windows/Linux, `Ctrl+s` is also the usual VS Code save shortcut; on macOS, `Cmd+s`. Closing and unsaved-change prompts follow the extension's integration with VS Code. Use explicit Save or Don't Save choices when prompted.

## 8. VS Code-specific caveats

- **Insert mode uses VS Code's editor.** Completion, snippets, and ordinary typing stay familiar; some terminal Neovim Insert mappings behave differently.
- **Ctrl shortcuts can conflict.** `Ctrl+v` may paste instead of starting a block; `Ctrl+r` and `Ctrl+i` may also be intercepted. Check Keyboard Shortcuts and the extension's control-key passthrough settings.
- **Clipboard:** try `"+y` on a selection or `"+yy` on a line to copy to the system clipboard; `"+p` pastes it. Availability depends on clipboard integration. Use VS Code's Copy/Paste menu when unsure.
- **Files, tabs, and windows belong to VS Code.** Commands such as `:q` and `:vsplit` are integrated with its editor actions. Do not assume terminal Neovim quit or force-quit behavior.
- **Formatting and display are integrated.** `=` uses VS Code formatting; a formatter must be available. Scrolling, wrapping, and line-number settings are controlled by VS Code. Dot-repeat can differ for complex Insert-mode edits.
- **VSCodeVim and VSCode Neovim are separate extensions.** Avoid enabling both for the same editor. Terminal UI plugins and full Neovim configurations may need adjustment.

For integration details, consult the [VSCode Neovim documentation](https://github.com/vscode-neovim/vscode-neovim#readme).

## 9. A two-minute practice loop

Paste this into a scratch file:

```python
from example import dlpack
message = "hello world"
first = 1
second = 2
third = 3
```

1. Find `dlpack`, change it with `ciw`, and press `Esc`.
2. Move inside the quotes; use `ci"`, type a new message, then `Esc`.
3. Move to `first`; use `V2jy` to copy the three assignments.
4. Press `G`, then `p` to paste them below the last line.
5. Try `u`, then `Ctrl+r`, to undo and redo the paste.
6. Save with `:w` then `Enter` if you want to keep the practice file.

Learn a few commands at a time. `Esc`, `i`, motions, `ciw`, `V`, `y`, `d`, `p`, `u`, and `:w` already cover a lot of daily editing.

## References

- [Neovim quick reference](https://neovim.io/doc/user/quickref/)
- [First steps and modes](https://neovim.io/doc/user/usr_02/)
- [Moving around](https://neovim.io/doc/user/usr_03/)
- [Making small changes and Visual mode](https://neovim.io/doc/user/usr_04/)
- [Making larger changes and text objects](https://neovim.io/doc/user/usr_10/)
- [VSCode Neovim integration and keybindings](https://github.com/vscode-neovim/vscode-neovim#readme)

*Compiled from the visible topics in the “Exit Insert Mode” conversation and expanded to cover the requested beginner workflow. The archived assistant replies were reference placeholders, so this is a reconstructed guide rather than an exact transcript.*
