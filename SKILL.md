---
name: notepad
description: Opens a notepad.md notepad in a vertical iTerm2 split for the current project. Supports nano (default) and vim editors.
version: 1.4.0
---

# Notepad

Open a vertical split in iTerm2 and launch an editor with the `notepad.md` file for the current project directory. If `notepad.md` does not exist, create it with a default template first.

## Editor Selection

- `/notepad` → opens with **nano** (default)
- `/notepad vim` → opens with **vim**

Check if the user specified an editor in their message. If they wrote `vim`, use vim. Otherwise default to nano.

## Steps

1. Run `pwd` via Bash to get the current project directory. Store it as `$PROJECT_DIR`.
2. Determine the editor: use `vim` if the user specified it, otherwise use `nano`.
3. Run the following bash command to create `notepad.md` with the template if it does not exist:
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
4. Delete any stale swap file: `rm -f "$PROJECT_DIR/.notepad.md.swp"`
5. Run: `it2 session split --vertical`
6. Capture the new pane ID from the output.
7. Run: `it2 session run -s <pane-id> "<editor> $PROJECT_DIR/notepad.md"` — replace `<editor>` with `nano` or `vim` based on step 2.

Use the Bash tool for all commands sequentially.
