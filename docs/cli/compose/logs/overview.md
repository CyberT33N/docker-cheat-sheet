# docker compose logs

View output from containers.

## Usage

```text
docker compose logs [OPTIONS] [SERVICE...]
```

## Options

| Option | Description |
|---|---|
| `--dry-run` | Execute command in dry run mode |
| `-f, --follow` | Follow log output |
| `--index int` | index of the container if service has multiple replicas |
| `--no-color` | Produce monochrome output |
| `--no-log-prefix` | Don't print prefix in logs |
| `--since string` | Show logs since timestamp (e.g. 2013-01-02T13:23:37Z) or relative (e.g. 42m for 42 minutes) |
| `-n, --tail string` | Number of lines to show from the end of the logs for each container (default "all") |
| `-t, --timestamps` | Show timestamps |
| `--until string` | Show logs before a timestamp (e.g. 2013-01-02T13:23:37Z) or relative (e.g. 42m for 42 minutes) |

## Documented examples

Check logs:

```bash
sudo docker-compose logs

# use the follow paramater to monitor the logs of your containers
sudo docker-compose logs -f

# check logs of specific container
sudo docker-compose logs -f containername
```
