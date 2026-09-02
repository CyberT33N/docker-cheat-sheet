# docker commit

Create a new image from a container's changes.

## Usage

```text
docker commit [OPTIONS] CONTAINER [REPOSITORY[:TAG]]
```

## Aliases

- `docker container commit`

## Options

| Option | Description |
|---|---|
| `-a, --author string` | Author (e.g., "John Hannibal Smith <hannibal@a-team.com>") |
| `-c, --change list` | Apply Dockerfile instruction to the created image |
| `-m, --message string` | Commit message |
| `--no-pause` | Disable pausing container during commit |

## Documented examples

Create an image of an existing container:

```bash
docker commit container_id svendowideit/testimage:version3
```
