# docker compose commit

Create a new image from a service container's changes.

## Usage

```text
docker compose commit [OPTIONS] SERVICE [REPOSITORY[:TAG]]
```

## Options

| Option | Description |
|---|---|
| `-a, --author string` | Author (e.g., "John Hannibal Smith <hannibal@a-team.com>") |
| `-c, --change list` | Apply Dockerfile instruction to the created image |
| `--dry-run` | Execute command in dry run mode |
| `--index int` | index of the container if service has multiple replicas. |
| `-m, --message string` | Commit message |
| `-p, --pause` | Pause container during commit (default true) |
