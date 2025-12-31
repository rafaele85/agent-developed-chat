# Iteration 001: Monorepo Setup

**Status**: Planning  
**Date Started**: (fill when you start)  
**Date Completed**: N/A

---

## Goal
Initialize git repository and establish npm workspace structure with minimal boilerplate.

---

## Scope

### In Scope
- Initialize git repository with `.gitignore`
- Create root `package.json` with workspace configuration
- Create `backend/` workspace folder with minimal `package.json`
- Create `frontend/` workspace folder with minimal `package.json`
- Create project `README.md` with overview
- Create `.nvmrc` specifying Node.js version (recommend 20.x or 22.x)

### Out of Scope
- Any actual application code
- TypeScript configuration (next iteration)
- Testing setup (next iteration)
- Linting/formatting configuration (next iteration)
- CI/CD pipelines

---

## Acceptance Criteria
- [ ] Git repository initialized with initial commit
- [ ] `.gitignore` excludes `node_modules/`, `dist/`, `.env`, common IDE files
- [ ] Root `package.json` declares workspaces: `["backend", "frontend"]`
- [ ] `backend/package.json` exists with name `@my-chat-project/backend`
- [ ] `frontend/package.json` exists with name `@my-chat-project/frontend`
- [ ] `README.md` contains project overview matching the provided description
- [ ] `.nvmrc` specifies Node.js version
- [ ] Running `npm install` at root succeeds without errors
- [ ] Running `npm --workspaces run placeholder` shows both workspaces (even if they do nothing yet)

---

## Technical Approach

### Root `package.json`
- Set `"private": true`
- Set `"workspaces": ["backend", "frontend"]`
- Include `"engines"` field matching `.nvmrc`
- Add placeholder script like `"test": "npm --workspaces run test"`

### Workspace `package.json` files
- Each has unique scoped name: `@my-chat-project/backend`, `@my-chat-project/frontend`
- Each has `"version": "0.1.0"`
- Each has `"private": true`
- Include placeholder scripts like `"placeholder": "echo 'Workspace ready'"`

### `.gitignore`
Standard Node.js patterns plus IDE-specific entries.

### `README.md`
Summarize project purpose, philosophy, and structure from the original spec.

---

## Testing Strategy
- **Manual verification**: Run `npm install`, verify no errors
- **Manual verification**: Run `npm --workspaces run placeholder`, verify both workspaces execute
- **Manual verification**: Check `git status` shows proper ignores

---

## Dependencies
- Node.js 20.x or 22.x installed
- npm 9.x or higher
- git installed

---

## Notes & Decisions
_(to be filled during execution)_

---

## Completion Checklist
- [ ] All files created as specified
- [ ] `npm install` runs successfully
- [ ] Workspaces recognized by npm
- [ ] Git repository initialized with proper ignores
- [ ] This iteration doc updated with completion date and notes
- [ ] `TODO.md` updated (move this iteration to "Completed")
