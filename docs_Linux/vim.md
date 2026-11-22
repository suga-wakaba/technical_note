# `.vimrc` Sample
```
set number
set belloff=all
set tabstop=4
set nowrap
set noautoindent
set nosmartindent
set hlsearch
set list
set listchars=tab:^-,space:·

autocmd!
autocmd FileType sh,conf,c,cpp,java,python,r,html,css,javascript,php,json,markdown setlocal expandtab shiftwidth=4 softtabstop=4

syntax on
```

# **Vim Cheat Sheet**

## **1. Basic Modes**

| Mode              | Description                   | Key           |
| ----------------- | ----------------------------- | ------------- |
| Normal Mode       | Navigate and execute commands | `Esc`         |
| Insert Mode       | Insert text                   | `i`, `a`, `o` |
| Visual Mode       | Select text                   | `v`           |
| Visual Line Mode  | Select entire lines           | `V`           |
| Visual Block Mode | Select rectangular blocks     | `Ctrl + v`    |
| Command Mode      | Execute commands              | `:`           |

## **2. File Operations**

| Command            | Description                    |
| ------------------ | ------------------------------ |
| `:w`               | Save file                      |
| `:q`               | Quit                           |
| `:wq`              | Save and quit                  |
| `:q!`              | Quit without saving            |
| `:w filename`      | Save as a new file             |
| `:e filename`      | Open another file              |
| `:r filename`      | Insert another file's contents |
| `:saveas filename` | Save with a new filename       |

## **3. Navigation**

| Key        | Description                           |
| ---------- | ------------------------------------- |
| `h`        | Move left                             |
| `j`        | Move down                             |
| `k`        | Move up                               |
| `l`        | Move right                            |
| `w`        | Move to the next word                 |
| `b`        | Move to the previous word             |
| `e`        | Move to the end of the word           |
| `0`        | Move to the beginning of the line     |
| `^`        | Move to the first non-blank character |
| `$`        | Move to the end of the line           |
| `gg`       | Move to the first line                |
| `G`        | Move to the last line                 |
| `nG`       | Move to line number n                 |
| `Ctrl + d` | Scroll down half a screen             |
| `Ctrl + u` | Scroll up half a screen               |
| `H`        | Move to the top of the screen         |
| `M`        | Move to the middle of the screen      |
| `L`        | Move to the bottom of the screen      |
| `%`        | Jump to matching bracket              |

## **4. Insert and Edit Text**

| Key  | Description                          |
| ---- | ------------------------------------ |
| `i`  | Insert before the cursor             |
| `a`  | Insert after the cursor              |
| `I`  | Insert at the beginning of the line  |
| `A`  | Insert at the end of the line        |
| `o`  | Open a new line below                |
| `O`  | Open a new line above                |
| `x`  | Delete character under cursor        |
| `X`  | Delete character before cursor       |
| `dd` | Delete current line                  |
| `dw` | Delete a word                        |
| `D`  | Delete from cursor to end of line    |
| `r`  | Replace one character                |
| `R`  | Enter replace mode                   |
| `cw` | Change a word                        |
| `cc` | Change entire line                   |
| `C`  | Change from cursor to end of line    |
| `J`  | Join current line with the next line |

## **5. Copy, Cut, and Paste**

| Key   | Description                       |
| ----- | --------------------------------- |
| `yy`  | Yank (copy) current line          |
| `yw`  | Yank a word                       |
| `y$`  | Yank to end of line               |
| `dd`  | Cut current line                  |
| `dw`  | Cut a word                        |
| `p`   | Paste after cursor or below line  |
| `P`   | Paste before cursor or above line |
| `"+y` | Copy to system clipboard          |
| `"+p` | Paste from system clipboard       |

## **6. Undo and Redo**

| Key        | Description            |
| ---------- | ---------------------- |
| `u`        | Undo                   |
| `Ctrl + r` | Redo                   |
| `.`        | Repeat the last change |

## **7. Search**

| Command           | Description                             |
| ----------------- | --------------------------------------- |
| `/pattern`        | Search forward                          |
| `?pattern`        | Search backward                         |
| `n`               | Jump to next match                      |
| `N`               | Jump to previous match                  |
| `*`               | Search for word under cursor (forward)  |
| `#`               | Search for word under cursor (backward) |
| `:noh`            | Clear search highlighting               |
| `:set hlsearch`   | Enable search highlighting              |
| `:set nohlsearch` | Disable search highlighting             |

## **8. Indentation**

