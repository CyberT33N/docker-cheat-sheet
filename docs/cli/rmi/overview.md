# docker rmi

Remove one or more images.

## Usage

```text
docker rmi [OPTIONS] IMAGE [IMAGE...]
```

## Aliases

- `docker image rm`
- `docker image remove`

## Options

| Option | Description |
|---|---|
| `-f, --force` | Force removal of the image |
| `--no-prune` | Do not delete untagged parents |
| `--platform strings` | Remove only the given platform variant. Formatted as "os[/arch[/variant]]" (e.g., "linux/amd64") |

## Documented examples

Remove image:

```bash
sudo docker rmi <container-name/ID/name:tag>
```

Remove all images:

```bash
# Method #1
sudo docker rm -vf $(sudo docker ps -aq)
sudo docker rmi -f $(sudo docker images -aq)

# Method #2
sudo docker rmi --force $(sudo docker ps -a -q)
```
