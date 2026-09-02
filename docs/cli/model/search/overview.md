# docker model search

Search for models from Docker Hub (ai/ namespace) and HuggingFace. When no search term is provided, lists all available models. When a search term is provided, filters models by name/description.

## Usage

```text
docker model search [OPTIONS] [TERM]
```

## Options

| Option | Description |
|---|---|
| `--json` | Output results as JSON |
| `-n, --limit int` | Maximum number of results to show (default 32) |
| `--source string` | Source to search: all, dockerhub, huggingface (default "all") |
