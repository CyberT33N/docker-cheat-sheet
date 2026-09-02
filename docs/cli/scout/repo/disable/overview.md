# docker scout repo disable

Disable Docker Scout on repositories.

## Usage

```text
docker scout repo disable [REPOSITORY]
```

## Options

| Option | Description |
|---|---|
| `--all` | Disable all repositories of the organization. Can not be used with --filter. |
| `--filter string` | Regular expression to filter repositories by name |
| `--integration string` | Name of the integration to use for enabling an image |
| `--org string` | Namespace of the Docker organization |
| `--registry string` | Container Registry |
