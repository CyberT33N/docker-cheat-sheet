# docker scout watch

Watch repositories in a registry and push images and indexes to Docker Scout.

## Usage

```text
docker scout watch
```

## Options

| Option | Description |
|---|---|
| `--all-images` | Push all images instead of only the ones pushed during the watch command is running |
| `--dry-run` | Watch images and prepare them, but do not push them |
| `--interval int` | Interval in seconds between checks (default 60) |
| `--org string` | Namespace of the Docker organization to which image will be pushed |
| `--refresh-registry` | Refresh the list of repositories of a registry at every run. Only with --registry. |
| `--registry string` | Registry to watch |
| `--repository strings` | Repository to watch |
| `--sbom` | Create and upload SBOMs (default true) |
| `--tag strings` | Regular expression to match tags to watch |
| `--workers int` | Number of concurrent workers (default 3) |
