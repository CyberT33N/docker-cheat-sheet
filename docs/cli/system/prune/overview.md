# docker system prune

Remove unused data.

## Usage

```text
docker system prune [OPTIONS]
```

## Options

| Option | Description |
|---|---|
| `-a, --all` | Remove all unused images not just dangling ones |
| `--filter filter` | Provide filter values (e.g. "label=<key>=<value>") |
| `-f, --force` | Do not prompt for confirmation |
| `--volumes` | Prune anonymous volumes |
