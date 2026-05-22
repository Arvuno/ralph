# Ralph - Selected 5 PR Plan

## Selected Candidates

| Priority | Issue | Title | Rationale |
|----------|-------|-------|-----------|
| 1 | **#149** | fix(flowchart): useCallback deps for handleNext/handlePrev/handleReset | Clean bug fix with obvious solution |
| 2 | **#139** | bug: useCallback missing deps in App.tsx cause ESLint failure | Detailed bug report, related to #149 |
| 3 | **#151** | Add Codex CLI runner support | Well-scoped feature addition |
| 4 | **#148** | Enabling to pass --model and --effort when run ./ralph | Simple parameter enhancement |
| 5 | **#143** | docs: clarify Ralph runner setup and output paths | Documentation improvement |

---

## PR #149: Fix useCallback deps

**File:** `flowchart/src/App.tsx`

**Changes Needed:**
- Wrap `getNodes` in `useCallback` with empty deps
- Wrap `getEdgeVisibility` in `useCallback` with empty deps  
- Add `getNodes` and `getEdgeVisibility` to `handleNext` and `handlePrev` deps
- Add `getNodes` to `handleReset` deps

**Acceptance Criteria:**
- `npm run lint` passes in flowchart/
- Flowchart still builds correctly

---

## PR #139: Fix ESLint failure from stale closures

**File:** `flowchart/src/App.tsx`

**Related to:** #149 (issue #149 is the PR that fixes #139)

**Changes Needed:**
- Same as #149 - this is the same fix, different framing
- Issue #139 provides detailed root cause analysis

**Note:** #149 was filed AFTER #139 and references it. They likely address the same root cause. Recommend implementing once and close both.

---

## PR #151: Add Codex CLI runner support

**Files to add/modify:**
- `ralph.sh` - Add `--tool codex` option
- `CODEX.md` - New prompt template for Codex
- `README.md` - Document Codex support

**Changes Needed:**
```bash
# In ralph.sh:
--tool codex)
  TOOL="codex"
  ;;
# Codex invocation:
OUTPUT=$(codex < "$SCRIPT_DIR/CODEX.md" 2>&1 | tee /dev/stderr) || true
```

**Acceptance Criteria:**
- `bash -n ralph.sh` passes
- Codex support documented in README
- Codex prompt template follows same pattern as prompt.md/CLAUDE.md

---

## PR #148: Enable --model and --effort parameters

**File:** `ralph.sh`

**Changes Needed:**
- Parse `--model` and `--effort` arguments
- Pass them through to the AI tool invocation

**Example:**
```bash
--model)
  MODEL="$2"
  shift 2
  ;;
--effort)
  EFFORT="$2"
  shift 2
  ;;
```

**Acceptance Criteria:**
- `bash -n ralph.sh` passes
- New parameters documented in README

---

## PR #143: Clarify Ralph runner setup and output paths

**File:** `README.md`

**Changes Needed:**
- Clarify that skills should be installed globally or per-project
- Document where prd.json and progress.txt are created
- Add clearer troubleshooting for common setup issues

**Sections to enhance:**
- Setup section (Option 1, 2, 3)
- Workflow section with clearer path expectations
- Debugging section with more examples

---

## Execution Order

1. **#149/#139** - Both fix the same App.tsx issue; implement once
2. **#148** - Simple parameter enhancement to ralph.sh
3. **#151** - New tool support (slightly larger scope)
4. **#143** - Documentation improvement (last)

---

## Testing Strategy

For each PR:
1. `bash -n ralph.sh` for shell script changes
2. `cd flowchart && npm run lint` for React changes
3. `cd flowchart && npm run build` to verify build
4. Manual verification of new features where applicable

---

## Notes

- The flowchart build has 8 vulnerabilities (3 moderate, 5 high) - not in scope for these PRs
- No test suite currently exists for ralph.sh itself
- The skills are well-documented but could use additional examples