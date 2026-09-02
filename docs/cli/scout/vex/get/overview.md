# docker scout vex get

Get VEX attestation for image.

## Usage

```text
docker scout vex get OPTIONS IMAGE
```

## Options

| Option | Description |
|---|---|
| `--key string` | Signature key to use for verification (default "https://registry.scout.docker.com/keyring/dhi/latest.pub") |
| `--org string` | Namespace of the Docker organization |
| `-o, --output string` | Write the report to a file |
| `--platform string` | Platform of image to analyze |
| `--ref string` | Reference to use if the provided tarball contains multiple references. Can only be used with archive |
| `--skip-tlog` | Skip signature verification against public transaction log |
| `--verify` | Verify the signature on the attestation |
