# docker context create

Create a context.

## Usage

```text
docker context create [OPTIONS] CONTEXT
```

## Options

| Option | Description |
|---|---|
| `--description string` | Description of the context |
| `--docker stringToString` | set the docker endpoint (default []) |
| `--from string` | create context from a named context |

## Docker endpoint config

| Name | Description |
|---|---|
| `from` | Copy named context's Docker endpoint configuration |
| `host` | Docker endpoint on which to connect |
| `ca` | Trust certs signed only by this CA |
| `cert` | Path to TLS certificate file |
| `key` | Path to TLS key file |
| `skip-tls-verify` | Skip TLS certificate validation |
