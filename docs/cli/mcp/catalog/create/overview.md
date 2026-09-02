# docker mcp catalog create

Create a new catalog from server references, a profile, legacy catalog, or community registry.

## Usage

```text
docker mcp catalog create <oci-reference> [--server <ref1> --server <ref2> ...] [--from-profile <profile-id>] [--from-legacy-catalog <url>] [--from-community-registry <hostname>] [--title <title>]
```

## Options

| Option | Description |
|---|---|
| `--exclude stringArray` | Server name to exclude from the catalog (can be specified multiple times, only valid with --from-community-registry) |
| `--from-community-registry string` | Community registry hostname to fetch servers from (e.g. registry.modelcontextprotocol.io) |
| `--from-legacy-catalog string` | Legacy catalog URL to create the catalog from |
| `--from-profile string` | Profile ID to create the catalog from |
| `--server stringArray` | Server to include specified with a URI: https:// (MCP Registry reference) or docker:// (Docker Image reference) or catalog:// (Catalog reference) or file:// (Local file path). Can be specified multiple times. |
| `--title string` | Title of the catalog |
