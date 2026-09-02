# docker network ls

List networks.

## Usage

```text
docker network ls [OPTIONS]
```

## Aliases

- `docker network list`

## Options

| Option | Description |
|---|---|
| `-f, --filter filter` | Provide filter values (e.g. "driver=bridge") |
| `--format string` | Format output using a custom template ('table', 'json' or a Go template) |
| `--no-trunc` | Do not truncate the output |
| `-q, --quiet` | Only display network IDs |

## Documented examples

Show all networks:

```bash
sudo docker network ls
```
