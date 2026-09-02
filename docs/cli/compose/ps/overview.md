# docker compose ps

List containers.

## Usage

```text
docker compose ps [OPTIONS] [SERVICE...]
```

## Options

| Option | Description |
|---|---|
| `-a, --all` | Show all stopped containers (including those created by the run command) |
| `--dry-run` | Execute command in dry run mode |
| `--filter string` | Filter services by a property (supported filters: status) |
| `--format string` | Format output using a custom template ('table', 'json' or a Go template) (default "table") |
| `--no-trunc` | Don't truncate output |
| `--orphans` | Include orphaned services (not declared by project) (default true) |
| `-q, --quiet` | Only display IDs |
| `--services` | Display services |
| `--status stringArray` | Filter services by status. Values: [paused \| restarting \| removing \| running \| dead \| created \| exited] |

## Documented examples

List all running containers:

```bash
sudo docker-compose ps
```
