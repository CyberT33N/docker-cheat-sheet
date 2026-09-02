# docker volume create

Create a volume.

## Usage

```text
docker volume create [OPTIONS] [VOLUME]
```

## Options

| Option | Description |
|---|---|
| `-d, --driver string` | Specify volume driver name (default "local") |
| `--label list` | Set metadata for a volume |
| `-o, --opt map` | Set driver specific options (default map[]) |

## Documented examples

Create named volume:

```bash
docker volume create todo-db
```
