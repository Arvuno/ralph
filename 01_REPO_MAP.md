# Ralph - Repository Map

## File Structure

```
ralph/
├── README.md              # Main documentation (239 lines)
├── LICENSE                # MIT License
├── ralph.sh               # Main loop script (113 lines, bash)
├── prompt.md              # Amp instructions (108 lines)
├── CLAUDE.md              # Claude Code instructions (104 lines)
├── prd.json.example       # Example PRD JSON (64 lines)
├── progress.txt           # Progress log (created on run)
├── AGENTS.md              # Agent instructions (47 lines)
├── ralph-flowchart.png    # Flowchart screenshot
├── ralph.webp             # Ralph logo
├── .gitignore
├── .claude-plugin/
│   ├── plugin.json        # Plugin manifest
│   └── marketplace.json  # Marketplace listing
├── .github/workflows/
│   └── deploy.yml         # GitHub Pages deployment
├── flowchart/             # React Flow visualization
│   ├── package.json       # Node 20, React 19, @xyflow/react 12
│   ├── vite.config.ts
│   ├── tsconfig.json
│   ├── index.html
│   └── src/
│       ├── App.tsx        # Main React component (React Flow)
│       ├── App.css
│       ├── main.tsx
│       └── index.css
└── skills/
    ├── prd/SKILL.md       # PRD generator skill (241 lines)
    └── ralph/SKILL.md     # PRD-to-JSON converter (258 lines)
```

---

## Key Files Overview

### Core Loop Files

| File | Purpose | Lines |
|------|---------|-------|
| `ralph.sh` | Bash loop spawning AI instances | 113 |
| `prompt.md` | Amp agent instructions | 108 |
| `CLAUDE.md` | Claude Code agent instructions | 104 |
| `prd.json.example` | Example task list format | 64 |

### Documentation

| File | Purpose | Lines |
|------|---------|-------|
| `README.md` | Main docs, setup instructions | 239 |
| `AGENTS.md` | Ralph agent instructions | 47 |

### Skills (Amp/Claude Code Plugins)

| File | Purpose | Lines |
|------|---------|-------|
| `skills/prd/SKILL.md` | Generate PRD from description | 241 |
| `skills/ralph/SKILL.md` | Convert PRD to prd.json format | 258 |

### Flowchart (React Flow)

| File | Purpose |
|------|---------|
| `flowchart/src/App.tsx` | Main flowchart visualization |
| `flowchart/package.json` | React 19, TypeScript, vite |

---

## Command Reference

```bash
# Run Ralph
./ralph.sh [max_iterations]         # Default Amp
./ralph.sh --tool claude [n]        # Claude Code

# Flowchart
cd flowchart && npm run dev         # Development
cd flowchart && npm run build       # Production build
```

---

## Git History Summary

| Commit | Message |
|--------|---------|
| 6c53cb0 | fix(skill): enfore options indentation in prd SKILL.md (#64) |
| 800c221 | feat: add Claude Code marketplace support (#9) |
| 03ed99b | Add MIT License |
| ed82d00 | Merge pull request #2 from denen99/main |
| ef93603 | updated CLAUDE.md |

**Note:** Fork is behind upstream (cloned from fork, not origin/main)

---

## Dependency Graph

```
ralph.sh
├── prompt.md (Amp) / CLAUDE.md (Claude)
├── prd.json (task list)
├── progress.txt (learnings)
└── External tools: amp CLI / claude CLI

flowchart/
├── @xyflow/react (React Flow)
├── react, react-dom (v19)
├── vite (build)
└── typescript
```

---

## Issue/PR Tags

**No labels used** on issues or PRs in this repository.

---

## Upstream Issues (30 open)

Top recent issues:
- #151: Add Codex CLI runner support
- #150: Codex cli loop
- #149: fix(flowchart): useCallback deps
- #148: Enabling to pass --model and --effort when run ./ralph
- #147: feat: wait on Claude rate limits
- #146: feat: Add ability to run via copilot

---

## CI/CD Pipeline

```yaml
# .github/workflows/deploy.yml
trigger: push to main + manual
node-version: 20
steps:
  1. Checkout
  2. Setup Node 20 with npm cache
  3. npm ci (in flowchart/)
  4. npm run build (in flowchart/)
  5. Configure GitHub Pages
  6. Upload artifact
  7. Deploy to GitHub Pages
```