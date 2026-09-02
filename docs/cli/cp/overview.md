# docker cp

Copy files/folders between a container and the local filesystem.

Use '-' as the source to read a tar archive from stdin and extract it to a directory destination in a container. Use '-' as the destination to stream a tar archive of a container source to stdout.

## Usage

```text
docker cp [OPTIONS] CONTAINER:SRC_PATH DEST_PATH|-
docker cp [OPTIONS] SRC_PATH|- CONTAINER:DEST_PATH
```

## Aliases

- `docker container cp`

## Options

| Option | Description |
|---|---|
| `-a, --archive` | Archive mode (copy all uid/gid information) |
| `-L, --follow-link` | Always follow symlinks in SRC_PATH |
| `-q, --quiet` | Suppress progress output during copy. Progress output is automatically suppressed if no terminal is attached |

## Documented examples

Copy file to running container:

```bash
sudo docker cp "/home/usernamehere/Documents/tmpEmbedDump.csv"  mongomain:"tmpEmbedDump.csv"
```
