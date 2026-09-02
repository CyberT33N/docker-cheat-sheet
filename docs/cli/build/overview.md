# docker build

Build an image from a Dockerfile.

The docker build command builds Docker images from a Dockerfile and a "context".

- [Docker documentation: docker build](https://docs.docker.com/engine/reference/commandline/build/)

> `docker build` is an alias of `docker buildx build` (BuildKit). The complete option reference is documented in [Flags](./flags.md).

## Usage

```text
docker buildx build [OPTIONS] PATH | URL | -
```

## Aliases

- `docker build`
- `docker builder build`
- `docker image build`
- `docker buildx b`

## Documented notes

```bash
# . <-- means catch docker file from the current directory
docker build .
```

### tag

- [An introduction to Docker tags](https://www.freecodecamp.org/news/an-introduction-to-docker-tags-9b5395636c2a/)
- Docker tags convey useful information about a specific image version/variant
- name:tag
- -t or --tag

```bash
# . <-- means catch docker file from the current directory
docker build . -t namehere

# If you later want to push to remote repo you may use
docker build . -t usernameORDomain/imagename
```

### file

- Tells where the Dockerfile is located. For default it chooses the current path.
- -f or --file

```bash
docker build -f location here
```

## Build from specific Dockerfile

```bash
sudo docker build - < Dockerfile.test -t yourTagNameHere
```
