# docker scout recommendations

Display available base image updates and remediation recommendations. Analyzes the image and displays recommendations to refresh or update the base image. For each recommendation it shows a list of benefits like less vulnerabilities, smaller image, etc.

## Usage

```text
docker scout recommendations [IMAGE|DIRECTORY|ARCHIVE]
```

## Options

| Option | Description |
|---|---|
| `--only-refresh` | Only display base image refresh recommendations |
| `--only-update` | Only display base image update recommendations |
| `--org string` | Namespace of the Docker organization |
| `-o, --output string` | Write the report to a file |
| `--platform string` | Platform of image to analyze |
| `--ref string` | Reference to use if the provided tarball contains multiple references. Can only be used with archive |
| `--tag string` | Specify tag |
