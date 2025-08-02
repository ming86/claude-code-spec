---
description: Task execution standards and progress tracking for implementing tasks.md plans
applyTo: ".spec-workflow/**/tasks.md"
---

# Task Execution Standards

Standards for executing implementation tasks and managing progress in the spec-driven development workflow.

## Execution Workflow Overview

### All-Tasks Execution Model

- **Execute ALL uncompleted tasks** in tasks.md following the planned sequence
- **Continue until completion** of all tasks or when user intervention is needed
- **Follow testing strategy** as specified in tasks.md plan - do not impose additional testing schedule
- **Execute efficiently** to complete all tasks in single interaction until tasks.md is fully executed

### Context-Safe Execution Protocol

- **Always re-read tasks.md** before starting ANY work and between tasks
- **Mark progress immediately** after completing each task
- **Preserve state continuously** through checkbox updates
- **Handle context compression** by re-reading tasks.md when context becomes unclear

## Task Execution Progress Standards

### HOW to Mark Tasks Complete

**CRITICAL**: Update tasks.md immediately after completing any task:
- Change `- [ ]` to `- [x]` for completed task
- Don't batch multiple completions - mark each task immediately upon completion
- Include brief completion note if helpful for context

### HOW to Resume Task Execution

**ALWAYS re-read `.spec-workflow/${feature}/tasks.md` before starting ANY work:**
- Whether executing a single task OR all tasks
- Scan for completed tasks (marked with `- [x]`)
- Identify remaining pending tasks (marked with `- [ ]`)
- Check for any new tasks added since last session
- Verify dependencies are satisfied before starting
- This enables seamless resume from any interruption point

### Key Workflow Pattern

1. **Read tasks.md** (always, regardless of scope)
2. **Assess current state** (what's done, what's pending)
3. **Execute work** (following planned sequence)
4. **Mark complete immediately** (don't wait)
5. **Update tasks.md** (preserve state)
6. **Continue to next task** (until all complete)

This makes any execution scope resumable and any interruption recoverable. The tasks.md file itself serves as the complete state persistence mechanism.

## Testing Strategy Execution

### Follow tasks.md Testing Plan

- **Execute testing tasks** only as specified in tasks.md with their defined timing and dependencies
- **Do NOT automatically test** after implementation tasks unless testing task is specified
- **Respect testing phases** - testing may be per-task, per-phase, or batched based on the implementation plan
- **Follow testing dependencies** - execute testing tasks only when their prerequisites are met

### Testing Task Identification

- **Unit Testing Tasks**: Usually named with "Unit Tests" or "Test" in title
- **Integration Testing Tasks**: Usually in separate phases after implementation
- **Validation Tasks**: May include acceptance criteria validation or integration verification

## Quality Standards During Execution

### Code Quality Requirements

- **Follow existing patterns**: Use established code organization and naming conventions
- **Error handling**: Include appropriate error handling and validation as specified in task acceptance criteria
- **Documentation**: Add clear inline comments for complex logic as specified in task requirements
- **Integration**: Ensure proper integration with existing code following task specifications

### Scope Control During Execution

- **Implement ONLY task specifications** - do not add additional features, optimizations, or "improvements"
- **Follow acceptance criteria exactly** - each criterion must be met without additions
- **Document scope expansion ideas** for future consideration but do not implement beyond task scope
- **Validate against requirements** - ensure implementation addresses referenced requirements (REQ-X.X)

## Progress Reporting Standards

### Task Completion Reporting

After completing each task, provide brief status:
- **Task completed**: Title and key implementation points
- **Files modified**: List of files created or updated
- **Next task**: Identify next task in sequence

### Feature Implementation Reporting

When all tasks complete, provide comprehensive report:
- **Total tasks completed**: Count and summary
- **Implementation summary**: Key components and functionality delivered
- **Testing completed**: Summary of testing tasks executed per plan
- **Integration status**: Verification that feature integrates properly

## Error Handling During Execution

### Execution Issues

- **If task requirements unclear**: Use context from requirements.md and design.md to interpret
- **If dependencies missing**: Complete prerequisite tasks first following planned sequence
- **If scope expansion tempting**: Strictly implement only task requirements - document additional ideas separately
- **If testing strategy unclear**: Follow ONLY testing tasks defined in tasks.md

### Context Management Issues

- **If context becomes unclear**: Re-read tasks.md, requirements.md, and design.md to restore context
- **If task status ambiguous**: Check tasks.md for completion markers and current position
- **If dependencies uncertain**: Review dependency information in tasks.md and verify prerequisite completion

### Quality Issues

- **If acceptance criteria unclear**: Make them specific and testable based on available context
- **If integration problems arise**: Ensure implementation follows existing codebase patterns
- **If testing failures occur**: Address issues before marking task complete

## Execution Efficiency Guidelines

### Interaction Optimization

- **Complete all tasks in single interaction**: Execute all uncompleted tasks until tasks.md is fully executed
- **Follow tasks.md sequence**: Execute tasks in exact order specified in tasks.md plan
- **Continuous progression**: Move to next task immediately after completion

### State Preservation

- **Mark progress continuously**: Update task status throughout execution, not just at end
- **Update tasks.md frequently**: Ensure tasks.md reflects current state after each task
- **Document blockers immediately**: Note any issues that prevent task completion
- **Maintain task sequence**: Follow planned order from tasks.md exactly

These standards ensure reliable, efficient task execution with comprehensive progress tracking and quality validation while respecting the planned implementation approach defined in tasks.md.