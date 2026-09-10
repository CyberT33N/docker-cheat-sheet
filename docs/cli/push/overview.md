# docker push

Upload an image to a registry.

- Push image to repo
- When you use docker login to connect to remote repo the command below will work as well
- [Docker documentation: docker push](https://docs.docker.com/engine/reference/commandline/push/)

## Usage

```text
docker push [OPTIONS] NAME[:TAG]
```

## Aliases

- `docker image push`

## Options

| Option | Description |
|---|---|
| `-a, --all-tags` | Push all tags of an image to the repository |
| `--platform string` | Push a platform-specific manifest as a single-platform image to the registry. Image index won't be pushed, meaning that other manifests, including attestations won't be preserved. 'os[/arch[/variant]]': Explicit platform (eg. linux/amd64) |
| `-q, --quiet` | Suppress verbose output |

## Documented examples

```bash
# push to docker website
docker push username/imagename
```

Push to an OCI registry with the digest proof:

```bash
docker push <REGION>-docker.pkg.dev/<PROJECT_ID>/<REPOSITORY_NAME>/<IMAGE_NAME>:<COMMIT_SHA>
```

Architectural explanation: the push output ends with the registry-accepted content digest (`<TAG>: digest: sha256:<DIGEST> size: ...`). That digest is the delivery proof: it must equal the registry-side read-back (`gcloud artifacts docker images describe` or `docker buildx imagetools inspect` on the same reference). The pair — push digest plus read-back digest — is the fail-closed evidence that the content built locally is the content stored remotely.
