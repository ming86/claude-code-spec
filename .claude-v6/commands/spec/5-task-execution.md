---
description: 'Execute implementation tasks efficiently with context-safe progress tracking'
argument-hint: '[feature-name]'
---

# Role and Objective

Execute ALL uncompleted implementation tasks for specified feature following the planned sequence in tasks.md until all tasks are completed, with efficient execution, quality implementation, and context-safe progress tracking.

# Instructions

## ⚠️ CRITICAL: Scope Control During Execution ⚠️

**TASK EXECUTION IS WHERE SCOPE CREEP MOST COMMONLY OCCURS**

- **EXECUTE ONLY the specific task requirements** - no additional features, optimizations, or "improvements"
- **RESIST developer instincts** to add helpful features or optimizations during coding
- **FOLLOW acceptance criteria exactly** - meet them precisely, no more, no less
- **DOCUMENT additional ideas separately** - exclude from current implementation tasks
- **EXECUTION DISCIPLINE prevents technical debt** accumulation and maintenance burden

## Core Execution Requirements

- **Context Refresh**: Always read tasks.md at the start and before each new task
- **Prerequisites Required**: Implementation plan must exist and be approved in spec.yaml
- **Progress Tracking**: Mark tasks complete in tasks.md immediately after completion
- **Sequential Execution**: Execute ALL tasks following dependencies and sequence until feature completion
- **Testing Strategy**: Follow testing tasks and timing as specified in tasks.md - do not impose additional testing requirements
- **Continuous Progression**: Continue to next task immediately after completing current task
- **Execution Efficiency**: Complete all tasks in single interaction until tasks.md is fully executed

## Anti-Shortcut Quality Patterns

- Read and understand task specifications exactly rather than making assumptions about implementation scope
- Follow existing codebase patterns and conventions rather than introducing new approaches
- Implement only what is specified in task acceptance criteria, avoiding feature expansion during development
- Use systematic testing approach as defined in tasks.md rather than ad-hoc testing decisions

# Execution Steps

## Step 1: Context Loading & Task Analysis

### ⚠️ CRITICAL: Prerequisites Validation ⚠️

**MUST verify before execution:**

- Implementation plan exists: `.spec-workflow/specs/{feature}/tasks.md`
- Previous phases approved (requirements, design, implementation-plan)
- Feature specification is valid and accessible

### ⚠️ CRITICAL: SCOPE CONTROL DURING EXECUTION ⚠️

**TASK EXECUTION IS WHERE SCOPE CREEP MOST COMMONLY OCCURS**

- **EXECUTE ONLY the specific task requirements** - no additional features, optimizations, or "improvements"
- **RESIST developer instincts** to add helpful features or optimizations during coding
- **FOLLOW acceptance criteria exactly** - meet them precisely, no more, no less
- **DOCUMENT additional ideas separately** - exclude from current implementation tasks
- **EXECUTION DISCIPLINE prevents technical debt** accumulation and maintenance burden

### MUST READ specification documents before implementation

1. **Requirements**: `.spec-workflow/specs/{feature}/requirements.md`
2. **Design**: `.spec-workflow/specs/{feature}/design.md`
3. **Tasks**: `.spec-workflow/specs/{feature}/tasks.md`

### Identify next tasks

Find the first task in tasks.md that hasn't started (not marked with [x]) or was interrupted:

- Analyze task description and acceptance criteria
- Review requirements references (_Requirements: X.X, Y.Y_)
- Understand time estimate and dependencies
- Check implementation details and constraints

### Context-Safe Execution Protocol

**EXECUTION FLOW**:

- **Always re-read tasks.md** before executing any task to maintain context accuracy
- **Execute tasks in predefined sequence** following the implementation plan order
- **Mark tasks complete immediately** after finishing each task
- **Continue with next available task** until reaching a natural stopping point

## Step 2: Implementation Process

### Task Analysis

**Parse task details from tasks.md**:

```markdown
### {Task Number} {Task Title}

- [ ] **Task**: {Clear description of what to implement}
- **Requirement**: {Reference to specific requirement}
- **Acceptance Criteria**: {Specific conditions for completion}
- **Files**: {Files to create or modify}
- **Dependencies**: {Prerequisites}
- **Estimated Time**: {Time estimate}
```

### Requirement Context

**Review referenced requirements**:

- Locate requirement ID in requirements.md
- Understand functional behavior expected
- Note acceptance criteria and constraints
- Consider integration requirements

### Design Context

**Review relevant design sections**:

- Component architecture for this task
- API specifications if applicable
- Data model requirements
- Integration patterns to follow

### Codebase Analysis

**Analysis Process**:

- Locate existing files and project structure
- Understand existing file structure and organization
- Find similar components and patterns
- Review testing frameworks and conventions
- Examine code style and naming conventions
- Identify integration points and dependencies

## Step 3: Implementation Execution

