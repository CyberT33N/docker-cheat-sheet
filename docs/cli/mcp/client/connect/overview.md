# docker mcp client connect

Connect the Docker MCP Toolkit to a client. Supported clients: claude-code, claude-desktop, cline, codex, continue, crush, cursor, gemini, goose, gordon, kiro, lmstudio, opencode, sema4, vscode, zed.

## Usage

```text
docker mcp client connect [OPTIONS] <mcp-client>
```

## Options

| Option | Description |
|---|---|
| `-g, --global` | Change the system wide configuration or the clients setup in your current git repo. |
| `-p, --profile string` | Profile to use for client connection. |
| `-q, --quiet` | Only display errors. |
