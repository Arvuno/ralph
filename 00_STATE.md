# Ralph - Repository State

**Analysis Date:** 2026-05-22
**Branch:** main
**Fork:** okwn/ralph (forked from snarktank/ralph)

---

## Repository Metadata

| Field | Value |
|-------|-------|
| Full Name | snarktank/ralph |
| Fork Name | okwn/ralph |
| Description | Ralph is an autonomous AI agent loop that runs AI coding tools (Amp or Claude Code) repeatedly until all PRD items are complete. |
| Language | TypeScript |
| License | MIT |
| Archived | No |
| Stars | 19,387 |
| Forks | 1,938 |
| Open Issues | 73 |
| Open PRs | 30 |
| Default Branch | main |

---

## What Ralph Does

Ralph is an autonomous coding agent system that:
1. Runs an AI coding tool (Amp or Claude Code) in a loop
2. Each iteration picks the highest-priority incomplete user story from `prd.json`
3. Implements one story per iteration with fresh context
4. Persists memory via git history, `progress.txt`, and `prd.json`
5. Outputs `<promise>COMPLETE</promise>` when all stories pass

---

## Project Structure

```
ralph/
├── ralph.sh           # Main loop script (supports --tool amp|claude)
├── prompt.md          # Amp agent instructions
├── CLAUDE.md          # Claude Code agent instructions
├── prd.json.example   # Example PRD format
├── progress.txt       # Learnings from iterations
├── AGENTS.md          # Agent instructions & patterns
├── flowchart/         # React Flow visualization (Node/React)
├── skills/
│   ├── prd/           # PRD generation skill
│   └── ralph/         # PRD-to-JSON conversion skill
├── .claude-plugin/    # Claude Code marketplace manifest
└── .github/workflows/deploy.yml  # GitHub Pages deployment
```

---

## CI/CD

- **deploy.yml**: Builds flowchart and deploys to GitHub Pages on push to main
- No test workflow configured (baseline tests not applicable - this is a script/template repo)

---

## Baseline Build Status

| Component | Status |
|-----------|--------|
| Flowchart TypeScript | ✅ Pass |
| Flowchart Build | ✅ Pass |
| ESLint | 8 vulnerabilities (3 moderate, 5 high) |

---

## Upstream Repository

- Parent: `snarktank/ralph`
- Fetched as `upstream` remote
- Last upstream push: 2026-02-02