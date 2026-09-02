# docker pull

Download an image from a registry.

- [Docker documentation: docker pull](https://docs.docker.com/engine/reference/commandline/pull/)

## Usage

```text
docker pull [OPTIONS] NAME[:TAG|@DIGEST]
```

## Aliases

- `docker image pull`

## Options

| Option | Description |
|---|---|
| `-a, --all-tags` | Download all tagged images in the repository |
| `--platform string` | Set platform if server is multi-platform capable |
| `-q, --quiet` | Suppress verbose output |

## Documented examples

```bash
docker pull ubuntu
docker pull debian:jessie
docker pull ubuntu:14.04
docker pull myregistry.local:5000/testing/test-image
```
