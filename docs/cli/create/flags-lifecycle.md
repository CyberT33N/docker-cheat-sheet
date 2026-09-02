# docker create — Lifecycle Flags

| Option | Description |
|---|---|
| `-a, --attach list` | Attach to STDIN, STDOUT or STDERR |
| `--cidfile string` | Write the container ID to the file |
| `--entrypoint string` | Overwrite the default ENTRYPOINT of the image |
| `-e, --env list` | Set environment variables |
| `--env-file list` | Read in a file of environment variables |
| `--help` | Print usage |
| `-i, --interactive` | Keep STDIN open even if not attached |
| `--name string` | Assign a name to the container |
| `--pull string` | Pull image before creating ("always", "missing", "never") (default "missing") |
| `-q, --quiet` | Suppress the pull output |
| `--restart string` | Restart policy to apply when a container exits (default "no") |
| `--rm` | Automatically remove the container and its associated anonymous volumes when it exits |
| `--stop-signal string` | Signal to stop the container |
| `--stop-timeout int` | Timeout (in seconds) to stop a container |
| `-t, --tty` | Allocate a pseudo-TTY |
| `-w, --workdir string` | Working directory inside the container |
