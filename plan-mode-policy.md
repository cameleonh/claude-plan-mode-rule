# Plan Mode Policy

Always enter plan mode before any task that meets these criteria:

## Auto-Enter Triggers

Enter plan mode proactively (without waiting for user request) when:

- **Modifying 3+ files** in a single task
- **Adding new features** or significant refactoring
- **Architecture or design decisions** are involved
- **Multi-step implementation sequences** (3+ sequential operations)
- **Unsure about approach** — when multiple valid approaches exist

## Skip Plan Mode

These can proceed directly:

- Simple bug fixes (single file, clear cause)
- Single-file edits
- Quick answers or explanations
- Formatting or style tweaks
- Adding comments or docs to existing code

## Behavior

- Do NOT wait for the user to request plan mode — judge proactively and enter automatically
- Use `EnterPlanMode` tool when triggered
- When in doubt, prefer plan mode over skipping it
