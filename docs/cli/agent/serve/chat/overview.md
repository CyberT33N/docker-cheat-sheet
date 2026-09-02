# docker agent serve chat

Start an agent as an OpenAI-compatible chat completions server.

## Usage

```text
docker agent serve chat <agent-file>|<registry-ref>
```

## Options

| Option | Description |
|---|---|
| `-a, --agent string` | Name of the agent to expose (all agents if not specified) |
| `--api-key string` | Required Bearer token clients must present (Authorization: Bearer <token>); empty disables auth |
| `--api-key-env string` | Read the API key from this environment variable instead of the command line |
| `--code-mode-tools` | Provide a single tool to call other tools via Javascript |
| `--conversation-ttl duration` | Idle TTL after which a cached conversation is evicted (default 30m0s) |
| `--conversations-max int` | Cache up to N conversations server-side, keyed by X-Conversation-Id (0 disables; clients must resend full history) |
| `--cors-origin string` | Allowed CORS origin (e.g. https://example.com); empty disables CORS entirely |
| `-l, --listen string` | Address to listen on (default "127.0.0.1:8083") |
| `--max-idle-runtimes int` | Maximum number of idle runtimes pooled per agent (0 disables pooling) (default 4) |
| `--max-request-size int` | Maximum request body size in bytes (default 1 MiB) (default 1048576) |
| `--request-timeout duration` | Per-request timeout (covers model + tool calls + streaming) (default 5m0s) |
| `--working-dir string` | Set the working directory for the session |

Plus the [global flags](../../../overview.md) and hook/flavor options.
