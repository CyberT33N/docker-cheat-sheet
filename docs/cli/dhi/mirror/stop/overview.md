# docker dhi mirror stop

Stop mirroring one or more Docker Hardened Image repositories. Multiple repositories can be specified as positional arguments.

## Usage

```text
docker dhi mirror stop <repository> [repository...]
```

## Options

| Option | Description |
|---|---|
| `--delete` | Delete the repositories after stopping mirroring |
| `-f, --force` | Skip confirmation prompt when deleting repositories |
| `--org string` | Docker Hub organization (overrides config) |
