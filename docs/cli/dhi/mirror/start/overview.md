# docker dhi mirror start

Start mirroring one or more Docker Hardened Images to your organization's registry. Repository mappings are specified as arguments (source, source,destination or ns/source,ns/dest).

## Usage

```text
docker dhi mirror start <mapping> [mapping...]
```

## Options

| Option | Description |
|---|---|
| `-d, --dependencies` | Mirrors any existing dependencies |
| `--json` | Output in JSON format |
| `--org string` | Docker Hub organization (overrides config) |
