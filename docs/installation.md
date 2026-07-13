# Installation

## Prerequisites

- Linux (Debian/Ubuntu) or macOS
- `jq` installed (`sudo apt install jq` on Debian)

## Install Codex CLI

```shell
curl -fsSL https://chatgpt.com/codex/install.sh | sh
source ~/.bashrc
codex --version
```

## Add Warp Marketplace & Plugins

```shell
codex plugin marketplace add warpdotdev/codex-warp
codex plugin add warp@codex-warp
codex plugin add orchestration@codex-warp
```

## Verify

```shell
codex plugin list
codex doctor
bash ~/.codex/.tmp/marketplaces/codex-warp/tests/test-hooks.sh
```
