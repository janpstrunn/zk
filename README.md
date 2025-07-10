# Journal Notes (jn)

`jn` is an opinionated journaling tool designed to help you keep daily, weekly, monthly, and yearly notes directly from your terminal. With the assistance of template notes, `jn` ensures your notes remain consistent and organized.

## Features

- **Add Journal Notes:**
  - Daily Notes
  - Weekly Notes
  - Monthly Notes
  - Yearly Notes
- **Search:** Utilize `fzf` for searching through your notes. Empower your search using `rg`
- **Add Normal Notes:** Create standalone notes
- **Multiple Workspaces:** Aggregate different notes into different directories (workspaces)
- **List Notes:** List all notes or workspaces

## Requirements

- `fzf`

## Installation

To install `jn`, follow these steps:

```bash
git clone https://github.com/janpstrunn/jn
cd jn && mv src/jn \$HOME/.local/bin
chmod +x \$HOME/.local/bin/jn
```

## Usage

```
jn | Journal Notes

Usage:
  jn FLAG <FLAG_INPUT> COMMAND INPUT
  jn -h | jn help

Commands:
  add FILENAME WORKSPACE       Add new note
  fzf WORKSPACE                Search all files with fzf
  journal DATE WORKSPACE       Add new journal entry
  list                         List all files
  rg WORKSPACE                 Search with fzf and rg

Flags:
  -h            Displays this message and exits
  --help       Displays this message and exits
  -n            Do not edit the note after creation
  -w            Search workspaces
```

### Examples

List all files or workspaces:

```bash
jn # Lists all files
jn -w # Lists all workspaces
jn list
jn -w list
```

Add a journal note:

```bash
jn journal day # Creates a Daily Note and interactively selects a workspace with fzf
jn journal week # Creates a Weekly Note
jn journal month # Creates a Monthly Note
jn journal year # Creates a Yearly Note
jn -n journal day # Creates a Daily Note without editing the file after creation
jn journal day journal/daily # Creates a Daily Note in the specified workspace
```

Add normal notes:

```bash
jn add mynote # Adds a note 'mynote.md' and interactively selects a workspace with fzf
jn add mynote notes # Adds a note 'mynote.md' in the 'notes/' directory
```

## Notes

This script has been tested exclusively on a Linux machine.

## License

This repository is licensed under the MIT License, allowing for extensive use, modification, copying, and distribution.
