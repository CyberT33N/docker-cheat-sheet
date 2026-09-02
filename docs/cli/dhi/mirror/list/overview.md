# docker dhi mirror list

List all Docker Hardened Images currently being mirrored to your organization's registry. Shows the source repositories, destination repositories, and mirroring status.

## Usage

```text
docker dhi mirror list
```

## Options

| Option | Description |
|---|---|
| `-f, --filter string` | Filter by repository name (partial match) |
| `--json` | Output in JSON format |
| `--org string` | Docker Hub organization (overrides config) |
| `--type string` | Filter by repository type (image or helm-chart) |
