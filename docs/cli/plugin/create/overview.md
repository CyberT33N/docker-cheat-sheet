# docker plugin create

Create a plugin from a rootfs and configuration. Plugin data directory must contain config.json and rootfs directory.

## Usage

```text
docker plugin create [OPTIONS] PLUGIN PLUGIN-DATA-DIR
```

## Options

| Option | Description |
|---|---|
| `--compress` | Compress the context using gzip |
