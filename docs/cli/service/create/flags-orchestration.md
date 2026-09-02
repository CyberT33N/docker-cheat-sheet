# docker service create — Orchestration Flags

| Option | Description |
|---|---|
| `--constraint list` | Placement constraints |
| `-d, --detach` | Exit immediately instead of waiting for the service to converge |
| `--max-concurrent uint` | Number of job tasks to run concurrently (default equal to --replicas) |
| `--mode string` | Service mode ("replicated", "global", "replicated-job", "global-job") (default "replicated") |
| `--name string` | Service name |
| `--no-resolve-image` | Do not query the registry to resolve image digest and supported platforms |
| `--placement-pref pref` | Add a placement preference |
| `-q, --quiet` | Suppress progress output |
| `--replicas uint` | Number of tasks |
| `--replicas-max-per-node uint` | Maximum number of tasks per node (default 0 = unlimited) |
| `--restart-condition string` | Restart when condition is met ("none", "on-failure", "any") (default "any") |
| `--restart-delay duration` | Delay between restart attempts (ns\|us\|ms\|s\|m\|h) (default 5s) |
| `--restart-max-attempts uint` | Maximum number of restarts before giving up |
| `--restart-window duration` | Window used to evaluate the restart policy (ns\|us\|ms\|s\|m\|h) |
| `--rollback-delay duration` | Delay between task rollbacks (ns\|us\|ms\|s\|m\|h) (default 0s) |
| `--rollback-failure-action string` | Action on rollback failure ("pause", "continue") (default "pause") |
| `--rollback-max-failure-ratio float` | Failure rate to tolerate during a rollback (default 0) |
| `--rollback-monitor duration` | Duration after each task rollback to monitor for failure (ns\|us\|ms\|s\|m\|h) (default 5s) |
| `--rollback-order string` | Rollback order ("start-first", "stop-first") (default "stop-first") |
| `--rollback-parallelism uint` | Maximum number of tasks rolled back simultaneously (0 to roll back all at once) (default 1) |
| `--update-delay duration` | Delay between updates (ns\|us\|ms\|s\|m\|h) (default 0s) |
| `--update-failure-action string` | Action on update failure ("pause", "continue", "rollback") (default "pause") |
| `--update-max-failure-ratio float` | Failure rate to tolerate during an update (default 0) |
| `--update-monitor duration` | Duration after each task update to monitor for failure (ns\|us\|ms\|s\|m\|h) (default 5s) |
| `--update-order string` | Update order ("start-first", "stop-first") (default "stop-first") |
| `--update-parallelism uint` | Maximum number of tasks updated simultaneously (0 to update all at once) (default 1) |
| `--with-registry-auth` | Send registry authentication details to swarm agents |
