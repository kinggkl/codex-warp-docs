# Codex + Warp Plugin Integration Guide

Steps to integrate Codex CLI with Warp plugins on a Debian Linux system.

## Prerequisites

- Debian Linux (or any Linux/macOS)
- `jq` (apt: `sudo apt install jq`)

## 1. Install Codex CLI

```shell
curl -fsSL https://chatgpt.com/codex/install.sh | sh
source ~/.bashrc
codex --version
```

This installs the standalone Rust binary (no Node.js required).

## 2. Add the Warp Plugin Marketplace

```shell
codex plugin marketplace add warpdotdev/codex-warp
```

## 3. Install the Plugins

```shell
codex plugin add warp@codex-warp           # Warp notification hooks
codex plugin add orchestration@codex-warp  # Oz orchestration + parent-message delivery
```

## 4. Verify

```shell
codex plugin list                          # Confirm installed & enabled
codex doctor                               # Health check (17 ok, 0 fail)
bash ~/.codex/.tmp/marketplaces/codex-warp/tests/test-hooks.sh  # 43 tests
```

## 5. Use

```shell
codex                     # Interactive REPL
codex exec "your prompt"  # Non-interactive execution
```

## Plugin Details

| Plugin | Version | Hooks |
|--------|---------|-------|
| `warp` | 0.4.0 | SessionStart, UserPromptSubmit, PostToolUse, PermissionRequest, Stop |
| `orchestration` | 0.4.0 | SessionStart, UserPromptSubmit, PostToolUse, Stop, SessionEnd + Oz skills |

## Environment

- **OS**: Debian 13 (Trixie)
- **Codex CLI**: v0.144.3
- **Shell**: Bash 5.2.37
- **jq**: 1.7
