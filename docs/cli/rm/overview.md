# docker rm

Remove one or more containers.

## Usage

```text
docker rm [OPTIONS] CONTAINER [CONTAINER...]
```

## Aliases

- `docker container rm`
- `docker container remove`

## Options

| Option | Description |
|---|---|
| `-f, --force` | Force the removal of a running container (uses SIGKILL) |
| `-l, --link` | Remove the specified link |
| `-v, --volumes` | Remove anonymous volumes associated with the container |

## Documented examples

Remove container:

```bash
sudo docker rm <container-name/ID>
```

Remove all container:

```bash
sudo docker rm --force $(sudo docker ps -a -q)
```
