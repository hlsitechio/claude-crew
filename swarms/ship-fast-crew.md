# Ship Fast Crew Swarm

Maximum velocity. Code, test, and document in parallel. For when you need to move FAST without cutting corners.

## Team Composition

| Agent | Role | When They Work |
|-------|------|---------------|
| **You + Claude** | Builder | Writing the code |
| **Test Writer** | Safety Net | Writing tests AS you code |
| **Doc Generator** | Communicator | Documenting AS you code |
| **DevOps Agent** | Deployer | Setting up CI/CD in parallel |

## Workflow

```
Time ──────────────────────────────────►

You:        [  Build Feature  ][  Polish  ][ Ship ]
Test Writer: [  Write Tests   ][  Edge Cases  ]
Doc Gen:        [ README ][ API Docs ][ Changelog ]
DevOps:     [ CI/CD ][ Docker ][ Deploy Config ]

                              ▲
                         All converge
                         ready to ship
```

## How to Use

```bash
# Terminal 1: You build the feature
# (Just code normally with Claude)

# Terminal 2: Tests being written
claude --agent agents/test-writer "Watch src/ for changes
  and generate tests for new functions"

# Terminal 3: Docs being written
claude --agent agents/doc-generator "Generate README and API
  docs for the new feature in src/feature/"

# Terminal 4: CI/CD being set up
claude --agent agents/devops "Create GitHub Actions workflow
  for this Node.js project with lint, test, build, deploy"
```

## The Speed Multiplier

Instead of the typical sequential flow:
```
Code (2h) → Test (1h) → Doc (30m) → CI/CD (30m) = 4 hours
```

The Ship Fast Crew runs in parallel:
```
Code (2h)
Tests     (running alongside) = already done when code is done
Docs      (running alongside) = already done when code is done
CI/CD     (running alongside) = already done when code is done
Total: 2 hours (50% time saved)
```

## When to Use This Swarm
- Hackathons and time-limited projects
- MVP development
- When you know what you're building and just need to execute
- Feature sprints with tight deadlines
