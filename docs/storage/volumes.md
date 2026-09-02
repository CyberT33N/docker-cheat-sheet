# Volumes

- [Docker documentation: Volumes](https://docs.docker.com/storage/volumes/)
- Volumes are completely managed by Docker and do not depend on the directory structure and OS of the host machine.

- Volumes are easier to back up or migrate than bind mounts.
- You can manage volumes using Docker CLI commands or the Docker API.
- Volumes work on both Linux and Windows containers.
- Volumes can be more safely shared among multiple containers.
- Volume drivers let you store volumes on remote hosts or cloud providers, to encrypt the contents of volumes, or to add other functionality.
- New volumes can have their content pre-populated by a container.
- Volumes on Docker Desktop have much higher performance than bind mounts from Mac and Windows hosts.

## Guides

- [Persisting data](https://docs.docker.com/get-started/05_persisting_data/)

## CLI

- Create a named volume: [docker volume create](../cli/volume/create/overview.md)
- Get details about a named volume: [docker volume inspect](../cli/volume/inspect/overview.md)
