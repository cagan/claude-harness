# Claude Harness

Generic Claude Code development harness — TDD pipeline, subagents, quality gates, and deploy workflow.

Works with **any language/framework** via a single `project.conf` configuration file.

## What's Included

| Component | Description |
|-----------|-------------|
| **5 Subagents** | planner, architect, tdd-guide, code-reviewer, deployer |
| **6 Skills** | init, implement-feature, deploy-pipeline, tdd, refactor-clean, codemap-update |
| **3 Hooks** | pre-commit quality gate, post-write lint hints, session auto-save |
| **Templates** | project.conf and CLAUDE.md templates for new projects |

## Install

```bash
# Add marketplace
/plugin marketplace add cagan/claude-harness

# Install plugin
/plugin install claude-harness@claude-harness
```

## Setup a New Project

After installing, run in your project:

```
/claude-harness:init
```

This interactively creates:
- `.claude/project.conf` — all project-specific variables
- `CLAUDE.md` — agent instructions
- `rules/` — coding, testing, and git workflow standards

## How It Works

All agents, skills, and hooks read from `.claude/project.conf`. To adapt the harness to a new project, you only change that one file.

### project.conf Example

```bash
PROJECT_NAME="my-app"
PROJECT_LANG="typescript"
PROJECT_FRAMEWORK="nextjs"

CMD_TEST="npm test"
CMD_LINT="npm run lint"
CMD_TYPECHECK="npx tsc --noEmit"

DIR_SRC="src/"
FILE_EXT_SOURCE="ts,tsx"

MAX_FUNCTION_LINES=30
MAX_FILE_LINES=150
NO_CONSOLE_LOG=true
MAIN_BRANCH="main"
```

## Feature Development Pipeline

```
/claude-harness:implement-feature
```

Runs the full TDD pipeline:

```
@planner → @architect → @tdd-guide → implement → @code-reviewer → deploy
```

Each step uses `project.conf` for language-specific commands and conventions.

## Available Commands

| Command | Description |
|---------|-------------|
| `/claude-harness:init` | Setup harness in a new project |
| `/claude-harness:implement-feature` | Full TDD feature pipeline |
| `/claude-harness:deploy-pipeline` | Commit → push → PR (with approval) |
| `/claude-harness:tdd` | Red → Green → Refactor cycle |
| `/claude-harness:refactor-clean` | Dead code & cleanup |
| `/claude-harness:codemap-update` | Update codebase map |

## Supported Stacks

Tested with:
- TypeScript / React Native (Expo)
- TypeScript / Next.js
- Python / Django
- Go / Gin
- Any stack configurable via `project.conf`

## License

MIT
