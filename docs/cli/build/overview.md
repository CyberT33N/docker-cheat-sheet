# docker build

Build an image from a Dockerfile.

## Usage

```text
docker build [OPTIONS] PATH
```

## Options

| Option | Description |
|---|---|
| `--build-arg stringArray` | Set build-time variables (for example the parameterized controller argument of a governed Dockerfile) |
| `--platform string` | Set the target platform (for example `linux/amd64`) |
| `-t, --tag stringArray` | Name and optionally a tag in the `name:tag` format |

## Documented examples

Parameterized governed build onto a digest-pinned minimal runtime:

```bash
docker build --build-arg CONTROLLER=<CONTROLLER_NAME> --platform linux/amd64 -t <REGION>-docker.pkg.dev/<PROJECT_ID>/<REPOSITORY_NAME>/<IMAGE_NAME>:<COMMIT_SHA> .
```

Architectural explanation: the governed build form packages a locally built, toolchain-pinned binary onto a digest-pinned minimal non-root runtime through a parameterized Dockerfile (`ARG CONTROLLER`); the build context is the repository root, so the binary path in the context is build output, never source. The proof pair of the build is the entrypoint smoke test (`docker run --rm <ref> --version`, see [run](../run/overview.md)) before any delivery and the registry-side digest read-back after the push (see [push](../push/overview.md)) — the local build is proven only when the pushed digest equals the registry read-back.
