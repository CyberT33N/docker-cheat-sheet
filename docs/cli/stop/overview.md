# docker stop

Stop one or more running containers.

- You can see name/id at [docker ps](../ps/overview.md) -a

## Usage

```text
docker stop [OPTIONS] CONTAINER [CONTAINER...]
```

## Aliases

- `docker container stop`

## Options

| Option | Description |
|---|---|
| `-s, --signal string` | Signal to send to the container |
| `-t, --timeout int` | Seconds to wait before killing the container |

## Documented examples

```bash
docker stop <container-name/ID>
```

## Stop all running container

```bash
sudo docker stop $(sudo docker ps -a -q)
```
