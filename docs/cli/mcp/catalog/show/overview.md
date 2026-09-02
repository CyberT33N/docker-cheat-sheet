# docker mcp catalog show

Show a catalog.

## Usage

```text
docker mcp catalog show <oci-reference> [--pull <pull-option>]
```

## Options

| Option | Description |
|---|---|
| `--format string` | Supported: json, yaml, human. (default "human") |
| `--no-tools` | Exclude tools from output (deprecated, use --yq instead) |
| `--pull string` | Supported: missing, never, always, initial, exists, or duration (e.g. '1h', '1d'). Duration represents time since last update. (default "never") |
| `--yq string` | YQ expression to apply to the output |
