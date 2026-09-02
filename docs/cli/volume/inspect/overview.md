# docker volume inspect

Display detailed information on one or more volumes.

## Usage

```text
docker volume inspect [OPTIONS] VOLUME [VOLUME...]
```

## Options

| Option | Description |
|---|---|
| `-f, --format string` | Format output using a custom template ('json' or a Go template) |

## Documented examples

Get details about named volume:

- The Mountpoint is the actual location on the disk where the data is stored. Note that on most machines, you will need to have root access to access this directory from the host.

```bash
docker volume inspect todo-db
[
    {
        "CreatedAt": "2019-09-26T02:18:36Z",
        "Driver": "local",
        "Labels": {},
        "Mountpoint": "/var/lib/docker/volumes/todo-db/_data",
        "Name": "todo-db",
        "Options": {},
        "Scope": "local"
    }
]
```
