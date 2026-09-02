# docker buildx imagetools create

Create a new image based on source images.

## Usage

```text
docker buildx imagetools create [OPTIONS] [SOURCE...]
```

## Options

| Option | Description |
|---|---|
| `--annotation stringArray` | Add annotation to the image |
| `--append` | Append to existing manifest |
| `--builder string` | Override the configured builder instance |
| `-D, --debug` | Enable debug logging |
| `--dry-run` | Show final image instead of pushing |
| `-f, --file stringArray` | Read source descriptor from file |
| `--metadata-file string` | Write create result metadata to a file |
| `-p, --platform stringArray` | Filter specified platforms of target image |
| `--prefer-index` | When only a single source is specified, prefer outputting an image index or manifest list instead of performing a carbon copy (default true) |
| `--progress string` | Set type of progress output ("auto", "none", "plain", "rawjson", "tty") (default "auto") |
| `-t, --tag stringArray` | Set reference for new image |
