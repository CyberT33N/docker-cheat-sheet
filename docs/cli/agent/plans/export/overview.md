# docker agent plans export

Write a plan's content to a file.

## Usage

```text
docker agent plans export [<name>]
```

## Options

| Option | Description |
|---|---|
| `--force` | Replace the destination file when it already exists |
| `--json` | Output as JSON |
| `--output string` | Destination file for the plan content; required |
| `--scope string` | Plan scope: "shared" or "session" (default "shared"; "session" is implied by --session) |
| `--session string` | Session ID whose plan to address (session scope) |

Plus the [global flags](../../overview.md).
