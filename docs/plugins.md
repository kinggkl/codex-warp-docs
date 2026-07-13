# Plugin Internals

## warp Plugin

Location: `~/.codex/plugins/cache/codex-warp/warp/`

| Hook | Script |
|------|--------|
| `SessionStart` | `scripts/on-session-start.sh` |
| `UserPromptSubmit` | `scripts/on-prompt-submit.sh` |
| `PostToolUse` | `scripts/on-post-tool-use.sh` |
| `PermissionRequest` | `scripts/on-permission-request.sh` |
| `Stop` | `scripts/on-stop.sh` |

Helper: `scripts/warp-notify.sh` — sends structured notifications to Warp.

## orchestration Plugin

Location: `~/.codex/plugins/cache/codex-warp/orchestration/`

| Hook | Purpose |
|------|---------|
| `SessionStart` | Initialize parent-message listener |
| `UserPromptSubmit` | Stage parent messages |
| `PostToolUse` | Deliver staged messages |
| `Stop` | Block until all messages drained |
| `SessionEnd` | Cleanup state directory |

Skills: Oz orchestration skills located in `skills/` directory.

## State Directory

Runtime state stored at `~/.codex/state/<session-id>/`:

- `listener.pid` — Oz parent listener process ID
- `staged/` — Queued parent messages
- `surfaced/` — Messages awaiting delivery
- `delivered.log` — Delivered message log
