# docker debug

Get an enhanced shell with additional tools into any container or image.

> `docker debug` is a Docker CLI plugin.

## Usage

```text
docker debug [OPTIONS] COMMAND
```

## Options

| Option | Description |
|---|---|
| `-c, --command string` | Evaluate the specified commands instead, passing additional positional arguments through $argv. |
| `--host string` | Daemon docker socket to connect to. E.g.: 'ssh://root@example.org', 'unix:///some/path/docker.sock' |
| `--preserve-user` | Running containers only: Use same user as the running container. Default is root. |
| `--privileged` | Running containers only: Give privileges to the shell (all capabilities). |
| `--shell shell` | Select a shell. Supported: "bash", "fish", "zsh", "auto". (default auto) |
| `--version` | Display version of the docker-debug plugin |

## Subcommands

See [TOC](./toc.md) for the complete subcommand list.
