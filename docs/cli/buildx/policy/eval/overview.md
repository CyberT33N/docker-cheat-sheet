# docker buildx policy eval

Evaluate policy for a source.

## Usage

```text
docker buildx policy eval [OPTIONS] source
```

## Options

| Option | Description |
|---|---|
| `--builder string` | Override the configured builder instance |
| `-D, --debug` | Enable debug logging |
| `--fields strings` | Fields to evaluate |
| `-f, --file string` | Policy filename to evaluate (default "Dockerfile") |
| `--platform string` | Target platform for policy evaluation |
| `--print` | Print policy output |
