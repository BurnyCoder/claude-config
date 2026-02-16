# Claude Code Global Configuration

My global configuration for [Claude Code](https://docs.anthropic.com/en/docs/claude-code).

## Custom Commands

| Command | Description |
|---------|-------------|
| `/push` | Commit and push to GitHub |
| `/pushall` | Commit all uncommitted changes and push to GitHub |
| `/commit` | Commit all uncommitted changes (without push) |
| `/test` | Do test-driven development |
| `/web` | Append web search instruction to prompt |
| `/testweb` | Combine test-driven development with web search |
| `/debug` | Debug step by step, wait for feedback after each attempt, iterate until resolved |
| `/double` | Double check it using web search |
| `/doublecheck` | Alias for `/double` |
| `/updatereadme` | Update README.md, browse repo and web search to verify accuracy |
| `/readme` | Alias for `/updatereadme` |

## Structure

- `commands/` - Custom slash commands (`.md` files)
- `settings.json` - Global permissions and plugin settings
- `skills/` - Complex skills with SKILL.md files
