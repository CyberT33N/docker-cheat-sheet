# docker history

Show the history of an image.

- Using the docker image history command, you can see the command that was used to create each layer within an image.

## Usage

```text
docker history [OPTIONS] IMAGE
```

## Aliases

- `docker image history`

## Options

| Option | Description |
|---|---|
| `--format string` | Format output using a custom template ('table', 'json' or a Go template) |
| `-H, --human` | Print sizes and dates in human readable format (default true) |
| `--no-trunc` | Don't truncate output |
| `--platform string` | Show history for the given platform. Formatted as "os[/arch[/variant]]" (e.g., "linux/amd64") |
| `-q, --quiet` | Only show image IDs |

## Documented examples

Show history of image:

```bash
docker image history getting-started
```

## Get Dockerfile from Image

```bash
docker history --no-trunc imageIDhere | tac | tr -s ' ' | cut -d " " -f 5- | sed 's,^/bin/sh -c #(nop) ,,g' | sed 's,^/bin/sh -c,RUN,g' | sed 's, && ,\n  & ,g' | sed 's,\s*[0-9]*[\.]*[0-9]*\s*[kMG]*B\s*$,,g' | head -n -1
```
