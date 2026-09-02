# docker stack config

Outputs the final config file, after doing merges and interpolations.

## Usage

```text
docker stack config [OPTIONS]
```

## Options

| Option | Description |
|---|---|
| `-c, --compose-file strings` | Path to a Compose file, or "-" to read from stdin |
| `--skip-interpolation` | Skip interpolation and output only merged config |
