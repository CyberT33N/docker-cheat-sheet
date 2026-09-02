# docker compose stats

Display a live stream of container(s) resource usage statistics.

## Usage

```text
docker compose stats [OPTIONS] [SERVICE]
```

## Options

| Option | Description |
|---|---|
| `-a, --all` | Show all containers (default shows just running) |
| `--dry-run` | Execute command in dry run mode |
| `--format string` | Format output using a custom template ('table', 'json' or a Go template) |
| `--no-stream` | Disable streaming stats and only pull the first result |
| `--no-trunc` | Do not truncate output |
