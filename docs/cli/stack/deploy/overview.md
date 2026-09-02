# docker stack deploy

Deploy a new stack or update an existing stack.

## Usage

```text
docker stack deploy [OPTIONS] STACK
```

## Aliases

- `docker stack up`

## Options

| Option | Description |
|---|---|
| `-c, --compose-file strings` | Path to a Compose file, or "-" to read from stdin |
| `-d, --detach` | Exit immediately instead of waiting for the stack services to converge (default true) |
| `--prune` | Prune services that are no longer referenced |
| `-q, --quiet` | Suppress progress output |
| `--resolve-image string` | Query the registry to resolve image digest and supported platforms ("always", "changed", "never") (default "always") |
| `--with-registry-auth` | Send registry authentication details to Swarm agents |
