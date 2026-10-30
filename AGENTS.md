# Implementing Source Code

Default process when the user gives no detailed instructions.

- **Goal:** Discover the relevant code and make the requested source change. Nothing else.
- **Process:**
  1. **Discover:** Read the code in scope and its consumers; for new code, also read a comparable existing feature. Find the exact files and lines where the change belongs.
  2. **Plan:** Before editing, list every file and function you will touch, and why.
  3. **Implement:** Make the smallest change that satisfies the request, following the patterns in the code and the coding standards in `CONTRIBUTING.md`.
  4. **Self-check:** Re-read the diff for correctness, scope, side effects, and downstream impact, and run the relevant type-check or static checks (for example, `npx tsc --noEmit` when applicable).
  5. **Test:** When behavior in `src/` changes, or tests are requested or broken, follow **Implementing Tests**.
- **Ask the user** (see **Asking the User**) if the request is ambiguous or the change needs files outside its scope. Do not improvise.
- **Report:** The plan, each changed file with what changed and why, the downstream consumers checked, and the behaviors that need tests.

## Implementing Tests

- **Goal:** Make the test suite protect the implemented behavior in a maintainable way.
- **Invokes:** `test-writer`. Run its full workflow, including baseline verification and any required cleanup or reporter restoration.
- **Report:** The skill's completion report, with every command run and its result.

## Documenting Pull Requests (PRs)

- **Goal:** Produce `PR.md` for the committed branch.
- **Invokes:** `pr-writer`. Run every phase, but push and open the PR only after the user explicitly approves.
- **Must not:** Edit code or tests.
- **Report:** The PR title, the `PR.md` path, and the skill's completion summary.
