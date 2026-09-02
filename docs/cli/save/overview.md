# docker save

Save one or more images to a tar archive (streamed to STDOUT by default).

- [Docker documentation: docker save](https://docs.docker.com/engine/reference/commandline/save/)

## Usage

```text
docker save [OPTIONS] IMAGE [IMAGE...]
```

## Aliases

- `docker image save`

## Options

| Option | Description |
|---|---|
| `-o, --output string` | Write to a file, instead of STDOUT |
| `--platform strings` | Save only the given platform(s). Formatted as a comma-separated list of "os[/arch[/variant]]" (e.g., "linux/amd64,linux/arm64/v8") |

## Documented examples

Save all images to one tar file:

```bash
docker save $(docker images -q) -o socket.io-chat-app-full.tar
```

## Related

- [docker export](../export/overview.md) — Export a container's filesystem as a tar archive
