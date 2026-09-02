# docker scout push

Push an image or image index to Docker Scout.

## Usage

```text
docker scout push IMAGE
```

## Options

| Option | Description |
|---|---|
| `--author string` | Name of the author of the image |
| `--dry-run` | Do not push the image but process it |
| `--org string` | Namespace of the Docker organization to which image will be pushed |
| `-o, --output string` | Write the report to a file |
| `--platform string` | Platform of image to be pushed |
| `--sbom` | Create and upload SBOMs |
| `--secrets` | Scan for secrets in the image |
| `--timestamp string` | Timestamp of image or tag creation |
