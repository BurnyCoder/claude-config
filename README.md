# Claude Code Global Configuration

My global configuration for [Claude Code](https://docs.anthropic.com/en/docs/claude-code).

## Custom Commands

### Git & Workflow

| Command | Description |
|---------|-------------|
| `/push` | Commit and push to GitHub |
| `/pushall` | Commit all uncommitted changes and push to GitHub |
| `/commit` | Commit all uncommitted changes (without push) |

### Development

| Command | Description |
|---------|-------------|
| `/test` | Test-driven development |
| `/testweb` | Test-driven development with web search |
| `/debug` | Debug step by step, wait for feedback after each attempt, iterate until resolved |
| `/web` | Search the web for how to do the task |
| `/double` | Double check using web search |
| `/doublecheck` | Alias for `/double` |
| `/venvai` | Activate venv and use `uv add` for packages |
| `/threejs` | Download Three.js skills from GitHub |

### README & CLAUDE.md Updates

Systematic 3x2x2 matrix: {target} x {scope} x {verification}.

| Command | Target | Full Codebase | Web Verify |
|---------|--------|:---:|:---:|
| `/readme` | README.md | Yes | No |
| `/claudemd` | CLAUDE.md | Yes | No |
| `/readmeclaudemd` | Both | Yes | No |
| `/readmeweb` | README.md | Yes | Yes |
| `/claudemdweb` | CLAUDE.md | Yes | Yes |
| `/readmeclaudemdweb` | Both | Yes | Yes |
| `/readmepart` | README.md | No | No |
| `/claudemdpart` | CLAUDE.md | No | No |
| `/readmeclaudemdpart` | Both | No | No |
| `/readmewebpart` | README.md | No | Yes |
| `/claudemdwebpart` | CLAUDE.md | No | Yes |
| `/readmeclaudemdwebpart` | Both | No | Yes |

## Enabled Plugins

### Official Plugins
- `pyright-lsp` - Python type checking
- `typescript-lsp` - TypeScript language server
- `github` - GitHub integration
- `playwright` - Browser automation
- `commit-commands` - Git commit workflows
- `agent-sdk-dev` - Agent SDK development
- `huggingface-skills` - Hugging Face ecosystem
- `claude-md-management` - CLAUDE.md management
- `claude-code-setup` - Claude Code setup tools
- `greptile` - Code search
- `ralph-loop` - Recurring task loops

### AI Research Skills (`orchestra-research/AI-research-SKILLs`)
- agents, data-processing, distributed-training, emerging-techniques, evaluation, fine-tuning, inference-serving, infrastructure, mechanistic-interpretability, ml-paper-writing, mlops, model-architecture, multimodal, observability, optimization, post-training, prompt-engineering, rag, safety-alignment, tokenization

## Structure

- `commands/` - Custom slash commands (`.md` files)
- `settings.json` - Global permissions and plugin settings
- `skills/` - Complex skills with SKILL.md files (e.g., `skill-creator`)
- `plugins/` - Plugin configuration and cache
- `CLAUDE.md` - Global instructions for all projects
