# docker model launch

Launch an app configured to use Docker Model Runner. Without arguments, lists all supported apps. Supported apps: anythingllm, claude, codex, openclaw, opencode, openwebui.

## Usage

```text
docker model launch [APP] [-- APP_ARGS...]
```

## Options

| Option | Description |
|---|---|
| `--config` | Print configuration without launching |
| `--detach` | Run containerized app in background |
| `--dry-run` | Print what would be executed without running it |
| `--image string` | Override container image for containerized apps |
| `--model string` | Model to use (for opencode) |
| `--port int` | Host port to expose (web UIs) |
