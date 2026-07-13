# Usage Examples

## Interactive REPL

```shell
codex
```
Opens the interactive terminal UI. Write prompts directly or use slash commands.

## Non-Interactive Execution

```shell
codex exec "explain this codebase"
codex exec "add unit tests for calc.sh"
codex exec "refactor main.py to use argparse"
```

## Code Review

```shell
codex review
```
Analyzes staged or unstaged changes and provides a code review.

## Resume Previous Session

```shell
codex resume
codex resume --last
```

## Slash Commands (Interactive)

| Command | Description |
|---------|-------------|
| `/status` | Session info and model config |
| `/model` | Switch the Codex model |
| `/review` | Analyze code changes |
| `/init` | Create AGENTS.md with project conventions |
| `/approvals` | Control auto-approval behavior |

## Approval Modes

```shell
codex --approval-mode suggest     # Default: propose, ask before applying
codex --approval-mode auto-edit   # Auto-apply edits, ask for shell commands
codex --approval-mode full-auto   # Fully autonomous in sandbox
```
