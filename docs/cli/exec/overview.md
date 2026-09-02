# docker exec

Execute a command in a running container.

- [Docker documentation: docker exec](https://docs.docker.com/engine/reference/commandline/exec/)

## Usage

```text
docker exec [OPTIONS] CONTAINER COMMAND [ARG...]
```

## Aliases

- `docker container exec`

## Options

| Option | Description |
|---|---|
| `-d, --detach` | Detached mode: run command in the background |
| `--detach-keys string` | Override the key sequence for detaching a container |
| `-e, --env list` | Set environment variables |
| `--env-file list` | Read in a file of environment variables |
| `-i, --interactive` | Keep STDIN open even if not attached |
| `--privileged` | Give extended privileges to the command |
| `-t, --tty` | Allocate a pseudo-TTY |
| `-u, --user string` | Username or UID (format: "<name\|uid>[:<group\|gid>]") |
| `-w, --workdir string` | Working directory inside the container |

## Documented examples

Enter terminal of Container:

```bash
# example #1
docker exec -it samplename bash

# example #2
docker exec -it <mysql-container-id> mysql -p

# example 3
 sudo docker exec -it mongomain bash -c "pwd"
```

## fix command not found error at clean debian container

```bash
apt-get update && apt-get -y install sudo
```

## Exit

Exit container:

```bash
exit
```
