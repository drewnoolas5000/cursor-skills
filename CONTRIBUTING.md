# Contributing to Gusto Cursor Skills

Thank you for contributing! This guide will help you add new skills that benefit the whole team.

---

## Before You Start

### Is This a Good Skill Candidate?

Ask yourself:

| Question | If Yes... |
|----------|-----------|
| Do I explain this to Cursor more than once a week? | ✅ Great candidate! |
| Would other teams find this useful? | ✅ Share it here |
| Is this specific to one project? | 🤔 Maybe keep it personal |
| Does it need production secrets? | ❌ Rethink the approach |

---

## Adding a New Skill

### Step 1: Choose the Right Category

| Category | Put it here if... |
|----------|-------------------|
| `beginner/` | Simple formatting or explanation skill |
| `intermediate/` | Multi-step analysis or review pattern |
| `workflows/` | Uses external data (Redash, APIs, etc.) |
| `security/` | Security scanning or threat analysis |

### Step 2: Use the Template

Start with the appropriate template from `skills/templates/`:

```bash
cp skills/templates/basic-skill-template.mdc skills/beginner/my-new-skill.mdc
```

### Step 3: Follow the File Format

Every skill must have:

```markdown
---
description: Clear one-line description (shown in Cursor's picker)
globs: [optional file patterns]
alwaysApply: false
---

# Skill Name

## Overview
What problem does this solve? Who should use it?

## Guidelines
Step-by-step instructions for the AI.

## Examples
At least one input → output example.
```

### Step 4: Test Your Skill

Before submitting:

1. Symlink your skill into a real project
2. Run it on at least 3 different scenarios
3. Verify the output matches your expectations
4. Have a teammate try it without explanation

### Step 5: Open a Pull Request

Include in your PR:

- [ ] The new skill file
- [ ] Example output (in `examples/` folder if complex)
- [ ] Description of use cases
- [ ] Before/after comparison if applicable

---

## Style Guide

### Naming Conventions

| Element | Convention | Example |
|---------|------------|---------|
| Filename | `kebab-case.mdc` | `code-review-checklist.mdc` |
| Skill title | Title Case | `# Code Review Checklist` |
| Section headers | Title Case | `## Guidelines` |

### Writing Guidelines

**Do:**
- Use clear, imperative language: "Check for...", "Generate...", "List..."
- Include specific criteria: "Flag if failure rate > 2.0%"
- Provide table formats for structured output
- Use emojis sparingly for visual hierarchy (✅ ⚠️ 🔴)

**Don't:**
- Use vague instructions: "Make it better"
- Assume context: Define acronyms on first use
- Write walls of text: Use bullet points and tables

### Example Quality Standards

Good example:
```markdown
## Examples

**User request:** "Review this PR for security issues"

**Expected output:**
| Finding | Severity | Location | Fix |
|---------|----------|----------|-----|
| SQL injection | 🔴 High | line 45 | Use parameterized query |
```

Bad example:
```markdown
## Examples

Just use it on code and it will find issues.
```

---

## Required Sections

### For All Skills

| Section | Required | Purpose |
|---------|----------|---------|
| Description (frontmatter) | ✅ Yes | Shown in Cursor's picker |
| Overview | ✅ Yes | Explains the skill's purpose |
| Guidelines | ✅ Yes | Step-by-step instructions |
| Examples | ✅ Yes | Shows expected behavior |

### For Workflow Skills (Additional)

| Section | Required | Purpose |
|---------|----------|---------|
| When to Use | ✅ Yes | Trigger conditions |
| Execution Process | ✅ Yes | Numbered steps |
| Data Sources | ✅ Yes | Query IDs or API endpoints |
| Output Location | ✅ Yes | Where results are saved |

---

## Pull Request Checklist

Before requesting review:

- [ ] Skill follows file format standard
- [ ] All required sections are present
- [ ] At least one example is included
- [ ] Tested on real scenarios
- [ ] No hardcoded secrets or PII
- [ ] Placed in correct category folder
- [ ] README.md updated if adding new category

---

## Review Process

1. **Self-review**: Check the checklist above
2. **Peer review**: Get one teammate to try the skill
3. **Merge**: Squash and merge when approved

Reviews should verify:
- Skill works as documented
- Examples are realistic
- No security concerns
- Benefits multiple teams

---

## Updating Existing Skills

When updating an existing skill:

1. Test that existing use cases still work
2. Document new features/changes in the PR
3. Update examples if behavior changed
4. Consider backwards compatibility

---

## Questions?

- Post in `#cursor` Slack channel
- Tag the skill author for clarification
- Open an issue for discussion

Thank you for making our tools better! 🎉