**⚠️ CRITICAL: Task Scope Discipline ⚠️**

**FOR EACH TASK:**

- **Read task specification exactly** - understand what is required, nothing more
- **Check acceptance criteria** - these define completion, not suggested additions
- **Implement ONLY what's specified** - resist urges to improve, optimize, or add features
- **Mark complete immediately** - update tasks.md checkbox after each task

**Follow this implementation sequence**:

### Code Implementation

- Create or modify files as specified in task
- Follow existing code patterns and conventions
- Implement functionality to meet acceptance criteria exactly
- Include proper error handling and validation as specified
- Add inline documentation as needed per task requirements

### Testing Implementation

- Create unit tests for new functionality when specified in task
- Follow existing testing patterns
- Ensure test coverage meets task acceptance criteria
- Include edge cases and error scenarios as specified
- Verify tests pass before completion

### Integration Validation

- Ensure code integrates with existing system as specified
- Test integration points work correctly per task requirements
- Verify no existing functionality is broken
- Check that dependencies are properly handled as specified

## Step 4: Acceptance Criteria Validation

**⚠️ CRITICAL: Exact Criteria Compliance ⚠️**

**Verify task completion against criteria exactly**:

- Check each acceptance criterion is met precisely
- Test functionality works as specified (not enhanced)
- Verify integration requirements satisfied as defined
- Confirm code quality standards met per task specification

**DO NOT:**

- Add additional validation beyond criteria
- Implement extra error handling not specified
- Add performance optimizations not required
- Include additional features "while we're here"

## Step 5: Task Completion & Progress Update

**Mark task as complete and provide summary**:

- Update tasks.md checkbox: `- [x]`
- Provide brief task completion summary with key changes made
- Document any implementation notes or issues discovered

**Automatically continue with next task**:

- Re-read tasks.md to get current state
- Identify next uncompleted task in sequence
- Continue execution automatically until reaching natural stopping point

## Quality Standards (Applied Throughout)

### Code Quality Requirements

- **Follow existing patterns**: Use established code organization and naming
- **Error handling**: Include appropriate error handling as specified in task
- **Documentation**: Add clear inline comments for complex logic as specified
- **Testing**: Include comprehensive unit tests when specified in task
- **Integration**: Ensure proper integration with existing code as specified

### Testing Standards

- **Unit tests**: Test individual functions and methods when task specifies
- **Integration tests**: Test component interactions when task specifies
- **Error scenarios**: Test error handling and edge cases as specified
- **Coverage**: Meet or exceed existing coverage standards as specified
- **Naming**: Use descriptive test names and organization

### Code Review Standards

- **Readability**: Code is clear and well-structured
- **Maintainability**: Code follows SOLID principles as appropriate
- **Performance**: Efficient implementation without premature optimization
- **Security**: Proper input validation and secure coding practices as specified
- **Standards Compliance**: Follows project coding standards

## Step 6: Context-Safe Continuation

### Multi-Task Execution Protocol

**CONTINUE UNTIL ALL TASKS COMPLETE:**

1. **Re-read tasks.md** after each completed task
2. **Identify next uncompleted task** in sequence
3. **Analyze next task requirements** and acceptance criteria
4. **Execute next task** following same process
5. **Mark complete immediately** and continue
6. **Repeat until all tasks completed** or natural stopping point reached

### Context Management

- **Handle context compression** by re-reading tasks.md when context unclear
- **Maintain execution state** through continuous progress updates
- **Preserve task sequence** exactly as defined in implementation plan
- **Update progress continuously** throughout execution session

## Task Completion Report

**MUST PROVIDE** after completing task execution:

### Implementation Summary

```markdown
## Task Execution Completion Report

### Feature: {Feature Name}

**Status**: ✅ All Complete / ⚠️ Partial / ❌ Blocked

### Tasks Completed

- [x] Task 1.1: {Brief description} - {Files modified}
- [x] Task 1.2: {Brief description} - {Files modified}
- [x] Task 2.1: {Brief description} - {Files modified}

### Implementation Details

- **Total Tasks Executed**: {count}
- **Files Modified**: List of all files created or modified
- **Code Changes**: Summary of key functionality implemented
- **Testing**: Tests created and validation performed per plan
- **Integration**: Integration points verified as specified

### Acceptance Criteria Validation

- [x] All task acceptance criteria met exactly as specified
- [x] No additional features or optimizations added beyond task scope
- [x] Code follows existing patterns and integrates properly
- [x] Testing completed according to tasks.md plan

### Quality Assurance

- **Code Quality**: All code follows existing patterns and standards
- **Testing Strategy**: All testing tasks executed per tasks.md plan
- **Integration Verification**: All integration points validated as specified
- **Scope Compliance**: Implementation limited strictly to task specifications

### Next Steps

- Feature implementation complete and ready for validation
- All tasks in tasks.md have been executed successfully
- No additional development work required beyond approved scope
```

# Examples

