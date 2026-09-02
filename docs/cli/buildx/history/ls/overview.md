# docker buildx history ls

List build records.

## Usage

```text
docker buildx history ls [OPTIONS]
```

## Options

| Option | Description |
|---|---|
| `--builder string` | Override the configured builder instance |
| `-D, --debug` | Enable debug logging |
| `--filter stringArray` | Provide filter values (e.g., "status=error") |
| `--format string` | Format the output (default "table") |
| `--local` | List records for current repository only |
| `--no-trunc` | Don't truncate output |
