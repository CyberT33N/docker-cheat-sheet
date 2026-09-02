# docker import

Import the contents from a tarball to create a filesystem image.

## Usage

```text
docker import [OPTIONS] file|URL|- [REPOSITORY[:TAG]]
```

## Aliases

- `docker image import`

## Options

| Option | Description |
|---|---|
| `-c, --change list` | Apply Dockerfile instruction to the created image |
| `-m, --message string` | Set commit message for imported image |
| `--platform string` | Set platform if server is multi-platform capable |
