# docker trust key load

Load a private key file for signing. Adds private keys to the local Docker trust keystore.

- [Docker documentation: docker trust key load](https://docs.docker.com/reference/cli/docker/trust/key/load/)

## Usage

```text
docker trust key load [OPTIONS] KEYFILE
```

## Options

| Option | Default | Description |
|---|---|---|
| `--name` | `signer` | Name for the loaded key |
