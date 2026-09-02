# docker agent alias add

Add a new alias.

## Usage

```text
docker agent alias add <alias-name> <agent-path>
```

## Options

| Option | Description |
|---|---|
| `--hide-tool-results` | Hide tool call results in the TUI |
| `--model string` | Override agent model (format: [agent=]provider/model) |
| `--safety string` | Default safety mode when running the alias: strict, balanced, or autonomous (wins over --yolo) |
| `--sandbox` | Always run the agent inside a Docker sandbox |
| `--yolo` | Automatically approve all tool calls without prompting |

Plus the [global flags](../../overview.md).
