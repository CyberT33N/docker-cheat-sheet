# docker create — System Flags

| Option | Description |
|---|---|
| `--annotation map` | Add an annotation to the container (passed through to the OCI runtime) (default map[]) |
| `--cap-add list` | Add Linux capabilities |
| `--cap-drop list` | Drop Linux capabilities |
| `--cgroup-parent string` | Optional parent cgroup for the container |
| `--cgroupns string` | Cgroup namespace to use (host\|private) |
| `--device list` | Add a host device to the container |
| `--device-cgroup-rule list` | Add a rule to the cgroup allowed devices list |
| `--gpus gpu-request` | GPU devices to add to the container ('all' to pass all GPUs) |
| `--group-add list` | Add additional groups to join |
| `--health-cmd string` | Command to run to check health |
| `--health-interval duration` | Time between running the check (ms\|s\|m\|h) (default 0s) |
| `--health-retries int` | Consecutive failures needed to report unhealthy |
| `--health-start-interval duration` | Time between running the check during the start period (ms\|s\|m\|h) (default 0s) |
| `--health-start-period duration` | Start period for the container to initialize before starting health-retries countdown (ms\|s\|m\|h) (default 0s) |
| `--health-timeout duration` | Maximum time to allow one check to run (ms\|s\|m\|h) (default 0s) |
| `--init` | Run an init inside the container that forwards signals and reaps processes |
| `--ipc string` | IPC mode to use |
| `--isolation string` | Container isolation technology |
| `-l, --label list` | Set meta data on a container |
| `--label-file list` | Read in a line delimited file of labels |
| `--log-driver string` | Logging driver for the container |
| `--log-opt list` | Log driver options |
| `--no-healthcheck` | Disable any container-specified HEALTHCHECK |
| `--pid string` | PID namespace to use |
| `--platform string` | Set platform if server is multi-platform capable |
| `--privileged` | Give extended privileges to this container |
| `--runtime string` | Runtime to use for this container |
| `--security-opt list` | Security Options |
| `--sysctl map` | Sysctl options (default map[]) |
| `--use-api-socket` | Bind mount Docker API socket and required auth |
| `-u, --user string` | Username or UID (format: <name\|uid>[:<group\|gid>]) |
| `--userns string` | User namespace to use |
| `--uts string` | UTS namespace to use |