| Command             | Description                                 |
| ------------------- | ------------------------------------------- |
| `>>`                | Indent current line                         |
| `<<`                | Unindent current line                       |
| `n>>`               | Indent n lines                              |
| `n<<`               | Unindent n lines                            |
| `=`                 | Auto-indent selected text                   |
| `gg=G`              | Auto-indent the entire file                 |
| `==`                | Auto-indent current line                    |
| `>}`                | Indent until the end of the paragraph       |
| `<}`                | Unindent until the end of the paragraph     |
| `:set shiftwidth=4` | Set indentation width to 4 spaces           |
| `:set tabstop=4`    | Set tab display width to 4 spaces           |
| `:set expandtab`    | Convert inserted tabs to spaces             |
| `:set noexpandtab`  | Insert actual tab characters                |
| `:retab`            | Convert existing tabs according to settings |

**Example: Indent multiple lines**

1. Press `V` to enter Visual Line Mode.
2. Select the lines using `j` or `k`.
3. Press `>` to indent.
4. Press `.` to repeat the operation if needed.

## **9. Find and Replace**

| Command            | Description                                |
| ------------------ | ------------------------------------------ |
| `:s/old/new/`      | Replace first occurrence on current line   |
| `:s/old/new/g`     | Replace all occurrences on current line    |
| `:%s/old/new/g`    | Replace all occurrences in the file        |
| `:%s/old/new/gc`   | Replace all occurrences with confirmation  |
| `:5,10s/old/new/g` | Replace occurrences between lines 5 and 10 |
| `:.,$s/old/new/g`  | Replace from current line to end of file   |
| `:%s/old/new/gi`   | Replace all occurrences, ignoring case     |
| `:%s/old/new/gI`   | Replace all occurrences, case-sensitive    |

**Useful examples**

```
:%s/foo/bar/g
```

Replace every occurrence of `foo` with `bar`.

```
:%s/foo/bar/gc
```

Ask for confirmation before each replacement.

```
:%s/\<foo\>/bar/g
```

Replace only the whole word `foo`, not occurrences inside other words.

## **10. Visual Mode**

| Key        | Description                        |
| ---------- | ---------------------------------- |
| `v`        | Start character-wise selection     |
| `V`        | Start line-wise selection          |
| `Ctrl + v` | Start block-wise selection         |
| `y`        | Copy selected text                 |
| `d`        | Delete selected text               |
| `c`        | Change selected text               |
| `>`        | Indent selected text               |
| `<`        | Unindent selected text             |
| `=`        | Auto-indent selected text          |
| `U`        | Convert selected text to uppercase |
| `u`        | Convert selected text to lowercase |
| `Esc`      | Exit Visual Mode                   |

## **11. Window Management**

| Command       | Description                        |
| ------------- | ---------------------------------- |
| `:split`      | Split window horizontally          |
| `:vsplit`     | Split window vertically            |
| `:new`        | Open a new empty horizontal window |
| `:vnew`       | Open a new empty vertical window   |
| `Ctrl + w, w` | Switch to the next window          |
| `Ctrl + w, h` | Move to the left window            |
| `Ctrl + w, j` | Move to the window below           |
| `Ctrl + w, k` | Move to the window above           |
| `Ctrl + w, l` | Move to the right window           |
| `Ctrl + w, q` | Close current window               |
| `Ctrl + w, =` | Equalize window sizes              |

## **12. Useful Settings**

Add these settings to `~/.vimrc` to configure Vim.

```
" Enable syntax highlighting
syntax on

" Display line numbers
set number

" Display relative line numbers
set relativenumber

" Enable search highlighting
set hlsearch

" Ignore case in searches
set ignorecase

" Use case-sensitive search when uppercase is included
set smartcase

" Use 4 spaces for indentation
set tabstop=4
set shiftwidth=4
set softtabstop=4
set expandtab

" Enable automatic indentation
set autoindent
set smartindent

" Enable mouse support
set mouse=a

" Show matching brackets
set showmatch

" Enable file type detection and indentation
filetype plugin indent on
```

## **13. Useful Tips**

| Command         | Description                               |
| --------------- | ----------------------------------------- |
| `:set number?`  | Check whether line numbers are enabled    |
| `:set all`      | Display all options                       |
| `:help command` | Open help for a specific command          |
| `:help :s`      | Open help for substitution                |
| `:help indent`  | Open indentation documentation            |
| `:version`      | Display Vim version                       |
| `:!command`     | Execute an external shell command         |
| `:r !command`   | Insert shell command output into the file |

**Remember:** Vim commands can be combined with numbers.

For example:

| Command | Description          |
| ------- | -------------------- |
| `5j`    | Move down 5 lines    |
| `3dd`   | Delete 3 lines       |
| `10yy`  | Copy 10 lines        |
| `4w`    | Move forward 4 words |
| `2>>`   | Indent 2 lines       |

