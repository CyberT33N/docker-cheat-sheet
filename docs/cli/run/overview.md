# docker run

Create and run a new container from an image.

The docker run command first creates a writeable container layer over the specified image, and then starts it using the specified command.

## Usage

```text
docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
```

## Aliases

- `docker container run`

## Options

The options are grouped by topic:

- [Compute flags](./flags-compute.md) — CPU, memory, IO and process limits
- [Networking flags](./flags-networking.md) — DNS, networks, ports and hosts
- [Storage flags](./flags-storage.md) — Volumes, mounts and filesystem options
- [Lifecycle flags](./flags-lifecycle.md) — Detach, restart, environment and entrypoint
- [System flags](./flags-system.md) — Security, namespaces, capabilities and metadata

## Documented notes

```bash
# Amount of CPU you want to use for this container. In this case two and a half CPU
--cpus 2.5

# Name of the Container - Only [a-zA-Z0-9][a-zA-Z0-9_.-] are allowed.
--name samplename

# Run container in background and print container ID
--detach , -d

# Set environment variables
--env , -e

# Memory limit. In this case 512 MB
--memory , -m 512m

# Enable unlimited Memory Swap
--memory-swap -1

# Use 2GB Memory Swap
--memory-swap 2048

# Allocate a pseudo-TTY (teletype aka terminal)
--tty , -t

# Username or UID (format: <name|uid>[:<group|gid>])
--user , -u

# Publish a container's port(s) to the host. In this case first 80 port is from host and second 80 port is from docker container
--publish , -p 80:80

# Bind mount a volume. We will use the named volume and mount it to /etc/todos, which will capture all files created at the path.
--volume , -v todo-db:/etc/todos

# bind mount the current directory from the host in the container into the /app directory
-v $(pwd):/app

# If volume "todo-mysql-data" was never created before it will be created automatically
-v todo-mysql-data:/var/lib/mysql 

# Working directory inside the container
--workdir , -w	
```

## Create Docker Container with Ubuntu and allocate pseudo-TTY

```bash
docker run -d --name test -it ubuntu
```

## Run terminal command

```bash
# on alpine use sh cause bash does not exist
docker run -d --name test -it ubuntu bash -c "your command here"
```
