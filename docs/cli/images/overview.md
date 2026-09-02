# docker images

List images.

- [Docker documentation: docker images](https://docs.docker.com/engine/reference/commandline/images/)

## Usage

```text
docker images [OPTIONS] [REPOSITORY[:TAG]]
```

## Aliases

- `docker image ls`
- `docker image list`

## Options

| Option | Description |
|---|---|
| `-a, --all` | Show all images (default hides intermediate and dangling images) |
| `--digests` | Show digests |
| `-f, --filter filter` | Filter output based on conditions provided |
| `--format string` | Format output using a custom template ('table', 'json' or a Go template) |
| `--no-trunc` | Don't truncate output |
| `-q, --quiet` | Only show image IDs |
| `--tree` | List multi-platform images as a tree (EXPERIMENTAL) |

## Documented examples

Show existing images:

```bash
docker images
```
