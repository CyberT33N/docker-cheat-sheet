# docker scout repo enable

Enable Docker Scout on repositories.

## Usage

```text
docker scout repo enable [REPOSITORY]
```

## Options

| Option | Description |
|---|---|
| `--all` | Enable all repositories of the organization. Can not be used with --filter. |
| `--filter string` | Regular expression to filter repositories by name |
| `--integration string` | Name of the integration to use for enabling an image |
| `--org string` | Namespace of the Docker organization |
| `--registry string` | Container Registry |
