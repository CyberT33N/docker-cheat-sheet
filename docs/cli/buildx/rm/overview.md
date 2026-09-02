# docker buildx rm

Remove one or more builder instances.

## Usage

```text
docker buildx rm [OPTIONS] [NAME...]
```

## Options

| Option | Description |
|---|---|
| `--all-inactive` | Remove all inactive builders |
| `--builder string` | Override the configured builder instance |
| `-D, --debug` | Enable debug logging |
| `-f, --force` | Do not prompt for confirmation |
| `--keep-daemon` | Keep the BuildKit daemon running |
| `--keep-state` | Keep BuildKit state |
| `--timeout duration` | Override the default timeout for loading builder status (default 20s) |
