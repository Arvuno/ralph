# Contributing to Ralph

Thank you for your interest in contributing to Ralph!

## Development Setup

### Prerequisites

- [Amp CLI](https://ampcode.com) or [Claude Code](https://docs.anthropic.com/en/docs/claude-code)
- `jq` installed (`brew install jq` on macOS, `apt install jq` on Linux)
- A git repository for your project

### Local Development

1. Fork the repository
2. Clone your fork:
   ```bash
   git clone https://github.com/<your-username>/ralph.git
   cd ralph
   ```
3. Install prerequisites:
   ```bash
   # Amp (default)
   brew install amp # macOS
   # or: curl -fsSL https://ampcode.com/install.sh | sh # Linux

   # Claude Code
   npm install -g @anthropic-ai/claude-code

   # jq
   brew install jq # macOS
   sudo apt install jq # Linux (Debian/Ubuntu)
   ```

## Testing

Run Ralph locally on a test project:

```bash
# Create a test PRD
mkdir -p my-test-project
cd my-test-project
git init

# Copy Ralph files
mkdir -p scripts/ralph
cp /path/to/ralph/ralph.sh scripts/ralph/
cp /path/to/ralph/prompt.md scripts/ralph/

# Create a test prd.json
echo '{"userStories": [{"id": "1", "title": "Test story", "branchName": "test", "passes": false}]}' > prd.json

# Run Ralph (limited iterations)
./scripts/ralph/ralph.sh 2
```

## Code Style

- Shell scripts: Use `shellcheck` for linting
- Documentation: Markdown format, 80-character line length

## Submitting Changes

1. Create a feature branch from `main`
2. Make your changes
3. Test locally
4. Submit a pull request

## Debugging

```bash
# Check which stories are done
cat prd.json | jq '.userStories[] | {id, title, passes}'

# See learnings from previous iterations
cat progress.txt

# Check git history
git log --oneline -10
```