# docker dhi attestation sbom

Display the SPDX SBOM attestation attached to a Docker Hardened Image in a human-readable format. Fetches the SPDX SBOM attestation from the OCI Referrers API, extracts the SPDX document, and displays a summary with a package table.

## Usage

```text
docker dhi attestation sbom <image>
```

## Options

| Option | Description |
|---|---|
| `--org string` | Docker Hub organization (overrides config) |
| `--platform string` | Platform to filter by (e.g., linux/amd64). Defaults to the Docker daemon platform |
