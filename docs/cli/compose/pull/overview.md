# docker compose pull

Pull service images.

## Usage

```text
docker compose pull [OPTIONS] [SERVICE...]
```

## Options

| Option | Description |
|---|---|
| `--dry-run` | Execute command in dry run mode |
| `--ignore-buildable` | Ignore images that can be built |
| `--ignore-pull-failures` | Pull what it can and ignores images with pull failures |
| `--include-deps` | Also pull services declared as dependencies |
| `--policy string` | Apply pull policy ("missing"\|"always") |
| `-q, --quiet` | Pull without printing progress information |
