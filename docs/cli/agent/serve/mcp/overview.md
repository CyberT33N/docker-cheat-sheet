# docker agent serve mcp

Start an agent as an MCP (Model Context Protocol) server.

## Usage

```text
docker agent serve mcp <agent-file>|<registry-ref>
```

## Options

| Option | Description |
|---|---|
| `-a, --agent string` | Name of the agent to run (all agents if not specified) |
| `--attach string[="latest"]` | Attach to a running TUI run by pid, address, or session id (or empty for the most recent) |
| `--code-mode-tools` | Provide a single tool to call other tools via Javascript |
| `--http` | Use streaming HTTP transport instead of stdio |
| `-l, --listen string` | Address to listen on (default "127.0.0.1:8081") |
| `--mcp-keepalive duration` | Interval between MCP keep-alive pings (e.g. 30s); 0 disables keep-alive |
| `--mcp-oauth-redirect-uri redirect_uri` | Public HTTPS URL to advertise as the OAuth redirect_uri for MCP servers running in unmanaged OAuth mode |
| `--models-gateway string` | Set the models gateway address |
| `--tool-name string` | Override the MCP tool identifier clients call (defaults to agent name); only valid when exposing a single agent |
| `--working-dir string` | Set the working directory for the session |

Plus the [global flags](../../../overview.md) and hook/flavor options.
