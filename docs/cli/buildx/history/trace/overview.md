# docker buildx history trace

Show the OpenTelemetry trace of a build record.

## Usage

```text
docker buildx history trace [OPTIONS] [REF]
```

## Options

| Option | Description |
|---|---|
| `--addr string` | Address to bind the UI server (default "127.0.0.1:0") |
| `--builder string` | Override the configured builder instance |
| `--compare string` | Compare with another build record |
| `-D, --debug` | Enable debug logging |
