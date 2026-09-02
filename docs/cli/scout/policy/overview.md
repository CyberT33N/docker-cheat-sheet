# docker scout policy

Evaluate local Rego policies against an image and display the results (experimental). Policies are loaded from the built-in default set, additional OCI policy bundles, and/or local .rego files and directories.

## Usage

```text
docker scout policy [IMAGE | REPO]
```

## Options

| Option | Description |
|---|---|
| `-e, --exit-code` | Return exit code '2' if policies are not met, '0' otherwise |
| `--only-policy strings` | Comma separated list of policies to evaluate |
| `--org string` | Namespace of the Docker organization |
| `-o, --output string` | Write the report to a file |
| `--platform string` | Platform of image to evaluate policies against |
| `--policy-bundle stringArray` | OCI reference of a policy bundle to evaluate (repeatable) |
| `--policy-config string` | Path or http(s) URL to a JSON file configuring policy enablement and inputs |
| `--policy-dir stringArray` | Path to a directory of local .rego policy files (repeatable) |
| `--policy-file stringArray` | Path or http(s) URL to a .rego policy file (repeatable) |
| `--result-file string` | Write the full Rego evaluation result of each evaluated policy to a JSON file |

## Subcommands

| Command | Description |
|---|---|
| `publish` | Package local Rego policies into an OCI bundle and push it to a registry (experimental) |
