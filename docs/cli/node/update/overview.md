# docker node update

Update a node.

## Usage

```text
docker node update [OPTIONS] NODE
```

## Options

| Option | Description |
|---|---|
| `--availability string` | Availability of the node ("active", "pause", "drain") |
| `--label-add list` | Add or update a node label ("key=value") |
| `--label-rm list` | Remove a node label if exists |
| `--role string` | Role of the node ("worker", "manager") |
