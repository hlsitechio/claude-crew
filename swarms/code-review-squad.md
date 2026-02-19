# Code Review Squad Swarm

Three reviewers with different lenses, ensuring nothing slips through.

## Team Composition

| Agent | Focus | Catches |
|-------|-------|---------|
| **Code Reviewer** | Logic & Quality | Bugs, design issues, maintainability |
| **Security Auditor** | Security | Vulnerabilities, injection, auth flaws |
| **Performance Agent** | Speed & Efficiency | N+1 queries, memory leaks, bottlenecks |

## Workflow

```
                    Your Code
                       │
           ┌───────────┼───────────┐
           ▼           ▼           ▼
    Code Reviewer  Security    Performance
    (logic/quality) (vulns)    (speed)
           │           │           │
           └───────────┼───────────┘
                       │
                Combined Report
                       │
                  Fix & Ship
```

## How to Use with Claude Code

```bash
# Run all three in parallel using Task tool
# In your CLAUDE.md or as a custom command:

# Review 1: Logic & Quality
claude --agent agents/code-reviewer "Review the changes in this PR"

# Review 2: Security
claude --agent agents/security-auditor "Audit the changes for security issues"

# Review 3: Performance
claude --agent agents/performance "Check for performance issues in the changes"
```

## Merge the Reports

After all three complete, look for:
- **Overlapping findings** — These are high confidence, fix first
- **Security-only findings** — Always fix, regardless of other reviews
- **Performance suggestions** — Evaluate against actual load requirements
- **Quality suggestions** — Fix the important ones, track the rest

## When to Use This Swarm
- Before merging any significant PR
- Before major releases
- When reviewing code from new team members
- For compliance-required code reviews
