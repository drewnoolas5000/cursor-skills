# 🎯 Gusto Cursor Skills

A shared library of Cursor AI skills for Gusto engineering teams. Clone this repo to get instant access to productivity-boosting AI workflows.

## What Are Skills?

**Skills** (also called "Rules" in Cursor) are instruction files that teach Cursor's AI how to perform specific tasks. Think of them like recipes that help the AI understand:

- What you're trying to accomplish
- What steps to follow
- What the output should look like

**In plain English:** Instead of explaining the same thing to Cursor every time, you write it once in a skill file, and Cursor remembers how to do it.

---

## Quick Start

### 1. Clone this repo somewhere on your machine

```bash
git clone git@github.com:Gusto/cursor-skills.git ~/cursor-skills
```

### 2. Symlink skills into your project

**Option A: Link the entire shared skills directory (recommended)**

```bash
# From your project root (e.g., zenpayroll)
ln -s ~/cursor-skills/skills .cursor/rules/shared-skills
```

**Option B: Link specific skills you want**

```bash
# Link just one skill
ln -s ~/cursor-skills/skills/workflows/gep-risk-metrics-monthly-report.mdc .cursor/rules/gep-risk-metrics.mdc
```

### 3. Use a skill in Cursor

1. Open Cursor
2. Open Chat (`Cmd+L` on Mac)
3. Type `@Rules` and select your skill
4. Ask Cursor to run it!

**Example:**
> "Run the GEP risk metrics monthly report"

---

## 📂 Repository Structure

```
cursor-skills/
├── README.md                    # You are here
├── CONTRIBUTING.md              # How to add new skills
├── SECURITY.md                  # Security best practices
├── skills/
│   ├── beginner/                # Simple skills for learning
│   │   ├── explain-code-simply.mdc
│   │   └── ruby-method-documenter.mdc
│   ├── intermediate/            # More complex patterns
│   │   ├── code-review-checklist.mdc
│   │   └── feature-flag-review.mdc
│   ├── workflows/               # Multi-step data-driven processes
│   │   └── gep-risk-metrics-monthly-report.mdc  ⭐ Featured
│   ├── security/                # Security analysis skills
│   │   └── threat-model-analysis.mdc
│   └── templates/               # Starting points for new skills
│       ├── basic-skill-template.mdc
│       └── workflow-skill-template.mdc
└── docs/
    ├── getting-started.md
    └── skill-types.md
```

---

## Skill Categories

| Category | Complexity | Description | Example |
|----------|------------|-------------|---------|
| 🟢 **Beginner** | Low | Simple formatting and explanation skills | Code explainer |
| 🟡 **Intermediate** | Medium | Multi-step analysis patterns | Code review checklist |
| 🔴 **Workflows** | High | Data-driven, multi-query processes | Monthly risk reports |
| 🔐 **Security** | Medium | Security scanning and analysis | STRIDE threat model |

---

## ⭐ Featured Skill: GEP Risk Metrics Monthly Report

Our most comprehensive skill example! This workflow:

1. **Queries production data** from 3 Redash queries
2. **Calculates metrics** across 6 months of partner data
3. **Identifies risk flags** using defined thresholds
4. **Generates a leadership-ready report** with tables and recommendations

**See it in action:**
- Skill file: [`skills/workflows/gep-risk-metrics-monthly-report.mdc`](./skills/workflows/gep-risk-metrics-monthly-report.mdc)
- Example output: [`examples/GEP_Risk_Metrics_Example.md`](./examples/GEP_Risk_Metrics_Example.md)

---

## Creating Your First Skill

Every skill file (`.mdc`) has two parts:

### 1. Frontmatter (The Header)

```yaml
---
description: What this skill does (shown when you pick it)
globs: "*.rb"           # Optional: Only activate for certain files
alwaysApply: false      # Optional: Auto-apply to every conversation
---
```

### 2. Content (The Instructions)

```markdown
# Skill Name

## Overview
Explain what this skill helps accomplish.

## Guidelines
Step-by-step instructions for the AI.

## Examples
Show input → output examples.
```

### Minimal Example

```markdown
---
description: Explains code in plain English for non-engineers
alwaysApply: false
---

# Explain Code Simply

## Overview
Explains code using everyday language and analogies.

## Guidelines
1. Start with what the code DOES (its purpose)
2. Use analogies from everyday life
3. Avoid jargon - if you must use technical terms, define them
4. Keep explanations to 2-3 short paragraphs

## Examples

**User asks**: "What does this method do?"

**Good response**: "This code figures out overtime pay. If someone 
works 40 hours or less, they get zero overtime. For every hour beyond 
40, it counts as 1.5 hours (time-and-a-half)."
```

---

## Skill Types Explained

### 🟢 Beginner: Simple Instructions

Best for: Formatting, code style, explanations

```markdown
# These skills just give the AI clear instructions
# No external data, no multi-step processes
```

### 🟡 Intermediate: Analysis Patterns

Best for: Code reviews, migrations, analysis

```markdown
# These skills have multiple steps:
# 1. Look at the code
# 2. Check for specific patterns
# 3. Provide structured feedback
```

### 🔴 Workflows: Data-Driven Processes

Best for: Reports, metrics analysis, recurring tasks

```markdown
# These skills:
# 1. Query external data (Redash, APIs)
# 2. Process and calculate metrics
# 3. Generate formatted output
# 4. Save results to files
```

---

## Using Skills with MCP Tools

Some skills use **MCP (Model Context Protocol)** to access external data. These skills can:

- Query Redash for production metrics
- Search Glean for documentation
- Look up Jira tickets
- Check Google Calendar

**Example from GEP Risk Metrics skill:**

The skill instructs Cursor to run Redash queries:
> "Execute Query 104845 with parameters: name='all', start_month='2025-07-01'"

Cursor uses the Redash MCP to fetch the data and continue the analysis.

---

## Best Practices

### ✅ Do

- **Be specific** - Tell the AI exactly what format you want
- **Include examples** - Show input/output pairs
- **Define thresholds** - Use tables for decision criteria
- **Test your skill** - Try it on real scenarios before sharing

### ❌ Don't

- **Hardcode secrets** - Never put API keys in skill files
- **Be vague** - "Make it good" doesn't help the AI
- **Skip examples** - The AI learns from your examples
- **Forget edge cases** - What should happen when data is missing?

---

## Contributing

We welcome new skills! See [CONTRIBUTING.md](./CONTRIBUTING.md) for:

- How to propose new skills
- Style guide for skill files
- Review process

**Quick steps:**
1. Fork this repo
2. Create your skill in the appropriate category folder
3. Test it in your local Cursor
4. Open a PR with before/after examples

---

## Security

Skills can be powerful. See [SECURITY.md](./SECURITY.md) for:

- What skills should never do
- How to handle sensitive data
- Prompt injection prevention

**The Golden Rule:** Skills should never output or request credentials, PII, or production secrets.

---

## Questions?

- 💬 Slack: `#cursor` channel
- 📖 Cursor Docs: https://docs.cursor.com/context/rules-for-ai
- 📂 Zenpayroll Rules: `.cursor/rules/` in the main repo

---

## Related Resources

- [Cursor Directory (Open Source Skills)](https://cursor.directory/)
- [MCP Documentation](https://docs.cursor.com/context/model-context-protocol)
- [Gusto AI Gem](https://github.com/Gusto/gusto-ai)
