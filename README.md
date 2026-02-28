# claude-skill-notepad

A [Claude Code](https://claude.ai/claude-code) skill that opens a `notepad.md` notepad in a vertical iTerm2 split for your current project — instantly, without leaving your workflow.

## What it does

When you type `/notepad`, Claude Code will:

1. Split your iTerm2 window vertically
2. Open `notepad.md` in the new pane using vim (in insert mode, ready to type)

The file is always opened in your **current project directory**, so it works across any project.

## Requirements

- [Claude Code](https://claude.ai/claude-code) CLI — must be run from within an iTerm2 terminal
- [iTerm2](https://iterm2.com/)
- **it2 CLI** (`pip install it2`) — Python CLI for controlling iTerm2
- **iTerm2 Python API enabled** — `iTerm2 → Preferences → General → Magic → Enable Python API`

## Install

```bash
git clone https://github.com/crfgxr/claude-skill-notepad.git ~/.claude/skills/notepad
```

That's it. Restart Claude Code (or start a new session) and type `/notepad`.

## Usage

```
/notepad
```

Claude will split your iTerm2 window and open `notepad.md` for your current project in vim.

To switch between panes use **⌘[** / **⌘]** or **⌘⌥←** / **⌘⌥→**.

## License

MIT
