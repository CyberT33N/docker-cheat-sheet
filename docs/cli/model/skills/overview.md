# docker model skills

Install Docker Model Runner skills for AI coding assistants. Skills are configuration files that help AI coding assistants understand how to use Docker Model Runner effectively for local model inference.

## Usage

```text
docker model skills
```

## Options

| Option | Description |
|---|---|
| `--claude` | Install skills for Claude Code (~/.claude/skills) |
| `--codex` | Install skills for OpenAI Codex CLI (~/.codex/skills) |
| `--dest string` | Install skills to a custom directory |
| `-f, --force` | Overwrite existing skills without prompting |
| `--opencode` | Install skills for OpenCode (~/.config/opencode/skills) |
