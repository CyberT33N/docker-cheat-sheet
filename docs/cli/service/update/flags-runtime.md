# docker service update — Runtime Flags

| Option | Description |
|---|---|
| `--cap-add list` | Add Linux capabilities |
| `--cap-drop list` | Drop Linux capabilities |
| `--credential-spec credential-spec` | Credential spec for managed service account (Windows only) |
| `--group-add list` | Add an additional supplementary user group to the container |
| `--group-rm list` | Remove a previously added supplementary user group from the container |
| `--health-cmd string` | Command to run to check health |
| `--health-interval duration` | Time between running the check (ms\|s\|m\|h) |
| `--health-retries int` | Consecutive failures needed to report unhealthy |
| `--health-start-interval duration` | Time between running the check during the start period (ms\|s\|m\|h) |
| `--health-start-period duration` | Start period for the container to initialize before counting retries towards unstable (ms\|s\|m\|h) |
| `--health-timeout duration` | Maximum time to allow one check to run (ms\|s\|m\|h) |
| `--init` | Use an init inside each service container to forward signals and reap processes |
| `--isolation string` | Service container isolation mode |
| `--no-healthcheck` | Disable any container-specified HEALTHCHECK |
| `--read-only` | Mount the container's root filesystem as read only |
| `--stop-grace-period duration` | Time to wait before force killing a container (ns\|us\|ms\|s\|m\|h) |
| `--stop-signal string` | Signal to stop the container |
| `--sysctl-add list` | Add or update a Sysctl option |
| `--sysctl-rm list` | Remove a Sysctl option |
| `-t, --tty` | Allocate a pseudo-TTY |
| `-u, --user string` | Username or UID (format: <name\|uid>[:<group\|gid>]) |
| `-w, --workdir string` | Working directory inside the container |
