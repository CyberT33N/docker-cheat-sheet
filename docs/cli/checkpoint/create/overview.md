# docker checkpoint create

Create a checkpoint from a running container.

> EXPERIMENTAL: This command is experimental and requires a Docker daemon with experimental features enabled.

- [Docker documentation: docker checkpoint create](https://docs.docker.com/reference/cli/docker/checkpoint/create/)

## Usage

```text
docker checkpoint create [OPTIONS] CONTAINER CHECKPOINT
```

## Options

| Option | Description |
|---|---|
| `--checkpoint-dir` | Use a custom checkpoint storage directory |
| `--leave-running` | Leave the container running after checkpoint |
