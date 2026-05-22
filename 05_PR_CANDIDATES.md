# Ralph - PR Candidates

## Open Issues Analysis (30 total)

### High-Quality Candidates

| # | Title | Priority | Complexity | Labels | Notes |
|---|-------|----------|------------|--------|-------|
| **151** | Add Codex CLI runner support | High | Medium | None | Well-documented, clear scope, ~4 files |
| **149** | fix(flowchart): useCallback deps for handleNext/handlePrev/handleReset | High | Low | None | Clear bug fix, already includes solution approach |
| **139** | bug: useCallback missing deps in App.tsx cause stale closure | High | Low | None | Detailed bug report with root cause & fix |
| **147** | feat: wait on Claude rate limits | High | Medium | None | Introduces retry loop + Python utility + test script |
| **148** | Enabling to pass --model and --effort when run ./ralph | Medium | Low | None | Simple parameter passing enhancement |

### Feature Enhancement Candidates

| # | Title | Priority | Complexity | Notes |
|---|-------|----------|------------|-------|
| **138** | feat: add support for Gemini CLI | Medium | Medium | Similar pattern to Claude Code support |
| **146** | feat: Add ability to run via copilot | Medium | Medium | Alternative tool integration |
| **132** | Add OpenRouter support (--tool openrouter) | Medium | Medium | Alternative tool integration |

### Documentation Candidates

| # | Title | Priority | Complexity | Notes |
|---|-------|----------|------------|-------|
| **143** | docs: clarify Ralph runner setup and output paths | Medium | Low | Documentation improvement |
| **133** | Consider listing in awesome-codex-plugins | Low | Low | Community listing |
| **135** | [codex] add Ralph Codex adaptation docs | Medium | Low | Documentation for Codex users |

### Duplicate/Unclear Candidates

| # | Title | Notes |
|---|-------|-------|
| **150** | Codex cli loop | Likely duplicate of #151 (same author, day apart) |
| **134** | Ralph/easier to use | Vague, no concrete scope |

---

## PR Quality Assessment

**Most Active Issues:**
- #147 (7 comments) - Rate limiting feature, active discussion
- #139 (2 comments) - Bug report with detailed analysis

**Best Candidates for Implementation:**
1. **#149** - Clear fix, low risk, small scope
2. **#139** - Detailed bug report, could build on #149's approach
3. **#151** - Well-scoped feature addition
4. **#148** - Simple enhancement
5. **#147** - Larger feature but well-described

---

## Skills Structure

The repo also has skills that could be improved:
- `skills/prd/SKILL.md` - PRD generation (241 lines)
- `skills/ralph/SKILL.md` - PRD-to-JSON conversion (258 lines)

Both include detailed patterns and examples that could be enhanced.