# docker agent new

Create a new agent configuration.

## Usage

```text
docker agent new [description]
```

## Options

| Option | Description |
|---|---|
| `--code-mode-tools` | Provide a single tool to call other tools via Javascript |
| `--env-from-file strings` | Set environment variables from file |
| `--flavor stringArray` | Enable a config flavor, a YAML patch defined under the config's 'flavors' section (repeatable, applied in order) |
| `--hook-* stringArray` | Hook commands (on-user-input, pre/post-tool-use, session-start/end, stop; repeatable) |
| `--max-iterations int` | Maximum number of agentic loop iterations to prevent infinite loops (default: 20 for DMR, unlimited for other providers) |
| `--mcp-oauth-redirect-uri redirect_uri` | Public HTTPS URL to advertise as the OAuth redirect_uri for MCP servers running in unmanaged OAuth mode |
| `--model string` | Model to use, optionally as provider/model (anthropic, openai, google, dmr, or a custom provider from docker agent setup) |
| `--models-gateway string` | Set the models gateway address |
| `--working-dir string` | Set the working directory for the session (applies to tools and relative paths) |

Plus the [global flags](../overview.md).
