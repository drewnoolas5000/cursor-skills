# Understanding Skill Types

This guide explains the different types of Cursor skills and when to use each.

---

## Overview

| Type | Complexity | External Data? | Example Use Case |
|------|------------|----------------|------------------|
| 🟢 **Beginner** | Low | No | Format code, explain concepts |
| 🟡 **Intermediate** | Medium | No | Code review, analysis |
| 🔴 **Workflow** | High | Yes (Redash, APIs) | Generate reports, fetch metrics |
| 🔐 **Security** | Medium | No | Threat modeling, vulnerability scan |

---

## 🟢 Beginner Skills

### What They Do

Simple, single-purpose skills that teach the AI a specific behavior or format.

### Characteristics

- No external data needed
- Single input → single output
- Can be explained in a few sentences

### Good For

- Formatting (commit messages, documentation)
- Explanations (code to plain English)
- Simple transformations (rename patterns)

### Example Structure

```markdown
---
description: One-line description
---

# Skill Name

## Overview
What it does in 1-2 sentences.

## Guidelines
1. Step one
2. Step two
3. Step three

## Examples
**Input:** [example]
**Output:** [example]
```

### Real Examples

- `explain-code-simply.mdc` - Translate code to plain English
- `ruby-method-documenter.mdc` - Add RDoc comments
- `format-commit-message.mdc` - Conventional commit format

---

## 🟡 Intermediate Skills

### What They Do

Multi-step analysis or review patterns that require understanding context.

### Characteristics

- Multiple steps or phases
- May need to search codebase
- Produces structured output (tables, checklists)

### Good For

- Code reviews
- Feature flag analysis
- Migration planning
- Technical debt assessment

### Example Structure

```markdown
---
description: One-line description
---

# Skill Name

## Overview
What problem this solves.

## When to Use
- Scenario 1
- Scenario 2

## Guidelines

### Step 1: [First Phase]
What to analyze first.

### Step 2: [Second Phase]
What to analyze next.

### Step 3: [Output]
How to format results.

## Output Format
[Table or template]

## Examples
[Before/after or request/response]
```

### Real Examples

- `code-review-checklist.mdc` - Systematic PR review
- `feature-flag-review.mdc` - Flag cleanup analysis
- `model-usage-analyzer.mdc` - Track model reads/writes

---

## 🔴 Workflow Skills

### What They Do

Data-driven processes that query external systems and generate comprehensive outputs.

### Characteristics

- Query external data (Redash, APIs, databases)
- Multi-step execution process
- Generate saved reports or artifacts
- Often run on a schedule (monthly, quarterly)

### Good For

- Monthly/quarterly reports
- Metrics dashboards
- Data analysis
- Automated documentation

### Example Structure

```markdown
---
description: One-line description
---

# Workflow Name

## Overview
What this produces and why it matters.

**Output Location:** `path/to/output.md`

## When to Use
- Beginning of each month
- Before quarterly reviews

## Execution Process

### Step 1: [Setup]
Calculate date ranges, parameters.

### Step 2: [Data Collection]
| Query ID | Purpose | Parameters |
|----------|---------|------------|
| 12345 | Get X | param: value |

### Step 3: [Processing]
How to calculate/transform data.

### Step 4: [Analysis]
Thresholds, flags, categorization.

### Step 5: [Output]
Format and save results.

## Report Template
[Markdown template of output format]

## Data Sources
| Query | Purpose | URL |
|-------|---------|-----|
| ID | Desc | link |
```

### Real Examples

- `gep-risk-metrics-monthly-report.mdc` - Partner risk analysis
- Quarterly business reviews
- Compliance reporting

---

## 🔐 Security Skills

### What They Do

Analyze code for security vulnerabilities using established frameworks.

### Characteristics

- Use security frameworks (STRIDE, OWASP)
- Categorize findings by severity
- Provide specific, actionable fixes
- Often produce audit-ready output

### Good For

- Pre-release security reviews
- Compliance audits
- Security training
- Vulnerability assessment

### Example Structure

```markdown
---
description: One-line description
---

# Security Skill Name

## Overview
What security analysis this performs.

## When to Use
- Before releases
- Compliance audits

## Guidelines

### Vulnerability Categories
| Category | What to Find |
|----------|--------------|
| SQL Injection | Pattern X |
| XSS | Pattern Y |

### Severity Levels
| Level | Criteria |
|-------|----------|
| Critical | Exploitable without auth |
| High | Significant impact |

## Output Format
[STRIDE categories with findings]

## Examples
[Code pattern → finding]
```

### Real Examples

- `threat-model-analysis.mdc` - STRIDE framework analysis
- `dependency-vulnerability-scan.mdc` - Check for CVEs

---

## Choosing the Right Type

### Start Simple

```
Is it a single formatting/explanation task?
├── Yes → 🟢 Beginner
└── No → Does it need external data?
    ├── Yes → 🔴 Workflow
    └── No → Is it security-focused?
        ├── Yes → 🔐 Security
        └── No → 🟡 Intermediate
```

### When to Level Up

| Sign | Action |
|------|--------|
| Skill is getting long | Break into steps (→ Intermediate) |
| Need real data | Add query steps (→ Workflow) |
| Finding security issues | Use STRIDE/OWASP (→ Security) |
| Want reusable output | Add template (→ Workflow) |

---

## Template Files

Use these as starting points:

| Type | Template |
|------|----------|
| Beginner | `skills/templates/basic-skill-template.mdc` |
| Intermediate | `skills/templates/basic-skill-template.mdc` |
| Workflow | `skills/templates/workflow-skill-template.mdc` |
| Security | Copy from `skills/security/threat-model-analysis.mdc` |

---

## Best Practices by Type

### Beginner Skills

- Keep it focused - one skill, one job
- Include at least 2 examples
- Test on edge cases (empty, long, special chars)

### Intermediate Skills

- Use numbered steps
- Output tables for structured data
- Define clear criteria/thresholds

### Workflow Skills

- Document all data sources
- Include date range logic
- Save output to consistent location
- Add error handling notes

### Security Skills

- Link to official frameworks
- Include severity levels
- Provide code-level fixes
- Note false positive patterns

---

## Questions?

- 💬 Slack: `#cursor`
- 📖 [Contributing Guide](../CONTRIBUTING.md)
