# docker version

Show the Docker version information.

## Usage

```text
docker version [OPTIONS]
```

## Options

| Option | Description |
|---|---|
| `-f, --format string` | Format output using a custom template ('json' or a Go template) |

## Documented examples

```bash
docker version
```

Scriptable client/server proof via Go template:

```bash
docker version --format "client={{.Client.Version}} server={{.Server.Version}}"
```

The template form reduces the output to the two versions that matter for compatibility proofs — one line, directly comparable in scripts and read-backs.
