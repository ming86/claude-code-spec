---
description: Execute implementation tasks efficiently with context-safe progress tracking
mode: agent
tools: ['codebase', 'usages', 'problems', 'changes', 'testFailure', 'terminalSelection', 'terminalLastCommand', 'findTestFiles', 'runTests', 'editFiles', 'search', 'runCommands', 'runTasks', 'get_syntax_docs', 'mermaid-diagram-validator']
---

# Execute Implementation Tasks

Execute ALL uncompleted implementation tasks for feature: **${input:feature:Enter feature name}** following the planned sequence in tasks.md until all tasks are completed, with efficient execution, quality implementation, and context-safe progress tracking.

# Execution Steps

## Step 1: Context Loading & Task Analysis

### ⚠️ CRITICAL: Prerequisites Validation ⚠️

**MUST verify before execution:**

- Implementation plan exists: `.spec-workflow/specs/${input:feature}/tasks.md`
- Previous phases approved (requirements, design, implementation-plan)
- Feature specification is valid and accessible

### ⚠️ CRITICAL: SCOPE CONTROL DURING EXECUTION ⚠️

**TASK EXECUTION IS WHERE SCOPE CREEP MOST COMMONLY OCCURS**

- **EXECUTE ONLY the specific task requirements** - no additional features, optimizations, or "improvements"
- **RESIST developer instincts** to add helpful features or optimizations during coding
- **FOLLOW acceptance criteria exactly** - meet them precisely, no more, no less
- **DOCUMENT additional ideas separately** - exclude from current implementation tasks
- **EXECUTION DISCIPLINE prevents technical debt** accumulation and maintenance burden

### MUST READ specification documents before implementation:

1. **Requirements**: `.spec-workflow/specs/${input:feature}/requirements.md`
2. **Design**: `.spec-workflow/specs/${input:feature}/design.md`
3. **Tasks**: `.spec-workflow/specs/${input:feature}/tasks.md`

### Identify next tasks:

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

- Use `search` tool to locate existing files and project structure
- Use `codebase` semantic search tool to understand:
  - Existing file structure and organization
  - Similar components and patterns
  - Testing frameworks and conventions
  - Code style and naming conventions
  - Integration points and dependencies

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

## Defensive Patterns

### Error Handling and Recovery

- **If task cannot be completed**: Stop immediately, identify specific missing components, and request resolution
- **If requirements unclear**: Use context from requirements.md and design.md to interpret task specifications
- **If technical blockers arise**: Document issues and continue with other non-blocked tasks
- **If scope expansion is tempting**: Strictly implement only task requirements - document additional ideas for future consideration but do not implement beyond task scope
- **If testing strategy unclear**: Follow ONLY testing tasks defined in tasks.md plan
- **If dependencies missing**: Complete prerequisite tasks first following planned sequence

### Context Management Recovery

- **If context becomes unclear**: Re-read tasks.md, requirements.md, and design.md to restore context
- **If task status ambiguous**: Check tasks.md for completion markers and current position
- **If execution sequence unclear**: Follow exact order defined in tasks.md implementation plan

### Quality Recovery

- **If acceptance criteria unclear**: Make them specific and testable based on available context
- **If integration problems arise**: Ensure implementation follows existing codebase patterns
- **If testing failures occur**: Address issues before marking task complete
- **If scope creep detected**: Remove additional functionality and implement only task specifications

## Success Criteria

Task execution is complete when:

- [ ] ALL uncompleted tasks in tasks.md are executed according to their specifications
- [ ] All completed tasks are marked with [x] in tasks.md immediately after completion
- [ ] **SCOPE CONTROL**: Implementation includes ONLY task-specified functionality - no additional features
- [ ] Code follows existing patterns and integrates seamlessly with existing codebase
- [ ] Testing tasks executed according to tasks.md plan (not automatically after each implementation)
- [ ] Integration points are verified as specified in task acceptance criteria
- [ ] All task statuses are updated in tasks.md throughout execution
- [ ] Comprehensive completion report provided for the entire feature implementation

**Execute ALL uncompleted tasks in tasks.md following the planned sequence, dependencies, and testing strategy. Continue until tasks.md is fully executed. Maintain strict scope discipline - implement only what tasks specify, resist adding improvements or optimizations during execution.**
