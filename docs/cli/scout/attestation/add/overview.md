# docker scout attestation add

Add attestation to image.

## Usage

```text
docker scout attestation add OPTIONS IMAGE [IMAGE...]
```

## Options

| Option | Description |
|---|---|
| `--file strings` | File location of attestations to attach |
| `--org string` | Namespace of the Docker organization |
| `--predicate-type string` | Predicate-type for attestations |
| `--referrer` | Use OCI referrer API for pushing attestation |
| `--referrer-repository string` | Repository to push referrer to (default "registry.scout.docker.com") |
