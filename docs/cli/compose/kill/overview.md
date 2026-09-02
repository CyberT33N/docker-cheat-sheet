# docker compose kill

Force stop service containers.

## Usage

```text
docker compose kill [OPTIONS] [SERVICE...]
```

## Options

| Option | Description |
|---|---|
| `--dry-run` | Execute command in dry run mode |
| `--remove-orphans` | Remove containers for services not defined in the Compose file |
| `-s, --signal string` | SIGNAL to send to the container (default "SIGKILL") |
