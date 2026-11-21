# Bash

## Prompt Appearance
```
PS1='\[\e[1;36m\]\u@\h\[\e[0m\]:\[\e[1;35m\]\w\[\e[0m\]\$ '
PS1='\[\e[38;5;208m\]\u@\h\[\e[0m\] \[\e[38;5;39m\]\W\[\e[0m\]\$ '
```

## Keyboard Shortcuts Cheat Sheet (Linux)
### 1. Cursor Movement

| Shortcut   | Description                              |
| ---------- | ---------------------------------------- |
| `Ctrl + A` | Move cursor to the beginning of the line |
| `Ctrl + E` | Move cursor to the end of the line       |
| `Ctrl + F` | Move cursor one character forward        |
| `Ctrl + B` | Move cursor one character backward       |
| `Alt + F`  | Move cursor one word forward             |
| `Alt + B`  | Move cursor one word backward            |

### 2. Editing Commands

| Shortcut   | Description                                            |
| ---------- | ------------------------------------------------------ |
| `Ctrl + U` | Delete from cursor to the beginning of the line        |
| `Ctrl + K` | Delete from cursor to the end of the line              |
| `Ctrl + W` | Delete the word before the cursor                      |
| `Alt + D`  | Delete the word after the cursor                       |
| `Ctrl + D` | Delete the character under the cursor                  |
| `Ctrl + H` | Delete the character before the cursor                 |
| `Ctrl + T` | Swap the current character with the previous character |
| `Alt + T`  | Swap the current word with the previous word           |
| `Ctrl + Y` | Paste the most recently deleted text                   |
| `Alt + U`  | Convert the current word to uppercase                  |
| `Alt + L`  | Convert the current word to lowercase                  |
| `Alt + C`  | Capitalize the current word                            |

### 3. Command History

| Shortcut   | Description                                                   |
| ---------- | ------------------------------------------------------------- |
| `Ctrl + P` | Move to the previous command in history                       |
| `Ctrl + N` | Move to the next command in history                           |
| `Ctrl + R` | Search command history backward                               |
| `Ctrl + S` | Search command history forward                                |
| `Ctrl + G` | Cancel history search                                         |
| `Ctrl + O` | Execute the selected history command and display the next one |
| `Alt + .`  | Insert the last argument of the previous command              |
| `Ctrl + L` | Clear the terminal screen                                     |

### 4. Process and Terminal Control

| Shortcut   | Description                                                     |
| ---------- | --------------------------------------------------------------- |
| `Ctrl + C` | Interrupt the currently running command                         |
| `Ctrl + Z` | Suspend the currently running process                           |
| `Ctrl + D` | Send EOF (End Of File); exits Bash if the command line is empty |
| `Ctrl + S` | Pause terminal output (XOFF)                                    |
| `Ctrl + Q` | Resume terminal output (XON)                                    |
| `Ctrl + \` | Send SIGQUIT to the foreground process                          |

### 5. Auto-completion and Miscellaneous

| Shortcut                    | Description                                               |
| --------------------------- | --------------------------------------------------------- |
| `Tab`                       | Complete commands, filenames, and paths                   |
| `Tab + Tab`                 | Display available completion candidates (press Tab twice) |
| `Alt + ?`                   | Display possible completions                              |
| `Alt + *`                   | Insert all possible completions                           |
| `Ctrl + X`, then `Ctrl + E` | Open the current command line in the default editor       |
| `Esc`, then `.`             | Insert the last argument of the previous command          |

### 6. Most Important Shortcuts to Memorize

| Shortcut   | Description                 |
| ---------- | --------------------------- |
| `Ctrl + A` | Beginning of line           |
| `Ctrl + E` | End of line                 |
| `Ctrl + U` | Delete to beginning of line |
| `Ctrl + K` | Delete to end of line       |
| `Ctrl + W` | Delete previous word        |
| `Ctrl + R` | Search command history      |
| `Ctrl + C` | Interrupt command           |
| `Ctrl + L` | Clear screen                |
| `Ctrl + Z` | Suspend process             |
| `Tab`      | Auto-completion             |

