# Getting Started with Cursor Skills

This guide will help you start using and creating Cursor skills in 10 minutes.

---

## What is a Skill?

A **skill** is a text file (`.mdc`) that teaches Cursor's AI how to do something specific. Instead of explaining the same thing every time, you write instructions once, and Cursor follows them.

**Think of it like a recipe card:**
- The recipe card says "how to make chocolate chip cookies"
- You don't explain from scratch each time - you just follow the card
- Skills work the same way for AI tasks

---

## Quick Setup (5 minutes)

### Step 1: Clone the Skills Repo

```bash
git clone git@github.com:Gusto/cursor-skills.git ~/cursor-skills
```

### Step 2: Link to Your Project

From your project directory (like zenpayroll):

```bash
# Create the rules directory if it doesn't exist
mkdir -p .cursor/rules

# Link all shared skills
ln -s ~/cursor-skills/skills .cursor/rules/shared
```

### Step 3: Verify It Works

1. Open Cursor
2. Open a chat (`Cmd+L`)
3. Type `@Rules` - you should see the linked skills

---

## Using Your First Skill

### Example: Explain Code Simply

1. Select some code in your editor
2. Open chat (`Cmd+L`)
3. Type: `@explain-code-simply What does this do?`
4. Cursor explains in plain English!

### Example: Run the GEP Report

1. Open chat
2. Type: `Run the GEP risk metrics monthly report`
3. Cursor runs the Redash queries and generates the report

---

## Understanding Skill Files

Every skill has two parts:

### Part 1: The Header (YAML)

```yaml
---
description: What shows up when you pick the skill
globs: "*.rb"           # Optional: only for Ruby files
alwaysApply: false      # Optional: auto-apply always
---
```

### Part 2: The Instructions (Markdown)

```markdown
# Skill Name

## Overview
What this skill does.

## Guidelines
Step-by-step instructions for the AI.

## Examples
Show what good output looks like.
```

---

## Your First Custom Skill

Let's create a simple skill that formats commit messages:

### Step 1: Create the File

```bash
touch ~/cursor-skills/skills/beginner/format-commit-message.mdc
```

### Step 2: Add the Content

```markdown
---
description: Formats commit messages using Conventional Commits
alwaysApply: false
---

# Format Commit Message

## Overview
Reformats commit messages to follow Conventional Commits format.

## Guidelines
1. Start with a type: feat, fix, docs, style, refactor, test, chore
2. Add scope in parentheses if relevant
3. Write a brief description in present tense
4. Keep the first line under 72 characters

## Examples

**User input:** "fixed the bug where users couldn't log in"

**Output:** `fix(auth): resolve login failure for existing users`

**User input:** "added new payroll report feature"

**Output:** `feat(payroll): add monthly payroll summary report`
```

### Step 3: Test It

1. Open Cursor
2. Type: `@format-commit-message I updated the employee search to be faster`
3. Get: `perf(employees): optimize employee search query`

---

## Skill Complexity Levels

| Level | What It Does | Example |
|-------|--------------|---------|
| 🟢 **Beginner** | Simple formatting/explanation | Commit messages, code comments |
| 🟡 **Intermediate** | Multi-step analysis | Code reviews, flag reviews |
| 🔴 **Workflow** | Queries data, generates reports | Monthly metrics, dashboards |

Start with beginner skills, then level up!

---

## Tips for Success

### ✅ Do

- **Be specific** in your instructions
- **Include examples** - AI learns from them
- **Test before sharing** - try 3+ scenarios

### ❌ Don't

- Be vague: "make it good"
- Skip examples
- Forget edge cases

---

## Next Steps

1. Browse existing skills in `skills/` folders
2. Try the [Code Review Checklist](../skills/intermediate/code-review-checklist.mdc)
3. Create your own skill using a [template](../skills/templates/)
4. Share in `#cursor` Slack!

---

## Getting Help

- 💬 Slack: `#cursor`
- 📖 [Cursor Docs](https://docs.cursor.com/context/rules-for-ai)
- 📂 [Contributing Guide](../CONTRIBUTING.md)
