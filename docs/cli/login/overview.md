# docker login

Authenticate to a registry. Defaults to Docker Hub if no server is specified.

## Usage

```text
docker login [OPTIONS] [SERVER]
```

## Options

| Option | Description |
|---|---|
| `-p, --password string` | Password or Personal Access Token (PAT), or "-" to read from stdin |
| `--password-stdin` | Take the Password or Personal Access Token (PAT) from stdin |
| `-u, --username string` | Username |

## Documented examples

Login to official docker:

```bash
docker login
```

Login to remote:

```bash
docker login urlhere
```
