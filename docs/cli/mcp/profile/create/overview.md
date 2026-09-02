# docker mcp profile create

Create a new profile of MCP servers.

## Usage

```text
docker mcp profile create [--name <name>] [--id <id>] [--server <ref> ...] [--from-template <template-id>] [--connect <client> ...]
```

## Options

| Option | Description |
|---|---|
| `--connect stringArray` | Clients to connect to: mcp-client (can be specified multiple times). Supported clients: claude-code, claude-desktop, cline, codex, continue, crush, cursor, gemini, goose, gordon, kiro, lmstudio, opencode, sema4, vscode, zed |
| `--from-template string` | Create profile from a starter template (use `docker mcp template list` to see options) |
| `--id string` | ID of the profile (defaults to a slugified version of the name) |
| `--name string` | Name of the profile (required unless --from-template is used) |
| `--server stringArray` | Server to include specified with a URI: https:// (MCP Registry reference) or docker:// (Docker Image reference) or catalog:// (Catalog reference) or file:// (Local file path). Can be specified multiple times. |
