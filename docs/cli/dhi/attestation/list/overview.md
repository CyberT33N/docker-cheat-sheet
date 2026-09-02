# docker dhi attestation list

List all attestations attached to a Docker Hardened Image. Attestations are retrieved via the OCI Referrers API from the Docker Scout referrer registry.

## Usage

```text
docker dhi attestation list <image>
```

## Options

| Option | Description |
|---|---|
| `--json` | Output in JSON format |
| `--org string` | Docker Hub organization (overrides config) |
| `--platform string` | Platform to filter by (e.g., linux/amd64). Defaults to the Docker daemon platform |
| `--predicate-type stringArray` | Filter by predicate type (can be specified multiple times) |
