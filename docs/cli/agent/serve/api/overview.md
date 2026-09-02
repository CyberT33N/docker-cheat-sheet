# docker agent serve api

Start the API server.

## Usage

```text
docker agent serve api
```

## Options

| Option | Description |
|---|---|
| `--pull-interval int` | Auto-pull OCI reference every N minutes (0 = disabled) |
| `--record string` | Record AI API interactions to cassette file |
| `-s, --session-db string` | Path to the session database (default "session.db") |
| `--session-workingdir-root string` | Restrict the working_dir of sessions created via POST /api/sessions to this directory and its descendants (empty = no restriction; recommended for multi-user deployments) |
| `--working-dir string` | Set the working directory for the session (applies to tools and relative paths) |

Plus the [global flags](../../../overview.md).
