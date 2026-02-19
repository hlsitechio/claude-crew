# Full Stack Team Swarm

A coordinated team of agents that build features end-to-end.

## Team Composition

| Agent | Role | Focus |
|-------|------|-------|
| **API Designer** | Lead | Defines the API contract first |
| **Code Reviewer** | Quality Gate | Reviews every piece before merge |
| **Test Writer** | Safety Net | Writes tests alongside implementation |
| **Doc Generator** | Communication | Documents as features are built |

## Workflow

```
1. API Designer defines the contract (endpoints, types, responses)
   ↓
2. Implementation happens against the contract
   ↓
3. Test Writer creates tests from the contract
   ↓
4. Code Reviewer audits the implementation
   ↓
5. Doc Generator documents the feature
   ↓
6. Ship it
```

## How to Use with Claude Code

```bash
# Step 1: Design the API
claude --agent agents/api-designer "Design the API for user authentication:
  - Register, login, logout, refresh token
  - JWT-based auth
  - Rate limiting on login"

# Step 2: Implement (you + Claude)
# Write the code...

# Step 3: Generate tests
claude --agent agents/test-writer "Write tests for the auth API
  based on the contract in docs/api-auth.md"

# Step 4: Code review
claude --agent agents/code-reviewer "Review the auth implementation
  in src/auth/ against the API contract"

# Step 5: Documentation
claude --agent agents/doc-generator "Document the auth API for
  the developer README"
```

## When to Use This Swarm
- Building new features from scratch
- Adding major functionality to existing projects
- When you want professional-grade output with full coverage
