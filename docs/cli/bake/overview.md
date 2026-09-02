# docker bake

Build from a file.

> `docker bake` is an alias of `docker buildx bake`.

## Usage

```text
docker buildx bake [OPTIONS] [TARGET...]
```

## Aliases

- `docker buildx bake`
- `docker buildx f`

## Options

| Option | Description |
|---|---|
| `--allow stringArray` | Allow build to access specified resources |
| `--builder string` | Override the configured builder instance |
| `--call string` | Set method for evaluating build ("check", "outline", "targets") (default "build") |
| `--check` | Shorthand for "--call=check" |
| `-D, --debug` | Enable debug logging |
| `-f, --file stringArray` | Build definition file |
| `--list string` | List targets or variables |
| `--load` | Shorthand for "--set=*.output=type=docker". Conditional. |
| `--metadata-file string` | Write build result metadata to a file |
| `--no-cache` | Do not use cache when building the image |
| `--policy stringArray` | Global policy evaluation options |
| `--print` | Print the options without building |
| `--progress string` | Set type of progress output ("auto", "none", "plain", "quiet", "rawjson", "tty") (default "auto") |
| `--provenance string` | Shorthand for "--set=*.attest=type=provenance" |
| `--pull` | Always attempt to pull all referenced images |
| `--push` | Shorthand for "--set=*.output=type=registry". Conditional. |
| `--sbom string` | Shorthand for "--set=*.attest=type=sbom" |
| `--set stringArray` | Override target value (e.g., "targetpattern.key=value") |
| `--var stringArray` | Set a variable value (e.g., "name=value") |

## Related

- [docker buildx bake](../buildx/bake/overview.md) — canonical command page
