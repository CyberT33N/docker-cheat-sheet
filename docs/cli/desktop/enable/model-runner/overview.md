# docker desktop enable model-runner

Enable and manage Docker Model Runner settings used by 'docker model'.

## Usage

```text
docker desktop enable model-runner [OPTIONS]
```

## Options

| Option | Description |
|---|---|
| `--cors strings` | CORS configuration: 'all', 'none', or a comma-separated list of allowed origins. Applies to Docker Model Runner HTTP connections. |
| `--gpu string` | Enable or disable GPU support: 'enable' or 'disable'. Requires a compatible GPU. See [Docker Model Runner](https://docs.docker.com/go/model-runner/). |
| `--tcp port[=12434]` | Set TCP port for HTTP connection (1-65535). (default 12434) |
