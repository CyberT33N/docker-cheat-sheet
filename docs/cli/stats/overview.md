# docker stats

Display a live stream of container(s) resource usage statistics.

## Usage

```text
docker stats [OPTIONS] [CONTAINER...]
```

## Aliases

- `docker container stats`

## Options

| Option | Description |
|---|---|
| `-a, --all` | Show all containers (default shows just running) |
| `--format string` | Format output using a custom template ('table', 'json' or a Go template) |
| `--no-stream` | Disable streaming stats and only pull the first result |
| `--no-trunc` | Do not truncate output |

## Documented examples

Show hardware resources of container:

```bash
docker stats
```
