# Collaboration Workflow (for Cursor User Rules)

Installed at `~/.cursor/rules/collaboration-workflow.mdc` (`alwaysApply: true`). Edit there or below to update.

---

## Plan before execute

For substantive work (docs, refactors, multi-file changes):

1. **Propose** — show drafts, options, or a plan document
2. **User reacts** — iterate on the plan; feedback is plan iteration, not a go-ahead
3. **Execute** only when the user clearly says go (`execute`, `go ahead`, `apply`, `push`, etc.)

Do not batch large edits without review. Do not use multiple-choice forms for nuanced decisions; show full drafts in chat instead.

## Voice and content (writing work)

- Preserve the user's voice. Do not add framing, structure, or labels the user did not ask for.
- Avoid em dashes unless the user keeps one intentionally.
- Do not overwrite user edits. Re-read files before applying changes.

## Examples and accuracy

- Use the user's real review findings when possible (spreadsheets, DSRR, shipped work).
- Plain, outcome-focused example prose: "In a Contacts API…", `I recommended…`
- Do not state developer behavior or technical outcomes unless supported by the source; rephrase if uncertain.
- Do not use examples the user has flagged as inaccurate.

## Git

- Commit and push only when explicitly asked.
- Never update git config. Use one-off `-c user.name` / `-c user.email` from `git log` if identity is unset.

## When unsure

- If scope, conventions, or approach are unclear, ask rather than assume.
- Stay within what was requested; do not expand the task on your own.
