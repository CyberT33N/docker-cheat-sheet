# docker inspect

Return low-level information on Docker objects.

## Usage

```text
docker inspect [OPTIONS] NAME|ID [NAME|ID...]
```

## Options

| Option | Description |
|---|---|
| `-f, --format string` | Format output using a custom template ('json' or a Go template) |
| `-s, --size` | Display total file sizes if the type is container |
| `--type string` | Only inspect objects of the given type |
