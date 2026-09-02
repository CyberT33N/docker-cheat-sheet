# docker model package

Package a model into a Docker Model OCI artifact. By default, the packaged artifact is loaded into the local Model Runner content store. Use --push to publish the model to a registry instead.

## Usage

```text
docker model package (--gguf <path> | --safetensors-dir <path> | --dduf <path> | --from <model>) [--license <path>...] [--mmproj <path>] [--context-size <tokens>] [--push] MODEL
```

## Options

| Option | Description |
|---|---|
| `--chat-template string` | absolute path to chat template file (must be Jinja format) |
| `--context-size uint` | context size in tokens |
| `--dduf string` | absolute path to DDUF archive file (Diffusers Unified Format) |
| `--format string` | output artifact format: "docker" (default) or "cncf" (CNCF ModelPack spec) (default "docker") |
| `--from string` | reference to an existing model to repackage |
| `--gguf string` | absolute path to gguf file |
| `-l, --license stringArray` | absolute path to a license file |
| `--mmproj string` | absolute path to multimodal projector file |
| `--push` | push to registry (if not set, the model is loaded into the Model Runner content store) |
| `--safetensors-dir string` | absolute path to directory containing safetensors files and config |
