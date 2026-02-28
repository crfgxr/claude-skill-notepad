# claude-skill-notepad

A [Claude Code](https://claude.ai/claude-code) skill that opens a `notepad.md` notepad in a vertical iTerm2 split for your current project — instantly, without leaving your workflow.

## What it does

When you type `/notepad`, Claude Code will:

1. Split your iTerm2 window vertically
2. Open `notepad.md` in the new pane using vim (in insert mode, ready to type)

The file is always opened in your **current project directory**, so it works across any project.

## Requirements

- [Claude Code](https://claude.ai/claude-code) CLI
- [iTerm2](https://iterm2.com/)
- **iTerm2 Shell Integration** — provides the `it2` command required for splitting panes (`iTerm2 menu → Install Shell Integration`)

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
