# docker ps

List containers.

## Usage

```text
docker ps [OPTIONS]
```

## Aliases

- `docker container ls`
- `docker container list`
- `docker container ps`

## Options

| Option | Description |
|---|---|
| `-a, --all` | Show all containers (default shows just running) |
| `-f, --filter filter` | Filter output based on conditions provided |
| `--format string` | Format output using a custom template ('table', 'json' or a Go template) |
| `-n, --last int` | Show n last created containers (includes all states) (default -1) |
| `-l, --latest` | Show the latest created container (includes all states) |
| `--no-trunc` | Don't truncate output |
| `-q, --quiet` | Only display container IDs |
| `-s, --size` | Display total file sizes |

## Documented examples

Show running Container:

```bash
# -a or -all means show all containers (default shows just running)
docker ps -a
```
