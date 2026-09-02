# Bind mounts

- [Docker documentation: Bind mounts](https://docs.docker.com/storage/bind-mounts/)
- Bind mounts are dependent on the directory structure and OS of the host machine

- Bind mounts have been around since the early days of Docker. Bind mounts have limited functionality compared to volumes. When you use a bind mount, a file or directory on the host machine is mounted into a container. The file or directory is referenced by its absolute path on the host machine. By contrast, when you use a volume, a new directory is created within Docker's storage directory on the host machine, and Docker manages that directory's contents.

- With bind mounts, we control the exact mountpoint on the host. We can use this to persist data, but is often used to provide additional data into containers. When working on an application, we can use a bind mount to mount our source code into the container to let it see code changes, respond, and let us see the changes right away.

- Using bind mounts is very common for local development setups. The advantage is that the dev machine doesn't need to have all of the build tools and environments installed. With a single docker run command, the dev environment is pulled and ready to go. We'll talk about Docker Compose in a future step, as this will help simplify our commands (we're already getting a lot of flags).

## Create Dev Mode Container

- [Starting a dev-mode container](https://docs.docker.com/get-started/06_bind_mounts/#starting-a-dev-mode-container)
