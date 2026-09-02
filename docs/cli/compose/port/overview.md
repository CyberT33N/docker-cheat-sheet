# docker compose port

Print the public port for a port binding.

## Usage

```text
docker compose port [OPTIONS] SERVICE PRIVATE_PORT
```

## Options

| Option | Description |
|---|---|
| `--dry-run` | Execute command in dry run mode |
| `--index int` | Index of the container if service has multiple replicas |
| `--protocol string` | tcp or udp (default "tcp") |
