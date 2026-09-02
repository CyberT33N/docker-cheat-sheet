# docker agent plans update

Replace the content of an existing shared plan.

## Usage

```text
docker agent plans update <name>
```

## Options

| Option | Description |
|---|---|
| `--author string` | New author label (omit to preserve the current one) |
| `--expected-version int` | Version the plan is expected to be at; the write fails with a version conflict (exit code 3) when it changed |
| `--file string` | File with the new plan content ("-" reads stdin); required |
| `--force` | Write unconditionally, without the optimistic-lock guard |
| `--json` | Output as JSON |
| `--scope string` | Plan scope: "shared" or "session" (default "shared"; "session" is implied by --session) |
| `--session string` | Session ID whose plan to address (session scope) |
| `--status string` | New lifecycle status (omit to preserve the current one) |
| `--title string` | New plan title (omit to preserve the current one) |

Plus the [global flags](../../overview.md).
