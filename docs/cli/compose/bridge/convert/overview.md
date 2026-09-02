# docker compose bridge convert

Convert compose files to Kubernetes manifests, Helm charts, or another model.

## Usage

```text
docker compose bridge convert
```

## Options

| Option | Description |
|---|---|
| `--dry-run` | Execute command in dry run mode |
| `-o, --output string` | The output directory for the Kubernetes resources (default "out") |
| `--templates string` | Directory containing transformation templates |
| `-t, --transformation stringArray` | Transformation to apply to compose model (default: docker/compose-bridge-kubernetes) |
