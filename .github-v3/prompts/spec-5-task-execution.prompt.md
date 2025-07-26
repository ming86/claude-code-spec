---
description: Execute specific implementation task from approved tasks.md with single-task focus
mode: agent
tools: ['codebase', 'editFiles', 'search', 'problems']
---

# Execute Implementation Task

Execute specific task for feature: **${input:feature:Enter feature name}**

**Task to execute**: **${input:taskNumber:Enter task number (e.g., 1.1, 2.3)}**

## Prerequisites Validation

**CRITICAL**: Verify before execution:

- Implementation plan exists: `.spec-workflow/specs/${input:feature}/tasks.md`
- Task `${input:taskNumber}` exists in the task list
- Previous phases approved (requirements, design, implementation-plan)

## Context Loading

**Read specification documents before implementation**:

1. **Requirements**: `.spec-workflow/specs/${input:feature}/requirements.md`
2. **Design**: `.spec-workflow/specs/${input:feature}/design.md`
3. **Tasks**: `.spec-workflow/specs/${input:feature}/tasks.md`

**Locate specific task**: Find task `${input:taskNumber}` in tasks.md and analyze:

- Task description and acceptance criteria
- Requirements references (_Requirements: X.X, Y.Y_)
- Time estimate and dependencies
- Implementation details and constraints

## Single Task Execution Discipline

### Core Execution Rules

- **Execute ONLY task `${input:taskNumber}`**
- **Do NOT implement other tasks automatically**
- **Complete the task thoroughly, then STOP**
- **Wait for user review before proceeding to next task**

### If Task Has Sub-tasks

When task `${input:taskNumber}` has sub-tasks (e.g., 1.1, 1.2):

- Execute sub-tasks in order if not specified
- Or execute only the specific sub-task if specified
- Complete all sub-tasks before marking parent task complete

## Implementation Process

### 1. Task Analysis

**Understand the implementation scope**:

- Parse task requirements and acceptance criteria
- Identify files/components to create or modify
- Review existing codebase patterns using codebase tool
- Plan implementation approach

### 2. Code Implementation

**Write the implementation**:

- Use editFiles tool to create/modify code
- Follow existing project patterns and conventions
- Implement according to design specifications
- Include proper error handling and validation

### 3. Testing Integration

**Ensure quality**:

- Add unit tests for new functionality
- Create integration tests where appropriate
- Follow existing testing patterns
- Include test data and fixtures as needed

### 4. Validation and Self-Correction

**Automatic quality control**:

- Use problems tool to identify issues
- Fix syntax errors, type errors, import issues automatically
- Re-validate after fixes
- Only proceed when validation passes

### 5. Task Completion

**Mark task complete**:

- Update tasks.md with ✅ for completed task
- Add completion timestamp
- Note any implementation decisions made
- Document issues resolved

## Implementation Guidelines

### Code Quality Standards

- **Follow existing patterns**: Use codebase tool to understand current conventions
- **Maintain consistency**: Match existing code style and architecture
- **Include documentation**: Add necessary inline comments and documentation
- **Error handling**: Implement appropriate error handling for the feature

### Testing Requirements

- **Unit tests**: For new business logic and functions
- **Integration tests**: For API endpoints and component interactions
- **Test coverage**: Ensure adequate test coverage for new functionality
- **Test data**: Create fixtures and test data as needed

### Integration Considerations

- **Existing components**: Integrate properly with existing codebase
- **Dependencies**: Handle task dependencies correctly
- **Configuration**: Update configuration files as needed
- **Database**: Include migrations if schema changes required

## Error Handling

### Automatic Resolution

**Fix these issues automatically**:

- Syntax and compilation errors
- Missing imports
- Type errors and interface mismatches
- Basic integration issues

### Request Guidance For

**Stop and ask for help with**:

- Ambiguous requirements or business logic
- Complex architectural decisions
- External dependency issues
- Performance or security concerns

## Progress Reporting

### Completion Summary

After task completion, provide:

- **What was implemented**: Summary of changes made
- **Files modified/created**: List of affected files
- **Requirements satisfied**: Reference to requirements addressed
- **Testing included**: Description of tests added
- **Issues resolved**: Any problems encountered and fixed

### Next Steps

- **Task marked complete** in tasks.md
- **Ready for review**: Implementation ready for user verification
- **Dependencies satisfied**: Note if this task unblocks other tasks
- **Recommended next task**: Suggest logical next task to execute

## Boundaries

### This Prompt DOES

- ✅ Execute the specific requested task only
- ✅ Write/modify application code
- ✅ Create comprehensive tests
- ✅ Validate against requirements
- ✅ Self-correct common issues
- ✅ Mark task complete in tasks.md

### This Prompt DOES NOT

- ❌ Modify the implementation plan
- ❌ Execute multiple tasks automatically
- ❌ Change task order or dependencies
- ❌ Skip validation steps
- ❌ Proceed to next task without approval

Execute task `${input:taskNumber}` with precision, quality, and discipline while maintaining strict single-task focus.
