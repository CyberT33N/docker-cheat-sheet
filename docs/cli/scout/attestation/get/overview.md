# docker scout attestation get

Get attestation for image.

## Usage

```text
docker scout attestation get OPTIONS IMAGE [DIGEST]
```

## Options

| Option | Description |
|---|---|
| `--key string` | Signature key to use for verification (default "https://registry.scout.docker.com/keyring/dhi/latest.pub") |
| `--org string` | Namespace of the Docker organization |
| `-o, --output string` | Write the report to a file |
| `--platform string` | Platform of image to analyze |
| `--predicate` | Get in-toto predicate only dropping the subject |
| `--predicate-type string` | Predicate-type for attestation |
| `--ref string` | Reference to use if the provided tarball contains multiple references. Can only be used with archive |
| `--skip-tlog` | Skip signature verification against public transaction log |
| `--verify` | Verify the signature on the attestation |
