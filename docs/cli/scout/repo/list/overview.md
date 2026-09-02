# docker scout repo list

List Docker Scout repositories. Shows all repositories in an organization. If ORG is not provided the default configured organization will be used.

## Usage

```text
docker scout repo list
```

## Options

| Option | Description |
|---|---|
| `--filter string` | Regular expression to filter repositories by name |
| `--only-disabled` | Filter to disabled repositories only |
| `--only-enabled` | Filter to enabled repositories only |
| `--only-registry string` | Filter to a specific registry only: hub.docker.com, ecr (AWS ECR) |
| `--org string` | Namespace of the Docker organization |
