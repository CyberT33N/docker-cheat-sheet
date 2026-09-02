# docker run — Compute Flags

| Option | Description |
|---|---|
| `--blkio-weight uint16` | Block IO (relative weight), between 10 and 1000, or 0 to disable (default 0) |
| `--blkio-weight-device list` | Block IO weight (relative device weight) (default []) |
| `-c, --cpu-shares int` | CPU shares (relative weight) |
| `--cpus decimal` | Number of CPUs |
| `--cpu-period int` | Limit CPU CFS (Completely Fair Scheduler) period |
| `--cpu-quota int` | Limit CPU CFS (Completely Fair Scheduler) quota |
| `--cpu-rt-period int` | Limit CPU real-time period in microseconds |
| `--cpu-rt-runtime int` | Limit CPU real-time runtime in microseconds |
| `--cpuset-cpus string` | CPUs in which to allow execution (0-3, 0,1) |
| `--cpuset-mems string` | MEMs in which to allow execution (0-3, 0,1) |
| `--device-read-bps list` | Limit read rate (bytes per second) from a device (default []) |
| `--device-read-iops list` | Limit read rate (IO per second) from a device (default []) |
| `--device-write-bps list` | Limit write rate (bytes per second) to a device (default []) |
| `--device-write-iops list` | Limit write rate (IO per second) to a device (default []) |
| `-m, --memory bytes` | Memory limit |
| `--memory-reservation bytes` | Memory soft limit |
| `--memory-swap bytes` | Swap limit equal to memory plus swap: '-1' to enable unlimited swap |
| `--memory-swappiness int` | Tune container memory swappiness (0 to 100) (default -1) |
| `--oom-kill-disable` | Disable OOM Killer |
| `--oom-score-adj int` | Tune host's OOM preferences (-1000 to 1000) |
| `--pids-limit int` | Tune container pids limit (set -1 for unlimited) |
| `--shm-size bytes` | Size of /dev/shm |
| `--ulimit ulimit` | Ulimit options (default []) |
