# docker compose watch

Watch build context for service and rebuild/refresh containers when files are updated.

## Usage

```text
docker compose watch [SERVICE...]
```

## Options

| Option | Description |
|---|---|
| `--dry-run` | Execute command in dry run mode |
| `--no-up` | Do not build & start services before watching |
| `--prune` | Prune dangling images on rebuild (default true) |
| `--quiet` | hide build output |
