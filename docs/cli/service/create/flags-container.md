# docker service create — Container Flags

| Option | Description |
|---|---|
| `--cap-add list` | Add Linux capabilities |
| `--cap-drop list` | Drop Linux capabilities |
| `--config config` | Specify configurations to expose to the service |
| `--container-label list` | Container labels |
| `--credential-spec credential-spec` | Credential spec for managed service account (Windows only) |
| `--entrypoint command` | Overwrite the default ENTRYPOINT of the image |
| `-e, --env list` | Set environment variables |
| `--env-file list` | Read in a file of environment variables |
| `--group list` | Set one or more supplementary user groups for the container |
| `--health-cmd string` | Command to run to check health |
| `--health-interval duration` | Time between running the check (ms\|s\|m\|h) |
| `--health-retries int` | Consecutive failures needed to report unhealthy |
| `--health-start-interval duration` | Time between running the check during the start period (ms\|s\|m\|h) |
| `--health-start-period duration` | Start period for the container to initialize before counting retries towards unstable (ms\|s\|m\|h) |
| `--health-timeout duration` | Maximum time to allow one check to run (ms\|s\|m\|h) |
| `--init` | Use an init inside each service container to forward signals and reap processes |
| `--isolation string` | Service container isolation mode |
| `-l, --label list` | Service labels |
| `--log-driver string` | Logging driver for service |
| `--log-opt list` | Logging driver options |
| `--mount mount` | Attach a filesystem mount to the service |
| `--no-healthcheck` | Disable any container-specified HEALTHCHECK |
| `--read-only` | Mount the container's root filesystem as read only |
| `--secret secret` | Specify secrets to expose to the service |
| `--stop-grace-period duration` | Time to wait before force killing a container (ns\|us\|ms\|s\|m\|h) (default 10s) |
| `--stop-signal string` | Signal to stop the container |
| `--sysctl list` | Sysctl options |
| `-t, --tty` | Allocate a pseudo-TTY |
| `-u, --user string` | Username or UID (format: <name\|uid>[:<group\|gid>]) |
| `-w, --workdir string` | Working directory inside the container |
