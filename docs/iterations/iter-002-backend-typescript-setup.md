# Iteration 002: Backend TypeScript Setup

**Status**: Planning
**Date Started**: (fill when you start)
**Date Completed**: N/A

---

## Goal
Set up TypeScript compilation infrastructure for the backend workspace with strict type checking.

---

## Scope

### In Scope
- Add TypeScript as dev dependency to backend workspace
- Create `tsconfig.json` with strict mode enabled
- Create `src/index.ts` with a simple exported function
- Add build script to compile TypeScript
- Verify TypeScript compiles successfully to `dist/`

### Out of Scope
- Fastify or any web framework setup
- Testing infrastructure (Jest, etc.)
- Linting/formatting configuration (ESLint, Prettier)
- Hot reload or development workflow
- Any actual application logic beyond "hello world"

---

## Acceptance Criteria
- [ ] TypeScript installed as dev dependency in `backend/package.json`
- [ ] `backend/tsconfig.json` exists with strict mode enabled
- [ ] `backend/src/index.ts` exists with at least one exported function
- [ ] `backend/package.json` has a `build` script that runs TypeScript compiler
- [ ] Running `npm run build` in backend workspace compiles without errors
- [ ] Compiled JavaScript files appear in `backend/dist/`
- [ ] `backend/dist/` is already ignored by `.gitignore` (from iter-001)

---

## Technical Approach

### TypeScript Configuration
- Install `typescript` as dev dependency
- Create `tsconfig.json` with:
  - `strict: true` for maximum type safety
  - `target: ES2022` for modern JavaScript features
  - `module: NodeNext` for Node.js ESM support
  - `outDir: ./dist` for compiled output
  - `rootDir: ./src` for source files
  - `esModuleInterop: true` for better import compatibility

### Source Structure
- Create `backend/src/` directory
- Create `backend/src/index.ts` with a simple function:
  ```typescript
  export function greet(name: string): string {
    return `Hello, ${name}!`;
  }
  ```

### Build Script
- Add to `backend/package.json`:
  "scripts": {
    "build": "tsc",
    "clean": "rm -rf dist"
  }

Key files to create/modify:
- `backend/package.json` - Add TypeScript dependency and build scripts
- `backend/tsconfig.json` - TypeScript compiler configuration
- `backend/src/index.ts` - Simple "hello world" module

---

## Testing Strategy
- **Manual verification**: Run `npm run build` in backend workspace, verify no errors
- **Manual verification**: Check that `backend/dist/index.js` exists and contains compiled code
- **Manual verification**: Run `npm --workspaces run build` from root, verify backend builds

---

## Dependencies
- Iteration 001 completed (workspace structure established)
- Node.js 20.x installed
- npm workspaces configured

---

## Notes & Decisions
_(to be filled during execution)_

---

## Completion Checklist
- [ ] TypeScript installed and build script working
- [ ] `tsconfig.json` configured with strict mode
- [ ] Sample source file compiles successfully
- [ ] Compiled output appears in `dist/` directory
- [ ] This iteration doc updated with completion date and notes
- [ ] `TODO.md` updated (move this iteration to "Completed")
