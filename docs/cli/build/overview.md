# docker build

Build an image from a Dockerfile.

- [Docker documentation: docker build](https://docs.docker.com/engine/reference/commandline/build/)

## Usage

```text
docker build [OPTIONS] PATH | URL | -
```

## Options

| Option | Description |
|---|---|
| `--build-arg stringArray` | Set build-time variables |
| `--platform stringArray` | Set target platform for build |
| `-t, --tag stringArray` | Image identifier (format: "[registry/]repository[:tag]") |
| `-f, --file string` | Name of the Dockerfile (default: "PATH/Dockerfile") |
| `-q, --quiet` | Suppress the build output and print image ID on success |

## Documented examples

Parameterized product-image build from a governed repository root:

```bash
docker build --build-arg CONTROLLER=<IMAGE_NAME> --platform linux/amd64 -t <REGION>-docker.pkg.dev/<PROJECT_ID>/<REPOSITORY_NAME>/<IMAGE_NAME>:<COMMIT_SHA> .
```

Architectural explanation: the build context is the governed repository root, so the Dockerfile packages exactly the binary built from the pinned source commit — the `<COMMIT_SHA>` tag keeps the source provenance visible on the reference. `--build-arg` selects the parameterized product binary, and `--platform` pins the target architecture of the workload runtime. The base image is referenced by full digest in the Dockerfile, so the build resolves the identical base content on every machine. The build itself carries no delivery proof — the proof chain starts after the build: the auth-free smoke test (see [docker run](../run/overview.md)), then the push digest plus the registry read-back (see [docker push](../push/overview.md) and the remote digest binding under [docker buildx imagetools inspect](../buildx/imagetools/inspect/overview.md)).
