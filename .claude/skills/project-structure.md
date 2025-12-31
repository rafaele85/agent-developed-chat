# Project Structure Skill

## Overview
This project is a monorepo containing a WebSocket chat application with strict TypeScript and testing requirements.

## Repository Layout
```
my-chat-project/
├── .claude/skills/          # Agent skills (this directory)
├── docs/
│   ├── templates/           # Reusable templates for iterations, PRs, etc.
│   └── iterations/          # Per-iteration documentation
├── backend/                 # Fastify WebSocket server
├── frontend/                # React client application
├── package.json             # Root package.json for workspace management
├── TODO.md                  # Current iteration tracking
└── README.md                # Project overview
```

## Monorepo Configuration
- **Tool**: npm workspaces
- **Workspaces**: `backend`, `frontend`
- All workspace packages use TypeScript strict mode
- Each workspace has its own `package.json`, `tsconfig.json`, and test configuration

## Naming Conventions
- **Folders**: lowercase with hyphens (e.g., `my-folder`)
- **Files**: camelCase for TS/JS (e.g., `userService.ts`), lowercase with hyphens for configs (e.g., `eslint.config.js`)
- **Iteration docs**: `iter-XXX-short-description.md` (e.g., `iter-001-monorepo-setup.md`)

## TypeScript Standards
- Strict mode enabled in all `tsconfig.json` files
- No `any` types without explicit justification
- Explicit return types on exported functions

## Testing Requirements
- Unit tests for all business logic
- Integration tests for API endpoints and WebSocket handlers
- Test files colocated with source: `myFile.ts` → `myFile.test.ts`

## Documentation Standards
- Every iteration must have a corresponding doc in `docs/iterations/`
- Iteration docs follow the template in `docs/templates/iteration-template.md`
- Code comments should explain "why", not "what"

## When Making Changes
- Never modify multiple workspaces in a single iteration
- Always create files with proper TypeScript configs before writing code
- Run tests before considering an iteration complete