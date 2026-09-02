# docker scout environment

Manage environments (experimental). Lists the environments and records images to it. Once recorded, environments can be referred to by their name, e.g. in the docker scout compare command using --to-env.

## Usage

```text
docker scout environment [ENVIRONMENT] [IMAGE]
```

## Aliases

- `environment`
- `env`

## Options

| Option | Description |
|---|---|
| `--org string` | Namespace of the Docker organization |
| `-o, --output string` | Write the report to a file |
| `--platform string` | Platform of image to record |
