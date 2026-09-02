# docker swarm join

Join a swarm as a node and/or manager.

## Usage

```text
docker swarm join [OPTIONS] HOST:PORT
```

## Options

| Option | Description |
|---|---|
| `--advertise-addr string` | Advertised address (format: "<ip\|interface>[:port]") |
| `--availability string` | Availability of the node ("active", "pause", "drain") (default "active") |
| `--data-path-addr string` | Address or interface to use for data path traffic (format: "<ip\|interface>") |
| `--listen-addr node-addr` | Listen address (format: "<ip\|interface>[:port]") (default 0.0.0.0:2377) |
| `--token string` | Token for entry into the swarm |
