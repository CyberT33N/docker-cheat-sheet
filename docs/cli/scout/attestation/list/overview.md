# docker scout attestation list

List attestations for image.

## Usage

```text
docker scout attestation list OPTIONS IMAGE
```

## Aliases

- `list`
- `ls`

## Options

| Option | Description |
|---|---|
| `--format string` | Output format: list, json (default "list") |
| `--org string` | Namespace of the Docker organization |
| `-o, --output string` | Write the report to a file |
| `--platform string` | Platform of image to analyze |
| `--predicate-type string` | Predicate-type for attestations |
| `--ref string` | Reference to use if the provided tarball contains multiple references. Can only be used with archive |
