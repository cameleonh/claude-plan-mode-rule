# Claude Plan Mode Rule

A Claude Code rule that automatically triggers plan mode for complex tasks, so you never forget to plan before implementing.

## What It Does

When active, Claude will **automatically enter plan mode** instead of jumping straight into code when it detects:

- Tasks involving 3+ file modifications
- New feature additions or significant refactoring
- Architecture or design decisions
- Multi-step implementation sequences
- Ambiguous tasks with multiple valid approaches

Simple tasks (single-file edits, quick answers, formatting) proceed normally without plan mode.

## Installation

### Option 1: Copy manually

```bash
# Create rules directory if it doesn't exist
mkdir -p ~/.claude/rules

# Copy the rule file
cp plan-mode-policy.md ~/.claude/rules/plan-mode-policy.md
```

### Option 2: One-liner (macOS / Linux)

```bash
mkdir -p ~/.claude/rules && curl -o ~/.claude/rules/plan-mode-policy.md https://raw.githubusercontent.com/cameleonh/claude-plan-mode-rule/master/plan-mode-policy.md
```

### Option 3: One-liner (Windows PowerShell)

```powershell
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.claude\rules"; Invoke-WebRequest -Uri "https://raw.githubusercontent.com/cameleonh/claude-plan-mode-rule/master/plan-mode-policy.md" -OutFile "$env:USERPROFILE\.claude\rules\plan-mode-policy.md"
```

## Verification

After installation, restart Claude Code. The rule loads automatically — no additional configuration needed.

To verify:

```bash
cat ~/.claude/rules/plan-mode-policy.md
```

## Uninstall

```bash
rm ~/.claude/rules/plan-mode-policy.md
```

## How It Works

Claude Code automatically loads all `.md` files from `~/.claude/rules/` at session start. This rule instructs Claude to evaluate task complexity and enter plan mode proactively when the task exceeds the defined threshold.

## License

MIT
