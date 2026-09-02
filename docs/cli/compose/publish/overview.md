# docker compose publish

Publish compose application.

## Usage

```text
docker compose publish [OPTIONS] REPOSITORY[:TAG]
```

## Options

| Option | Description |
|---|---|
| `--app` | Published compose application (includes referenced images) |
| `--dry-run` | Execute command in dry run mode |
| `--oci-version string` | OCI image/artifact specification version (automatically determined by default) |
| `--resolve-image-digests` | Pin image tags to digests |
| `--with-env` | Include environment variables in the published OCI artifact |
| `-y, --yes` | Assume "yes" as answer to all prompts |
