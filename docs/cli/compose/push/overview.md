# docker compose push

Push service images.

## Usage

```text
docker compose push [OPTIONS] [SERVICE...]
```

## Options

| Option | Description |
|---|---|
| `--dry-run` | Execute command in dry run mode |
| `--ignore-push-failures` | Push what it can and ignores images with push failures |
| `--include-deps` | Also push images of services declared as dependencies |
| `-q, --quiet` | Push without printing progress information |
