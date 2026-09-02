# docker buildx inspect

Inspect current builder instance.

## Usage

```text
docker buildx inspect [NAME]
```

## Options

| Option | Description |
|---|---|
| `--bootstrap` | Ensure builder has booted before inspecting |
| `--builder string` | Override the configured builder instance |
| `-D, --debug` | Enable debug logging |
| `--timeout duration` | Override the default timeout for loading builder status (default 20s) |
