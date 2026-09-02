# docker scout compare

Compare two images and display differences (experimental). Analyzes two images and displays a comparison of both. The main usage is to compare two versions of the same image. If no image is specified, the most recently built image will be used.

## Usage

```text
docker scout compare --to IMAGE|DIRECTORY|ARCHIVE [IMAGE|DIRECTORY|ARCHIVE]
```

## Aliases

- `compare`
- `diff`

## Options

| Option | Description |
|---|---|
| `-x, --exit-on strings` | Comma separated list of conditions to fail the action step if worse or changed, options are: vulnerability, policy, package |
| `--format string` | Output format of the generated vulnerability report: text, markdown, json (default "text") |
| `--hide-policies` | Hide policy status from the output |
| `--ignore-base` | Filter out CVEs introduced from base image |
| `--ignore-suppressed` | Filter CVEs found in Scout exceptions based on the specified exception scope |
| `--ignore-unchanged` | Filter out unchanged packages |
| `--multi-stage` | Show packages from multi-stage Docker builds |
| `--only-fixed` | Filter to fixable CVEs |
| `--only-package-type strings` | Comma separated list of package types (like apk, deb, rpm, npm, pypi, golang, etc) |
| `--only-policy strings` | Comma separated list of policies to evaluate |
| `--only-severity strings` | Comma separated list of severities (critical, high, medium, low, unspecified) to filter CVEs by |
| `--only-stage strings` | Comma separated list of multi-stage Docker build stage names |
| `--only-unfixed` | Filter to unfixed CVEs |
| `--only-vex-affected` | Filter CVEs by VEX statements with status not affected |
| `--org string` | Namespace of the Docker organization |
| `-o, --output string` | Write the report to a file |
| `--platform string` | Platform of image to analyze |
| `--policy-bundle stringArray` | OCI reference of a policy bundle to evaluate (repeatable) |
| `--policy-config string` | Path or http(s) URL to a JSON file configuring policy enablement and inputs |
| `--policy-dir stringArray` | Path to a directory of local .rego policy files (repeatable) |
| `--policy-file stringArray` | Path or http(s) URL to a .rego policy file (repeatable) |
| `--ref string` | Reference to use if the provided tarball contains multiple references. Can only be used with archive |
| `--to string` | Image, directory, or archive to compare to |
| `--to-env string` | Name of environment to compare to |
| `--to-latest` | Latest image processed to compare to |
| `--to-ref string` | Reference to use if the provided tarball contains multiple references. Can only be used with archive. |
| `--vex-author strings` | List of VEX statement authors to accept (default [<.*@docker.com>]) |
| `--vex-location strings` | File location of directory or file containing VEX statements |

## Artifact reference prefixes

- `image://` (default) use a local image, or fall back to a registry lookup
- `local://` use an image from the local image store (don't do a registry lookup)
- `registry://` use an image from a registry (don't use a local image)
- `oci-dir://` use an OCI layout directory
- `archive://` use a tarball archive, as created by docker save
- `fs://` use a local directory or file
- `sbom://` use an SBOM as SPDX file or in-toto attestation file with SPDX predicate or syft json SBOM file
