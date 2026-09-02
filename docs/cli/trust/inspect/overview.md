# docker trust inspect

Return low-level information about keys and signatures. Provides low-level JSON information on signed repositories: all image tags that are signed, who signed them, and who can sign new tags.

- [Docker documentation: docker trust inspect](https://docs.docker.com/reference/cli/docker/trust/inspect/)

## Usage

```text
docker trust inspect IMAGE[:TAG] [IMAGE[:TAG]...]
```

## Options

| Option | Description |
|---|---|
| `--pretty` | Print the information in a human friendly format |
