# docker export

Export a container's filesystem as a tar archive.

## Usage

```text
docker export [OPTIONS] CONTAINER
```

## Aliases

- `docker container export`

## Options

| Option | Description |
|---|---|
| `-o, --output string` | Write to a file, instead of STDOUT |

## Documented examples

Save specific image:

```bash
sudo docker export image_name/image_id > socket.io-chat-app.tar
```

## Related

- [docker save](../save/overview.md) — Save one or more images to a tar archive
