---
name: notepad
description: Opens a notepad.md notepad in a vertical iTerm2 split for the current project.
version: 1.3.0
---

# Notepad

Open a vertical split in iTerm2 and launch vim with the `notepad.md` file for the current project directory. If `notepad.md` does not exist, create it with a default template first.

## Steps

1. Run `pwd` via Bash to get the current project directory. Store it as `$PROJECT_DIR`.
2. Run the following bash command to create `notepad.md` with the template if it does not exist:
   ```bash
   [ ! -f "$PROJECT_DIR/notepad.md" ] && cat > "$PROJECT_DIR/notepad.md" << 'EOF'
   # Notepad

   ## Goal
   <!-- What are we trying to achieve? -->

   ## Tasks
   - [ ]

   ## Notes

   ## Blockers

   ## Links
   EOF
   ```
3. Delete any stale swap file: `rm -f "$PROJECT_DIR/.notepad.md.swp"`
4. Run: `it2 session split --vertical`
5. Capture the new pane ID from the output.
6. Run: `it2 session run -s <pane-id> "vim $PROJECT_DIR/notepad.md"` — `run` sends the command and executes it automatically (no need to send a separate newline).

Use the Bash tool for all commands sequentially.
