# Add source-code, test, and PR workflows

## Summary

- Add `AGENTS.md` with a default workflow for implementing source changes, writing and verifying tests, and documenting pull requests.
- Replace project-specific community agent names with generic `test-writer` and `pr-writer` references.
- Require explicit user approval before pushing a branch or opening a pull request.

## Test plan

- [x] Reviewed the new guidance against the supplied screenshot.
- [x] Confirmed the instructions use generic agent references.
- [x] Ran `git diff --check`.
- [ ] Review the opened pull request and its checks.
