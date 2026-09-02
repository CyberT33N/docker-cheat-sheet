# docker dhi attestation get

Get an attestation attached to a Docker Hardened Image. Returns the in-toto statement extracted from the attestation referrer. The referrer digest must be provided to select which attestation to retrieve.

## Usage

```text
docker dhi attestation get <image> <digest>
```

## Options

| Option | Description |
|---|---|
| `--org string` | Docker Hub organization (overrides config) |
| `-o, --output string` | Write output to file instead of stdout |
