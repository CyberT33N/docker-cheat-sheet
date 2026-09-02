# docker logs

Fetch the logs of a container.

- Show logs of your container
- Only show log of main process
- [Docker documentation: docker logs](https://docs.docker.com/engine/reference/commandline/logs/)

## Usage

```text
docker logs [OPTIONS] CONTAINER
```

## Aliases

- `docker container logs`

## Options

| Option | Description |
|---|---|
| `--details` | Show extra details provided to logs |
| `-f, --follow` | Follow log output |
| `--since string` | Show logs since timestamp (e.g. "2013-01-02T13:23:37Z") or relative (e.g. "42m" for 42 minutes) |
| `-n, --tail string` | Number of lines to show from the end of the logs (default "all") |
| `-t, --timestamps` | Show timestamps |
| `--until string` | Show logs before a timestamp (e.g. "2013-01-02T13:23:37Z") or relative (e.g. "42m" for 42 minutes) |

## Documented examples

```bash
sudo docker logs container_name_here
```

## follow

- follow logs (monitor logs)
- --follow or -f

```bash
sudo docker logs -f container_name_here
```
