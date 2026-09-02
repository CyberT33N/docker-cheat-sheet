# docker dhi customization prepare

Prepare a new single or bulk customization YAML file by fetching tag details from Docker Hardened Images. This creates a scaffold YAML file that can be used with the create command. The scaffold is written to stdout; redirect to a file if needed.

## Usage

```text
docker dhi customization prepare <dhi-repository> <tag>
```

## Options

| Option | Description |
|---|---|
| `-d, --destination string` | Destination repository (e.g. myorg/dhi-golang) |
| `-n, --name string` | Name for the customization |
| `--org string` | Docker Hub organization (overrides config) |
