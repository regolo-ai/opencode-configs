# OpenCode Configurations
[![License](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](http://www.gnu.org/licenses/gpl-3.0)   

Configuration files for [OpenCode](https://opencode.ai/) using the [Regolo AI](https://regolo.ai/) provider.

## What's Inside

| File | Description |
|------|-------------|
| `opencode.json` | Main OpenCode configuration with Regolo provider setup, MCP servers, and permissions |
| `oh-my-opencode.json` | Oh-My-OpenCode plugin configuration with agent model assignments and categories |

## Features

### Models Configured

- **qwen3.5-122b** - Main reasoning model
- **qwen3-coder-next** - Fast coding model (240k context)
- **mistral-small-4-119b** - Balanced model
- **minimax-m2.5** - Large context model (130k)
- **gpt-oss-120b** - Alternative reasoning model

### MCP Servers Enabled

- **context7** - Official documentation lookup
- **grep_app** - Real-world code examples search
- **websearch** (Exa) - Web search capabilities
- **sequentialthinking** - Structured reasoning
- **fetch** - URL content retrieval
- **deepwiki** - Repository knowledge extraction

### Agents (via oh-my-opencode)

| Agent | Model | Purpose |
|-------|-------|---------|
| sisyphus | minimax-m2.5 | Main orchestrator |
| oracle | qwen3.5-122b | Read-only consultation |
| librarian | qwen3.5-122b | External documentation |
| explore | qwen3-coder-next | Codebase exploration |
| prometheus | minimax-m2.5 | Planning |
| metis | mistral-small-4-119b | Pre-planning analysis |
| momus | qwen3-coder-next | Quality review |

## Setup

1. Copy configuration files to your OpenCode config directory:
   ```bash
   cp opencode.json ~/.config/opencode/
   cp oh-my-opencode.json ~/.config/opencode/
   ```

2. Set your Regolo API key:
   ```bash
   export REGOLOAI_API_KEY="your-api-key"
   ```

3. Restart OpenCode

## Recommended: Create AGENTS.md

We strongly recommend creating an `AGENTS.md` file in your project root to provide behavioral guidelines for AI coding assistants. This helps reduce common LLM mistakes and improves code quality.

### Example AGENTS.md

You can use the [Andrej Karpathy-style guidelines](https://github.com/forrestchang/andrej-karpathy-skills/blob/main/CLAUDE.md) as a starting point.

### Why AGENTS.md?

- **Consistency**: Ensures AI follows your coding standards
- **Quality**: Reduces over-engineering and unnecessary changes
- **Efficiency**: AI asks clarifying questions instead of guessing
- **Safety**: Prevents unwanted refactoring of working code

## Requirements

- [OpenCode](https://opencode.ai/) installed
- [Regolo AI](https://regolo.ai/) account and API key
- [oh-my-opencode](https://github.com/code-yeongyu/oh-my-opencode) plugin (auto-installed via config)
