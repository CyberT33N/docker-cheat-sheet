# docker buildx imagetools inspect

Show details of an image in the registry.

## Usage

```text
docker buildx imagetools inspect [OPTIONS] NAME
```

## Options

| Option | Description |
|---|---|
| `--builder string` | Override the configured builder instance |
| `-D, --debug` | Enable debug logging |
| `--format string` | Format the output using the given Go template |
| `--raw` | Show original, unformatted JSON manifest |

## Documented examples

Bind the digest of a remote reference without pulling the image:

```bash
docker buildx imagetools inspect gcr.io/distroless/static-debian12:nonroot
```

The `Digest` line of the answer is the content address of the OCI image index; the per-platform manifests are listed beneath it. This is the upstream proof form for pinning a base image by digest: the tag is resolved remotely and the digest is bound, never the other way around. The same form proves a pushed image in the target registry after a `docker push`.

## Related

- [docker push](../../../../push/overview.md) — Upload an image to a registry (digest extraction workflow is planned for the examples area)
