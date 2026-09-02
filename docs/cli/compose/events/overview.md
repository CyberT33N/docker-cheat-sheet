# docker compose events

Receive real time events from containers.

## Usage

```text
docker compose events [OPTIONS] [SERVICE...]
```

## Options

| Option | Description |
|---|---|
| `--dry-run` | Execute command in dry run mode |
| `--json` | Output events as a stream of json objects |
| `--since string` | Show all events created since timestamp |
| `--until string` | Stream events until this timestamp |
