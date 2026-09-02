# docker agent run — Execution Flags

| Option | Description |
|---|---|
| `-a, --agent string` | Name of the agent to run (defaults to the team's first agent) |
| `--agent-picker string[="defaults"]` | Show a full-screen picker to choose an agent before launching. Optional comma-separated list of agent refs; "defaults" offers the built-in agents plus any configs in ~/.agents |
| `--app-name string` | Application name shown in the TUI in place of "docker agent" |
| `--attach string` | Attach an image file to the message |
| `--code-mode-tools` | Provide a single tool to call other tools via Javascript |
| `--dry-run` | Initialize the agent without executing anything |
| `--exec` | Execute without a TUI |
| `--fake string` | Replay AI responses from cassette file (for testing) |
| `--fake-stream int[=15]` | Simulate streaming with delay in ms between chunks (default 15ms if no value given) |
| `--json` | Output results in JSON format |
| `--lean` | Use a simplified TUI with minimal chrome |
| `--model stringArray` | Override agent model: [agent=]provider/model (repeatable) |
| `--models-gateway string` | Set the models gateway address |
| `--remote string` | Use remote runtime with specified address |
| `--safety string` | Safety mode for tool approval: strict (ask for everything), balanced (auto-approve safe calls), or autonomous (approve everything) |
| `--sandbox` | Run the agent inside a Docker sandbox (requires Docker Desktop with sandbox support) |
| `--sbx` | Prefer the sbx CLI backend when available (set --sbx=false to force docker sandbox) (default true) |
| `--template string` | Template image for the sandbox (default "docker/docker-agent-sbx-templates:latest") |
| `--theme string` | Preselect a TUI theme by name, or "auto" to match the terminal's light/dark background |
| `--working-dir string` | Set the working directory for the session (applies to tools and relative paths) |
| `-w, --worktree string[="auto"]` | Run the agent in a fresh git worktree of the working directory (isolates changes from your checkout). Optionally name it: --worktree=my-name |
| `--worktree-base string` | Branch the --worktree from this ref instead of the current HEAD (e.g. main, origin/main) |
| `--worktree-pr string` | Run the agent in a git worktree checked out on an existing GitHub pull request (number or URL). Requires the GitHub CLI (gh). |
| `--yolo` | Automatically approve all tool calls without prompting (same as --safety autonomous) |
