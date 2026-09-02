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
