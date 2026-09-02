# docker scout quickview

Quick overview of an image. Displays a summary of the vulnerabilities in the image and the vulnerabilities from the base image. If available it also displays base image refresh and update recommendations. If no image is specified, the most recently built image is used.

## Usage

```text
docker scout quickview [IMAGE|DIRECTORY|ARCHIVE]
```

## Aliases

- `quickview`
- `qv`

## Options

| Option | Description |
|---|---|
| `--env string` | Name of the environment |
| `--ignore-suppressed` | Filter CVEs found in Scout exceptions based on the specified exception scope |
| `--latest` | Latest indexed image |
| `--only-policy strings` | Comma separated list of policies to evaluate |
| `--only-vex-affected` | Filter CVEs by VEX statements with status not affected |
| `--org string` | Namespace of the Docker organization |
| `-o, --output string` | Write the report to a file |
| `--platform string` | Platform of image to analyze |
| `--policy-bundle stringArray` | OCI reference of a policy bundle to evaluate (repeatable) |
| `--policy-config string` | Path or http(s) URL to a JSON file configuring policy enablement and inputs |
| `--policy-dir stringArray` | Path to a directory of local .rego policy files (repeatable) |
| `--policy-file stringArray` | Path or http(s) URL to a .rego policy file (repeatable) |
| `--ref string` | Reference to use if the provided tarball contains multiple references. Can only be used with archive |
| `--vex-author strings` | List of VEX statement authors to accept (default [<.*@docker.com>]) |
| `--vex-location strings` | File location of directory or file containing VEX statements |
