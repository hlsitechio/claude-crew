<div align="center">

# Claude Crew

### Pre-built AI agent personas for Claude Code

**Drop them in. They work.**

[![Claude Code](https://img.shields.io/badge/Claude_Code-Compatible-blueviolet?style=flat-square&logo=anthropic)](https://code.claude.com)
[![Agents](https://img.shields.io/badge/Agents-15-green?style=flat-square)]()
[![Fun Modes](https://img.shields.io/badge/Fun_Modes-6-orange?style=flat-square)]()
[![Swarms](https://img.shields.io/badge/Swarm_Templates-3-blue?style=flat-square)]()
[![License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)]()

*Everyone builds the orchestra. We wrote the musicians.*

</div>

---

## What is this?

A collection of **ready-to-use AI agent personas** for Claude Code. Each agent is a specialized expert with a defined personality, methodology, and output format.

Copy an agent into your project. Point Claude Code at it. Get expert-level output.

## Quick Start

```bash
# Clone the crew
git clone https://github.com/hlsitechio/claude-crew.git

# Copy agents you need into your project
cp -r claude-crew/agents/code-reviewer ~/.claude/agents/
cp -r claude-crew/fun/gordon-ramsay ~/.claude/agents/

# Use in Claude Code
# Claude will automatically detect agents in .claude/agents/
```

Or cherry-pick individual agents:

```bash
# Just the code reviewer
curl -o .claude/agents/code-reviewer.md \
  https://raw.githubusercontent.com/hlsitechio/claude-crew/main/agents/code-reviewer/agent.md
```

---

## Production Agents

Real tools for real work. Each one is a specialist.

| Agent | What it does | Best for |
|-------|-------------|----------|
| [**Code Reviewer**](agents/code-reviewer/) | Finds bugs, security issues, design problems | PR reviews, code quality |
| [**Test Writer**](agents/test-writer/) | Generates comprehensive tests that catch real bugs | Test coverage, TDD |
| [**Doc Generator**](agents/doc-generator/) | Writes docs humans actually read | README, API docs, architecture |
| [**Refactorer**](agents/refactorer/) | Transforms messy code into clean systems | Legacy code, tech debt |
| [**API Designer**](agents/api-designer/) | Designs clean REST/GraphQL APIs | New APIs, API redesign |
| [**DevOps**](agents/devops/) | CI/CD, Docker, deployment automation | Infrastructure, shipping |
| [**Performance**](agents/performance/) | Finds bottlenecks, optimizes systems | Slow apps, scaling |
| [**Accessibility**](agents/accessibility/) | WCAG compliance, inclusive design | Web apps, compliance |
| [**Migrator**](agents/migrator/) | Framework/language/architecture migrations | Upgrades, rewrites |
| [**Learner**](agents/learner/) | Explains code like a patient teacher | Learning, onboarding |
| [**Security Auditor**](agents/security-auditor/) | OWASP Top 10, dependency audit, vulnerability scanning | Security reviews |
| [**SysAdmin**](agents/sysadmin/) | Server management, networking, hardening | Infrastructure, ops |
| [**Cloud Architect**](agents/cloud-architect/) | Cloud infrastructure design, cost optimization | Architecture, scaling |
| [**Incident Responder**](agents/incident-responder/) | Production incident management, post-mortems | On-call, outages |
| [**Data Engineer**](agents/data-engineer/) | Pipelines, schemas, query optimization | Data systems, ETL |

---

## Fun Modes

Because coding should be fun. These go viral on Twitter.

| Mode | Personality | Sample |
|------|------------|--------|
| [**Gordon Ramsay**](fun/gordon-ramsay/) | Brutal code reviewer chef | *"This function is RAWWW! 200 lines?! SPLIT IT UP!"* |
| [**Pirate**](fun/pirate/) | Nautical developer | *"Arrr! A sea monster lurks in yer auth middleware!"* |
| [**Yoda**](fun/yoda/) | Force-wielding code master | *"Null pointer, there is. Handle the absence, you must."* |
| [**Bob Ross**](fun/bob-ross/) | Gentle debugging companion | *"Happy little accident on line 47. Let's add a fix right here."* |
| [**Coach**](fun/coach/) | Motivational hype person | *"You just CRUSHED that bug! CHAMPIONSHIP behavior!"* |
| [**Noir Detective**](fun/noir-detective/) | Hard-boiled bug hunter | *"The bug walked in at 3am. Empty catch block. A cover-up."* |

---

## Swarm Templates

Multi-agent team configurations for coordinated work.

| Swarm | Agents | Use Case |
|-------|--------|----------|
| [**Full Stack Team**](swarms/full-stack-team.md) | API Designer + Code Reviewer + Test Writer + Doc Generator | Building features end-to-end |
| [**Code Review Squad**](swarms/code-review-squad.md) | Code Reviewer + Security Auditor + Performance | Triple-lens code review |
| [**Ship Fast Crew**](swarms/ship-fast-crew.md) | Builder + Test Writer + Doc Generator + DevOps | Maximum velocity shipping |

---

## How Agents Work in Claude Code

Claude Code supports custom agents through markdown files in your project:

```
your-project/
├── .claude/
│   └── agents/
│       ├── code-reviewer.md    ← Agent persona
│       ├── test-writer.md      ← Agent persona
│       └── gordon-ramsay.md    ← Fun mode
├── src/
└── ...
```

When you use the Task tool or subagents, Claude Code reads these agent definitions and adopts the persona, methodology, and output format defined in each file.

### Using agents in CLAUDE.md

```markdown
# CLAUDE.md

## Agents
When asked to review code, use the code-reviewer agent.
When asked to write tests, use the test-writer agent.
When the user types "/fun", switch to gordon-ramsay mode.
```

---

## Contributing

**Add your own agents!** The crew is always hiring.

1. Fork this repo
2. Create `agents/your-agent/agent.md` or `fun/your-mode/agent.md`
3. Follow the format: Personality + Methodology + Output Format + Rules
4. Submit a PR

### Agent Template

```markdown
# Agent Name

[One line: what this agent does]

## Personality
- [How it communicates]
- [What it prioritizes]

## Methodology
[Step-by-step approach]

## Output Format
[How results are structured]

## Rules
- [Non-negotiable behaviors]
```

---

## Related

- [**claude-memory**](https://github.com/hlsitechio/claude-memory) — Persistent memory for Claude Code sessions
- [Claude Code Docs](https://code.claude.com/docs) — Official documentation
- [MCP Protocol](https://modelcontextprotocol.io) — Model Context Protocol

---

<div align="center">

**Everyone builds orchestration frameworks. Nobody writes the agents.**

**We did.**

MIT License

</div>
