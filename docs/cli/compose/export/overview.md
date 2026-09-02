# docker compose export

Export a service container's filesystem as a tar archive.

## Usage

```text
docker compose export [OPTIONS] SERVICE
```

## Options

| Option | Description |
|---|---|
| `--dry-run` | Execute command in dry run mode |
| `--index int` | index of the container if service has multiple replicas. |
| `-o, --output string` | Write to a file, instead of STDOUT |
