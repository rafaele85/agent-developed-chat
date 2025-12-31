# Git Workflow Skill

## Overview
This project uses git for version control with conventional commits and a structured branching strategy.

---

## Commit Message Format

### Structure
```
<type>(<scope>): <subject>

<body>

<footer>
```

### Types
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation only
- `style`: Code style/formatting (no logic change)
- `refactor`: Code restructuring (no feature/fix)
- `test`: Adding or updating tests
- `chore`: Build process, dependencies, tooling
- `ci`: CI/CD pipeline changes

### Scope
- `backend`: Changes to backend workspace
- `frontend`: Changes to frontend workspace
- `root`: Root-level configuration
- `docs`: Documentation files
- `ci`: CI/CD configuration

### Subject Line
- Use imperative mood ("add" not "added" or "adds")
- No period at the end
- Maximum 72 characters
- Lowercase after type/scope

### Examples
```
feat(backend): add WebSocket connection handler

Implements basic WebSocket server using Fastify's websocket plugin.
Accepts connections and logs client connection/disconnection events.

Refs: iter-003
```
```
test(frontend): add username validation tests

Covers edge cases: empty strings, whitespace-only, special characters,
and length limits.
```
```
chore(root): add ESLint and Prettier configuration

Sets up shared linting rules for both workspaces.
Configures pre-commit hooks for automatic formatting.
```

---

## Branching Strategy

### Branch Naming
- Feature branches: `feat/iter-XXX-short-description`
- Bug fixes: `fix/issue-description`
- Documentation: `docs/what-changed`
- Chores: `chore/what-changed`

### Main Branches
- `main`: Production-ready code, always stable
- Feature branches are short-lived, merged via PR after review

### Workflow
1. Create feature branch from `main`
2. Make changes in small, logical commits
3. Push branch when iteration complete
4. Create PR (human reviews)
5. Merge to `main` after approval
6. Delete feature branch

---

## When Creating Commits

### Automatic Commit Creation
When asked to "create a commit" or "commit these changes":

1. **Stage changes**: `git add .` (or specific files if instructed)
2. **Generate commit message** following conventional format:
    - Determine type based on changes
    - Determine scope based on files modified
    - Write clear subject (imperative, <72 chars)
    - Add body if changes need explanation
    - Reference iteration if applicable
3. **Create commit**: `git commit -m "..."`
4. **Confirm**: Show commit hash and message to human

### Multi-file Changes
If changes span multiple scopes (e.g., backend + root config):
- Create separate commits per scope when possible
- OR use broader scope like `root` if changes are tightly coupled
- Explain the choice to human

### What NOT to Commit
- `node_modules/` (should be gitignored)
- Build artifacts (`dist/`, `.cache/`)
- Environment files (`.env`, `.env.local`)
- IDE-specific files (unless `.vscode/settings.json` is intentionally shared)
- Logs or temporary files

---

## When Creating Branches

### Automatic Branch Creation
When asked to "create a branch for iteration X":

1. **Ensure clean working directory**: Check `git status`
2. **Create branch**: `git checkout -b feat/iter-XXX-description`
3. **Confirm**: Show branch name to human

### Branch Naming from Iteration
Extract branch name from iteration file:
- `iter-002-backend-workspace.md` → `feat/iter-002-backend-workspace`
- `iter-005-username-entry.md` → `feat/iter-005-username-entry`

---

## Verification Before Commit

Before creating any commit:
- [ ] All acceptance criteria met (check iteration doc)
- [ ] Tests pass (`npm test` or workspace-specific test command)
- [ ] TypeScript compiles (`npm run build` or `tsc --noEmit`)
- [ ] Linting passes (if configured)
- [ ] No unintended files staged (check `git status`)

If any verification fails, **stop and report to human** rather than committing broken code.

---


## Working with Iteration Workflow

### Standard Iteration Commit Flow
For a typical iteration:

1. Human approves iteration spec
2. **Agent MUST create feature branch FIRST**: `feat/iter-XXX-description`
3. Agent implements changes
4. Agent runs all verification checks
5. Agent creates commit(s) with conventional messages
6. Agent reports completion to human
7. Human reviews, merges PR

### Creating Branch at Start of Iteration
**CRITICAL**: Before making ANY code changes for an iteration:
1. Check current branch with `git branch --show-current`
2. If not on `main`, ask human if you should switch
3. Create feature branch: `git checkout -b feat/iter-XXX-description`
4. Confirm branch creation to human
5. Then proceed with implementation

The feature branch name should match the iteration file name.
Example: `iter-002-backend-typescript.md` → `feat/iter-002-backend-typescript`


### Multiple Commits Per Iteration
It's acceptable to create multiple commits during one iteration:
- Logical separation (e.g., "add config" → "add implementation" → "add tests")
- Each commit should be atomic and buildable
- All commits use conventional format

---

## When NOT to Commit

- If verification checks fail
- If iteration is not complete
- If human has not approved the changes
- If working directory contains unrelated changes

Always ask for guidance if unsure.