# docker compose down

Stop and remove containers, networks.

## Usage

```text
docker compose down [OPTIONS] [SERVICES]
```

## Options

| Option | Description |
|---|---|
| `--dry-run` | Execute command in dry run mode |
| `--remove-orphans` | Remove containers for services not defined in the Compose file |
| `--rmi string` | Remove images used by services. "local" remove only images that don't have a custom tag ("local"\|"all") |
| `-t, --timeout int` | Specify a shutdown timeout in seconds |
| `-v, --volumes` | Remove named volumes declared in the "volumes" section of the Compose file and anonymous volumes attached to containers |

## Documented examples

Shutdown:

```bash
sudo docker-compose down

# By default, named volumes in your compose file are NOT removed when running docker-compose down. If you want to remove the volumes, you will need to add the --volumes flag.
sudo docker-compose down --volumes
```
