# docker dhi customization create

Create a new Docker Hardened Images customization using a YAML file as input. The file should contain the complete customization structure without an 'id' field.

## Usage

```text
docker dhi customization create <file>
```

## Options

| Option | Description |
|---|---|
| `-d, --destination string` | Override the destination repository (e.g. myorg/dhi-golang) |
| `--json` | Output in JSON format |
| `-n, --name string` | Override the customization name from the YAML file |
| `--org string` | Docker Hub organization (overrides config) |
| `-t, --tag-definition-id string` | Override the tag definition ID (single-target only) |
