# claude-skill-notepad

A [Claude Code](https://claude.ai/claude-code) skill that opens a `notepad.md` file in a vertical iTerm2 split for your current project — instantly, without leaving your workflow.

![claude-skill-notepad screenshot](screenshot.png)

## What it does

Type `/notepad` in Claude Code and it will:

1. Create `notepad.md` in your project folder (first time only) with a ready-to-use template
2. Split your iTerm2 window vertically
3. Open the file in your editor of choice on the right pane

Next time you type `/notepad`, it just opens the existing file.

## Setup (one time)

### 1. Make sure you're using iTerm2
This skill only works inside [iTerm2](https://iterm2.com/). If you're using a different terminal, it won't work.

### 2. Enable the iTerm2 Python API
Open iTerm2 and go to:
> Preferences → General → Magic → ✅ Enable Python API

### 3. Install the it2 CLI
```bash
pip install it2
```

### 4. Install the skills
```bash
# nano version (default)
git clone https://github.com/crfgxr/claude-skill-notepad.git ~/.claude/skills/notepad

# vim version (optional)
cp -r ~/.claude/skills/notepad/notepad-vim ~/.claude/skills/notepad-vim
```

### 5. Restart Claude Code
Start a new Claude Code session. That's it.

## Usage

```
/notepad        # opens with nano (beginner-friendly)
/notepad-vim    # opens with vim
```

To switch between panes: **⌘[** / **⌘]** or **⌘⌥←** / **⌘⌥→**

## Template

On first run, `notepad.md` is created with:

```markdown
# Notepad

## Goal
## Tasks
## Notes
## Blockers
## Links
```

## License

MIT
