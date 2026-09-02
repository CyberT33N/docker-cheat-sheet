# docker service update — Orchestration Flags

| Option | Description |
|---|---|
| `--constraint-add list` | Add or update a placement constraint |
| `--constraint-rm list` | Remove a constraint |
| `-d, --detach` | Exit immediately instead of waiting for the service to converge |
| `--force` | Force update even if no changes require it |
| `--max-concurrent uint` | Number of job tasks to run concurrently (default equal to --replicas) |
| `--no-resolve-image` | Do not query the registry to resolve image digest and supported platforms |
| `--placement-pref-add pref` | Add a placement preference |
| `--placement-pref-rm pref` | Remove a placement preference |
| `-q, --quiet` | Suppress progress output |
| `--replicas uint` | Number of tasks |
| `--replicas-max-per-node uint` | Maximum number of tasks per node (default 0 = unlimited) |
| `--restart-condition string` | Restart when condition is met ("none", "on-failure", "any") |
| `--restart-delay duration` | Delay between restart attempts (ns\|us\|ms\|s\|m\|h) |
| `--restart-max-attempts uint` | Maximum number of restarts before giving up |
| `--restart-window duration` | Window used to evaluate the restart policy (ns\|us\|ms\|s\|m\|h) |
| `--rollback` | Rollback to previous specification |
| `--rollback-delay duration` | Delay between task rollbacks (ns\|us\|ms\|s\|m\|h) |
| `--rollback-failure-action string` | Action on rollback failure ("pause", "continue") |
| `--rollback-max-failure-ratio float` | Failure rate to tolerate during a rollback |
| `--rollback-monitor duration` | Duration after each task rollback to monitor for failure (ns\|us\|ms\|s\|m\|h) |
| `--rollback-order string` | Rollback order ("start-first", "stop-first") |
| `--rollback-parallelism uint` | Maximum number of tasks rolled back simultaneously (0 to roll back all at once) |
| `--update-delay duration` | Delay between updates (ns\|us\|ms\|s\|m\|h) |
| `--update-failure-action string` | Action on update failure ("pause", "continue", "rollback") |
| `--update-max-failure-ratio float` | Failure rate to tolerate during an update |
| `--update-monitor duration` | Duration after each task update to monitor for failure (ns\|us\|ms\|s\|m\|h) |
| `--update-order string` | Update order ("start-first", "stop-first") |
| `--update-parallelism uint` | Maximum number of tasks updated simultaneously (0 to update all at once) |
| `--with-registry-auth` | Send registry authentication details to swarm agents |
