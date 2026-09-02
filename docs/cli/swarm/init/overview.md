# docker swarm init

Initialize a swarm. The Docker Engine targeted by this command becomes a manager in the newly created single-node swarm.

- [Docker documentation: docker swarm init](https://docs.docker.com/reference/cli/docker/swarm/init/)

## Usage

```text
docker swarm init [OPTIONS]
```

## Options

| Option | Default | Description |
|---|---|---|
| `--advertise-addr` | | Advertised address (format: `<ip\|interface>[:port]`) |
| `--availability string` | | Availability of the node ("active", "pause", "drain") |
| `--data-path-addr` | | Address or interface to use for data path traffic (format: `<ip\|interface>`) |
| `--data-path-port` | | Port number to use for data path traffic (1024 - 49151). If no value is set or is set to 0, the default port (4789) is used |
| `--default-addr-pool` | | Default address pool in CIDR format |
| `--default-addr-pool-mask-length` | `24` | Default address pool subnet mask length |
| `--dispatcher-heartbeat` | `5s` | Dispatcher heartbeat period (ns\|us\|ms\|s\|m\|h) |
| `--external-ca` | | Specifications of one or more certificate signing endpoints |
| `--force-new-cluster` | | Force create a new cluster from current state |
| `--listen-addr` | `0.0.0.0:2377` | Listen address (format: `<ip\|interface>[:port]`) |
| `--max-snapshots` | | Number of additional Raft snapshots to retain |
| `--snapshot-interval` | `10000` | Number of log entries between Raft snapshots |
| `--task-history-limit` | `5` | Task history retention limit |
