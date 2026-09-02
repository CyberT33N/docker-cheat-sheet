# docker agent run — Hooks and Session Flags

| Option | Description |
|---|---|
| `--disable-commands strings` | Comma-separated list of slash commands to hide and disable in the TUI (e.g. /cost,/eval,/model) |
| `--env-from-file strings` | Set environment variables from file |
| `--flavor stringArray` | Enable a config flavor, a YAML patch defined under the config's 'flavors' section (repeatable, applied in order) |
| `--hide-tool-calls` | Hide the tool calls in the output |
| `--hide-tool-results` | Hide tool call results |
| `--hook-on-user-input stringArray` | Add an on-user-input hook command (repeatable) |
| `--hook-post-tool-use stringArray` | Add a post-tool-use hook command that runs after every tool call (repeatable) |
| `--hook-pre-tool-use stringArray` | Add a pre-tool-use hook command that runs before every tool call (repeatable) |
| `--hook-session-end stringArray` | Add a session-end hook command (repeatable) |
| `--hook-session-start stringArray` | Add a session-start hook command (repeatable) |
| `--hook-stop stringArray` | Add a stop hook command, fired when the model finishes responding (repeatable) |
| `--mcp-oauth-redirect-uri redirect_uri` | Public HTTPS URL to advertise as the OAuth redirect_uri for MCP servers running in unmanaged OAuth mode |
| `--no-kit` | Do not stage a docker-agent kit (skills, prompt files) when running in a sandbox |
| `--on-event stringArray` | Run shell command on event: --on-event <type>=<cmd> (or *=<cmd> for any). Repeatable. |
| `--prompt-file stringArray` | Append file contents to the prompt (repeatable) |
| `--record string[="true"]` | Record AI API interactions to cassette file and generate a TUI e2e test from the session (auto-generates filename if empty) |
| `--session string` | Continue from a previous session by ID or relative offset (e.g., -1 for last session) |
| `-s, --session-db string` | Path to the session database (default: <data-dir>/session.db) |
| `--session-read-only` | Open the session in read-only mode (view conversation history but prevent new messages) |
| `--sidebar` | Show the sidebar in the TUI (set --sidebar=false to hide it) (default true) |
