# docker extension init

Create a new Docker Extension based on a template.

## Usage

```text
docker extension init [FOLDER]
```

## Options

| Option | Description |
|---|---|
| `--image-repo string` | Image Repository where the extension will be pushed (required with --quiet) |
| `-q, --quiet` | Use quiet to not prompt questions and use default values as answers. |
| `--title string` | Title of your extension as it will appear in the Marketplace (required with --quiet) |
| `--version string` | Minimum extension SDK version the extension is compatible with |
