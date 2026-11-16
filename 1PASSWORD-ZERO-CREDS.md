# 1Password zero-credentials (no disk writes)

This fork runs with **zero credential files on disk**. Tokens live in
1Password and are injected at process start. Nothing is written to
`~/.config/grokbot-gateway/tokens.json` in this mode.

## Run

```bash
op run --env -- grokbot mcp
op run --env -- grokbot bots --json
```

Required env (set in 1Password, not in shell history):

- `GROKBOT_TOKENS_JSON` — full `{"version":1,"tokens":[...]}` file content.
  Create with `grokbot token create` once, store the returned secret in
  1Password, then export only the JSON shape (hashes only, never the
  `gbgt_` secret) for steady state.
- `GROKBOT_NO_DISK_TOKENS=1` — fail closed: reads return empty and any
  disk write throws instead of creating `tokens.json`.

1Password Environments mount works the same way: mount at runtime, never
commit a `.env` file. `doctor` passes with no `tokens.json` present.

## Rules

- Never paste a `gbgt_` secret in chat, logs, or argv.
- `tokens.json` must not exist on a zero-cred host — its presence means
  the lane fell back to disk.
- `verifyToken` last-used updates stay in memory only in env mode.
