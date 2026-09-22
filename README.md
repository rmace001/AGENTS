# AGENTS.md

## User Actions

Whenever you identify actions the user must take or information the user must provide:

- Add a `## Your actions` section.
- Use imperative checklist items.
- Start each item with a specific verb.
- Order items by time or priority.
- Group items by day or stage only when useful.
- Include only actions the user must perform.
- Omit background, rationale, progress updates, and agent-owned work.
- Omit the section when the user has no action to take.

For one-off requests, use this shorter prompt:

> List only my next actions. Use imperative checkboxes, order them by time or priority, and omit explanations.

----

## Asking the User

**Every decision, ambiguity, or confirmation is asked as a multiple-choice question.** Use the harness-specific question function: `AskUserQuestion`. In GitHub Copilot, it's `vscode_askQuestions`; in Hermes, it is the "clarify function"; in Codex, it is the "default_mode_request_user_input" function, AND needs to be enabled explicitly ("codex features enable default_mode_request_user_input")

Never ask an open-ended question when the options are enumerable, and never guess a user preference to keep the pipeline moving.


Contract for every question:

- The **first option is the recommendation**, and its label ends with `(Recommended)`.
- Labels are 1–5 words. The `description` states the consequence of choosing it — what happens next and what it costs.
- `header` ≤ 12 characters.
- `multiSelect: false` unless the choices genuinely combine.
- Do not add a "cancel" or "other" option — the harness always supplies free-text **Other**.
- **Batch all pending questions into a single call.** Do not drip-feed one at a time.
- Act on the answer. Do not re-ask or seek a second confirmation for the same decision.

Example Shape:

```
AskUserQuestion({
  questions: [{
    header: "Cleanup",
    question: "The planning documents are superseded by docs/spec/<feature-name>.md. Delete them?",
    multiSelect: false,
    options: [
      { label: "Delete (Recommended)", description: "Removed in this same commit and PR. Single source of truth." },
      { label: "Keep",                 description: "Planning history retained. Spec and planning docs will drift apart." }
    ]
  }]
})
```

If such a function is unavailable in the user's harness, render the identical options as a numbered list, recommended first, and wait for an explicit reply.

**Genuine dead-ends are not questions.** When there is no valid path forward — missing planning artifacts, empty PR body, wrong artifact filenames, etc. — stop and report plainly. Offering a choice between two failures is noise.
