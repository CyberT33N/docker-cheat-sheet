# docker mcp profile config

Update the configuration of a profile.

## Usage

```text
docker mcp profile config <profile-id> [--set <key>=<value> ...] [--get <key> ...] [--del <key> ...]
```

## Options

| Option | Description |
|---|---|
| `--del stringArray` | Delete configuration values: `<key>` (can be specified multiple times) |
| `--format string` | Supported: json, yaml, human. (default "human") |
| `--get stringArray` | Get configuration values: `<key>` (can be specified multiple times) |
| `--get-all` | Get all configuration values |
| `--set stringArray` | Set configuration values: `<key>=<value>` (repeatable). Value may be JSON to set typed values (arrays, numbers, booleans, objects). |
