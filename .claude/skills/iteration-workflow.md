# Iteration Workflow Skill

## Overview
This project progresses through small, documented iterations. Each iteration follows a strict process.

---

## Creating New Iterations

### When Asked to Create an Iteration Spec
1. Generate the next iteration number (check `docs/iterations/` folder)
2. Create `docs/iterations/iter-XXX-description.md` using `docs/templates/iteration-template.md`
3. Fill in all sections with specific, testable criteria
4. Keep scope minimal - one focused change per iteration
5. **Stop and ask for human approval** before proceeding to execution

### Iteration Numbering
- Format: `iter-001`, `iter-002`, etc. (zero-padded to 3 digits)
- Check existing files to determine next number
- Never skip numbers

### Writing Good Iteration Specs
- **Goal**: One clear sentence
- **Scope**: List 3-5 concrete deliverables, explicitly state what's OUT of scope
- **Acceptance Criteria**: Must be testable/verifiable, include "tests pass", "TypeScript compiles", "linting passes"
- **Technical Approach**: Specific file names, libraries to use, patterns to follow
- **Testing Strategy**: What tests will be written (unit/integration/e2e)

### Scope Guidelines
- Never mix backend + frontend work
- Never add features + tests + CI in one iteration
- Prefer 30-60 minute iterations over multi-hour ones
- If scope feels large, split into multiple iterations

---

## Executing Iterations

### When Asked to Execute an Iteration
1. Read the iteration spec from `docs/iterations/iter-XXX-*.md`
2. Read all relevant skills
3. Update iteration doc status to "In Progress"
4. Create/modify files as specified
5. Run tests and verification steps
6. Update iteration doc status to "Complete" with completion date
7. Add notes about any deviations or decisions
8. Move iteration from "Upcoming" to "Completed" in `TODO.md`

### During Execution
- Follow TypeScript strict mode (per `project-structure.md`)
- Create tests alongside code
- Never skip acceptance criteria
- If you encounter blockers, stop and ask for guidance

### After Execution
- Run all verification commands (npm install, tests, linting)
- Confirm all acceptance criteria checkboxes are met
- Update documentation
- Ask human to review before considering complete

---

## When NOT to Proceed
- If iteration spec is missing critical details
- If acceptance criteria are vague or untestable
- If scope seems too large for one iteration
- If dependencies from previous iterations aren't met

Stop and ask for clarification rather than making assumptions.