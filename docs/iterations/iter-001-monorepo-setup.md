# Iteration 001: Monorepo Setup

**Status**: Completed
**Date Started**: 2026-01-01
**Date Completed**: 2026-01-01

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
- [x] Git repository initialized with initial commit
- [x] `.gitignore` excludes `node_modules/`, `dist/`, `.env`, common IDE files
- [x] Root `package.json` declares workspaces: `["backend", "frontend"]`
- [x] `backend/package.json` exists with name `@my-chat-project/backend`
- [x] `frontend/package.json` exists with name `@my-chat-project/frontend`
- [x] `README.md` contains project overview matching the provided description
- [x] `.nvmrc` specifies Node.js version
- [x] Running `npm install` at root succeeds without errors
- [x] Running `npm --workspaces run placeholder` shows both workspaces (even if they do nothing yet)

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
- Chose Node.js 20.x for LTS support
- Used scoped package names (`@my-chat-project/*`) for clear workspace identification
- Enhanced `.gitignore` with comprehensive patterns for various IDEs and OS files
- Added standard workspace scripts (test, build, dev) to root package.json for future use
- All workspace verification passed successfully

---

## Completion Checklist
- [x] All files created as specified
- [x] `npm install` runs successfully
- [x] Workspaces recognized by npm
- [x] Git repository initialized with proper ignores
- [x] This iteration doc updated with completion date and notes
- [x] `TODO.md` updated (move this iteration to "Completed")
