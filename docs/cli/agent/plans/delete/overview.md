# docker agent plans delete

Delete a shared plan.

## Usage

```text
docker agent plans delete <name>
```

## Aliases

- `delete`
- `rm`

## Options

| Option | Description |
|---|---|
| `--expected-version int` | Version the plan is expected to be at; the write fails with a version conflict (exit code 3) when it changed |
| `--force` | Write unconditionally, without the optimistic-lock guard |
| `--json` | Output as JSON |
| `--scope string` | Plan scope: "shared" or "session" (default "shared"; "session" is implied by --session) |
| `--session string` | Session ID whose plan to address (session scope) |

Plus the [global flags](../../overview.md).
