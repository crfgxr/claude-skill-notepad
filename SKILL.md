---
name: notepad
description: Opens a notepad.md notepad in a vertical iTerm2 split for the current project.
version: 1.0.0
---

# Notepad

Open a vertical split in iTerm2 and launch vim with the `notepad.md` file for the current project directory.

## Steps

1. Run `pwd` via Bash to get the current project directory. Store it as `$PROJECT_DIR`.
2. Run: `it2 session split --vertical`
3. Capture the new pane ID from the output.
4. Delete any stale swap file: `rm -f "$PROJECT_DIR/.notepad.md.swp"`
5. Run: `it2 session send -s <pane-id> "vim +startinsert $PROJECT_DIR/notepad.md"` — the `+startinsert` flag opens vim directly in insert mode. Send the command text, then send a newline separately.

Use the Bash tool for all commands sequentially.
