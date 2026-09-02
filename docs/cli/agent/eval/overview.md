# docker agent eval

Run evaluations for an agent.

## Usage

```text
docker agent eval <agent-file>|<registry-ref> [<eval-dir>|./evals]
```

## Options

| Option | Description |
|---|---|
| `--base-image string` | Custom base image for running evaluations |
| `--code-mode-tools` | Provide a single tool to call other tools via Javascript |
| `-c, --concurrency int` | Number of concurrent evaluation runs (default 32) |
| `--container-runtime string` | Container runtime executable for building and running evaluations (default "docker") |
| `-e, --env strings` | Environment variables to pass to container (KEY or KEY=VALUE) |
| `--env-from-file strings` | Set environment variables from file |
| `--flavor stringArray` | Enable a config flavor, a YAML patch defined under the config's 'flavors' section (repeatable, applied in order) |
| `--hook-* stringArray` | Hook commands (on-user-input, pre/post-tool-use, session-start/end, stop; repeatable) |
| `--judge-model string` | Model to use for relevance checking (format: provider/model) (default "anthropic/claude-opus-5") |
| `--keep-containers` | Keep containers after evaluation (don't use --rm) |
| `--mcp-oauth-redirect-uri redirect_uri` | Public HTTPS URL to advertise as the OAuth redirect_uri for MCP servers running in unmanaged OAuth mode |
| `--models-gateway string` | Set the models gateway address |
| `--only strings` | Only run evaluations with file names matching these patterns (can be specified multiple times) |
| `--output string` | Directory for results and logs (default: <eval-dir>/results) |
| `--repeat int` | Number of times to repeat each evaluation (useful for computing baselines) (default 1) |
| `--working-dir string` | Set the working directory for the session (applies to tools and relative paths) |

Plus the [global flags](../overview.md).
