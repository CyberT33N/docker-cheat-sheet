# docker start

Start one or more stopped containers.

- You can see name/id at [docker ps](../ps/overview.md) -a

## Usage

```text
docker start [OPTIONS] CONTAINER [CONTAINER...]
```

## Aliases

- `docker container start`

## Options

| Option | Description |
|---|---|
| `-a, --attach` | Attach STDOUT/STDERR and forward signals |
| `--detach-keys string` | Override the key sequence for detaching a container |
| `-i, --interactive` | Attach container's STDIN |

## Documented examples

```bash
docker start <container-name/ID>
```
