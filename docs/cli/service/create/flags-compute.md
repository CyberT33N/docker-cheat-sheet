# docker service create — Compute Flags

| Option | Description |
|---|---|
| `--generic-resource list` | User defined resources |
| `--limit-cpu decimal` | Limit CPUs |
| `--limit-memory bytes` | Limit Memory |
| `--limit-pids int` | Limit maximum number of processes (default 0 = unlimited) |
| `--memory-swap bytes` | Swap Bytes (-1 for unlimited) |
| `--memory-swappiness int` | Tune memory swappiness (0-100), -1 to reset to default (default -1) |
| `--oom-score-adj int` | Tune host's OOM preferences (-1000 to 1000) |
| `--reserve-cpu decimal` | Reserve CPUs |
| `--reserve-memory bytes` | Reserve Memory |
| `--ulimit ulimit` | Ulimit options (default []) |
