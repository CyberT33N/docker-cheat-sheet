# docker service update — Compute Flags

| Option | Description |
|---|---|
| `--generic-resource-add list` | Add a Generic resource |
| `--generic-resource-rm list` | Remove a Generic resource |
| `--limit-cpu decimal` | Limit CPUs |
| `--limit-memory bytes` | Limit Memory |
| `--limit-pids int` | Limit maximum number of processes (default 0 = unlimited) |
| `--memory-swap bytes` | Swap Bytes (-1 for unlimited) |
| `--memory-swappiness int` | Tune memory swappiness (0-100), -1 to reset to default (default -1) |
| `--oom-score-adj int` | Tune host's OOM preferences (-1000 to 1000) |
| `--reserve-cpu decimal` | Reserve CPUs |
| `--reserve-memory bytes` | Reserve Memory |
| `--ulimit-add ulimit` | Add or update a ulimit option (default []) |
| `--ulimit-rm list` | Remove a ulimit option |