## Argument Handling

```bash
/spec:5-task-execution user-authentication-system
/spec:5-task-execution payment-processing-integration
/spec:5-task-execution real-time-notifications
```

## Complete Feature Implementation Flow

1. **Initial Assessment**: "Reading tasks.md... Found 12 total tasks: 4 implementation, 2 testing, 4 implementation, 2 integration tests..."
2. **Phase 1 Execution**: "Executing implementation tasks 1.1-1.4... Following planned sequence..."
3. **Testing as Planned**: "Task 1.5 is unit testing - executing now as specified in plan (not automatically)..."
4. **Phase 2 Continuation**: "Moving to Phase 2 implementation tasks 2.1-2.4..."
5. **Integration Testing**: "Tasks 3.1-3.2 are integration tests - executing as planned after Phase 2..."
6. **Completion**: "All 12 tasks completed according to tasks.md plan. Feature implementation complete."

## Testing Strategy Examples

- **✅ Correct**: "Task 2.3 specifies unit tests - executing now per tasks.md plan"
- **❌ Wrong**: "Implementation task complete - automatically running tests (not in plan)"
- **✅ Correct**: "No testing tasks until Phase 3 - continuing with implementation per plan"

## Scope Control Examples

- **✅ Correct**: "Implement login endpoint with email/password validation (as specified in task)"
- **❌ Scope Creep**: "Implement login endpoint with email/password validation, plus OAuth, rate limiting, and password strength meter"

## Context-Safe Execution Example

1. **Context Loading**: "Re-reading tasks.md... Current status: 3 of 8 tasks completed, starting Task 1.4..."
2. **Task Analysis**: "Task 1.4: Create user registration API endpoint (_Requirements: REQ-2.1_)..."
3. **Implementation**: "Following acceptance criteria exactly - endpoint validation, database integration, error responses..."
4. **Completion**: "Task 1.4 completed, marking [x] in tasks.md, proceeding to Task 2.1..."
5. **Context Refresh**: "Re-reading tasks.md... Task 2.1 ready for execution..."

## All-Tasks Execution Model

**EXECUTE ALL UNCOMPLETED TASKS** in tasks.md following the planned sequence:

1. **Context Loading**: Read tasks.md, identify pending tasks
2. **Sequential Execution**: Execute tasks 1.1 → 1.2 → 1.3 → 2.1 → 2.2...
3. **Progress Tracking**: Mark each task [x] immediately after completion
4. **Testing Integration**: Execute testing tasks when specified in sequence
5. **Continuous Flow**: Continue until all tasks marked complete
6. **Completion Report**: Comprehensive summary of all work completed

## Task Execution Workflow

### Single Task Execution

```markdown
**TASK EXECUTION PROCESS:**

1. **Read tasks.md** - Get current state and identify next task
2. **Analyze Task** - Understand requirements, acceptance criteria, dependencies
3. **Review Context** - Check requirements.md and design.md for relevant information
4. **Implement** - Execute task following specifications exactly
5. **Validate** - Ensure acceptance criteria met precisely
6. **Mark Complete** - Update tasks.md with [x] immediately
7. **Continue** - Move to next task in sequence
```

### Multi-Task Execution

```markdown
**ALL-TASKS EXECUTION PROCESS:**

1. **Initial Assessment** - Read tasks.md, count total and completed tasks
2. **Sequential Processing** - Execute all uncompleted tasks in order
3. **Context Safety** - Re-read tasks.md before each new task
4. **Progress Updates** - Mark each task complete immediately after finishing
5. **Quality Maintenance** - Apply same standards across all tasks
6. **Completion Report** - Provide comprehensive summary when all tasks done
```

### Context Management Protocol

```markdown
**CONTEXT-SAFE EXECUTION:**

- **Always re-read tasks.md** before starting any task (single or multiple)
- **Scan for completed tasks** (marked with [x]) to understand current state
- **Identify remaining pending tasks** (marked with [ ]) 
- **Check for new tasks** added since last session
- **Verify dependencies** are satisfied before starting
- **This enables seamless resume** from any interruption point
```

### Error Handling During Execution

```markdown
**EXECUTION ISSUES:**

- **If task requirements unclear**: Use context from requirements.md and design.md to interpret
- **If dependencies missing**: Complete prerequisite tasks first following planned sequence
- **If scope expansion tempting**: Strictly implement only task requirements - document additional ideas separately
- **If testing strategy unclear**: Follow ONLY testing tasks defined in tasks.md
- **If context becomes unclear**: Re-read tasks.md, requirements.md, and design.md to restore context
- **If acceptance criteria unclear**: Make them specific based on available context while staying within task scope
```

Execute ALL uncompleted tasks in tasks.md following the planned sequence, dependencies, and testing strategy. Continue until tasks.md is fully executed. Maintain strict scope discipline - implement only what tasks specify, resist adding improvements or optimizations during execution.
