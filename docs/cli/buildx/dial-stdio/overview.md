# docker buildx dial-stdio

Proxy current stdio streams to builder instance.

## Usage

```text
docker buildx dial-stdio
```

## Options

| Option | Description |
|---|---|
| `--builder string` | Override the configured builder instance |
| `-D, --debug` | Enable debug logging |
| `--platform string` | Target platform: this is used for node selection |
| `--progress string` | Set type of progress output ("auto", "plain", "rawjson", "tty"). Use plain to show container output (default "none") |
