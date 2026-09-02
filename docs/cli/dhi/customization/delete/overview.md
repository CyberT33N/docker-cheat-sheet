# docker dhi customization delete

Delete one or more Docker Hardened Images customizations by their IDs. Multiple IDs can be specified as positional arguments.

## Usage

```text
docker dhi customization delete <id> [id...]
```

## Options

| Option | Description |
|---|---|
| `-f, --force` | Skip the confirmation prompt; aborts if any ID does not exist |
| `--org string` | Docker Hub organization (overrides config) |
