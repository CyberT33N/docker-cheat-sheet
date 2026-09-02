# docker scout cves

Display CVEs identified in a software artifact. Analyzes a software artifact for vulnerabilities. If no image is specified, the most recently built image is used.

## Usage

```text
docker scout cves [OPTIONS] [IMAGE|DIRECTORY|ARCHIVE]
```

## Options

| Option | Description |
|---|---|
| `--details` | Print details on default text output |
| `--env string` | Name of environment |
| `--epss` | Display the EPSS scores and organize the package's CVEs according to their EPSS score |
| `--epss-percentile float32` | Exclude CVEs with EPSS scores less than the specified percentile (0 to 1) |
| `--epss-score float32` | Exclude CVEs with EPSS scores less than the specified value (0 to 1) |
| `-e, --exit-code` | Return exit code '2' if vulnerabilities are detected |
| `--format string` | Output format of the generated vulnerability report: packages, sarif, spdx, gitlab, markdown, sbom (default "packages") |
| `--ignore-base` | Filter out CVEs introduced from base image |
| `--ignore-suppressed` | Filter CVEs found in Scout exceptions based on the specified exception scope |
| `--locations` | Print package locations including file paths and layer diff_id |
| `--multi-stage` | Show packages from multi-stage Docker builds |
| `--only-base` | Only show CVEs introduced by the base image |
| `--only-cisa-kev` | Filter to CVEs listed in the CISA KEV catalog |
| `--only-cve-id strings` | Comma separated list of CVE ids (like CVE-2021-45105) to search for |
| `--only-fixed` | Filter to fixable CVEs |
| `--only-metric strings` | Comma separated list of CVSS metrics (like AV:N or PR:L) to filter CVEs by |
| `--only-package strings` | Comma separated regular expressions to filter packages by |
| `--only-package-type strings` | Comma separated list of package types (like apk, deb, rpm, npm, pypi, golang, etc) |
| `--only-severity strings` | Comma separated list of severities (critical, high, medium, low, unspecified) to filter CVEs by |
| `--only-stage strings` | Comma separated list of multi-stage Docker build stage names |
| `--only-unfixed` | Filter to unfixed CVEs |
| `--only-vex-affected` | Filter CVEs by VEX statements with status not affected |
| `--only-vuln-packages` | When used with --format=only-packages ignore packages with no vulnerabilities |
| `--org string` | Namespace of the Docker organization |
| `-o, --output string` | Write the report to a file |
| `--platform string` | Platform of image to analyze |
| `--ref string` | Reference to use if the provided tarball contains multiple references. Can only be used with archive |
| `--vex-author strings` | List of VEX statement authors to accept |
| `--vex-location strings` | File location of directory or file containing VEX statements |
