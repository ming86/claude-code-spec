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

- Implementation plan exists: `.kiro/specs/${input:feature}/tasks.md`
- Task `${input:taskNumber}` exists in the task list
- Previous phases approved (requirements, design, implementation-plan)

## Context Loading

**Read specification documents before implementation**:

1. **Requirements**: `.kiro/specs/${input:feature}/requirements.md`
2. **Design**: `.kiro/specs/${input:feature}/design.md`
3. **Tasks**: `.kiro/specs/${input:feature}/tasks.md`

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
- Complete each sub-task before moving to next
- Stop after completing requested task or sub-task

## Implementation Process

### 1. Task Analysis

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

### 2. Requirement Context

**Review referenced requirements**:

- Locate requirement ID in requirements.md
- Understand functional behavior expected
- Note acceptance criteria and constraints
- Consider integration requirements

### 3. Design Context

**Review relevant design sections**:

- Component architecture for this task
- API specifications if applicable
- Data model requirements
- Integration patterns to follow

### 4. Codebase Analysis

**Use codebase tool to understand**:

- Existing file structure and organization
- Similar components and patterns
- Testing frameworks and conventions
- Code style and naming conventions
- Integration points and dependencies

### 5. Implementation Execution

**Follow this implementation sequence**:

#### Code Implementation

- Create or modify files as specified in task
- Follow existing code patterns and conventions
- Implement functionality to meet acceptance criteria
- Include proper error handling and validation
- Add inline documentation as needed

#### Testing Implementation

- Create unit tests for new functionality
- Follow existing testing patterns
- Ensure test coverage meets acceptance criteria
- Include edge cases and error scenarios
- Verify tests pass before completion

#### Integration Validation

- Ensure code integrates with existing system
- Test integration points work correctly
- Verify no existing functionality is broken
- Check that dependencies are properly handled

### 6. Acceptance Criteria Validation

**Verify task completion against criteria**:

- Check each acceptance criterion is met
- Test functionality works as specified
- Verify integration requirements satisfied
- Confirm code quality standards met

### 7. Task Completion

**Mark task as complete**:

- Update tasks.md checkbox: `- [x]`
- Document any implementation notes
- Identify any issues or dependencies discovered
- Prepare summary for user review

## Implementation Quality Standards

### Code Quality Requirements

- **Follow existing patterns**: Use established code organization and naming
- **Error handling**: Include appropriate error handling and validation
- **Documentation**: Add clear inline comments for complex logic
- **Testing**: Include comprehensive unit tests
- **Integration**: Ensure proper integration with existing code

### Testing Standards

- **Unit tests**: Test individual functions and methods
- **Integration tests**: Test component interactions
- **Error scenarios**: Test error handling and edge cases
- **Coverage**: Meet or exceed existing coverage standards
- **Naming**: Use descriptive test names and organization

### Code Review Standards

- **Readability**: Code is clear and well-structured
- **Maintainability**: Code follows SOLID principles
- **Performance**: Efficient implementation without premature optimization
- **Security**: Proper input validation and secure coding practices
- **Standards Compliance**: Follows project coding standards

## Task Completion Report

After completing task execution, provide:

### Implementation Summary

```markdown
## Task `${input:taskNumber}` Completion Report

### Task: {Task Title}

**Status**: ✅ Complete / ⚠️ Partial / ❌ Blocked

### Implementation Details

- **Files Modified**: List of files created or modified
- **Code Changes**: Brief description of implementation
- **Testing**: Tests created and validation performed
- **Integration**: Integration points verified

### Acceptance Criteria Validation

- [x] Criterion 1: Met with implementation details
- [x] Criterion 2: Met with test validation
- [ ] Criterion 3: Partially met - explanation needed

### Issues Identified

- Any problems encountered during implementation
- Dependencies discovered that weren't in task description
- Suggestions for improvements or next steps

### Next Steps

- Ready for user review and approval
- Recommendations for next task to execute
- Any preparation needed for subsequent tasks
```

## Error Handling and Recovery

### If Task Cannot Be Completed

- **Missing Dependencies**: Identify specific missing components
- **Unclear Requirements**: Request clarification on ambiguous requirements
- **Technical Blockers**: Document technical issues preventing completion
- **Scope Issues**: Identify if task scope is too large or unclear

### Partial Completion Strategy

- Complete implementable portions of the task
- Document what was completed and what remains
- Identify specific blockers preventing full completion
- Provide recommendations for resolution

## Multi-Task Execution Mode

**Only when explicitly requested by user**:

If user requests multiple tasks (e.g., "execute tasks 1.1-1.3"):

### Batch Execution Process

1. **Validate all requested tasks exist**
2. **Execute tasks in dependency order**
3. **Complete each task fully before next**
4. **Stop if any task encounters blockers**
5. **Provide summary report for all completed tasks**

### Batch Execution Constraints

- **Sequential execution**: Complete tasks in logical order
- **Stop on errors**: Don't proceed if task fails
- **Quality maintenance**: Same quality standards for each task
- **Progress reporting**: Report completion of each task

## Integration with Existing Codebase

### Pattern Analysis

- **Identify existing patterns**: Use codebase tool to understand established patterns
- **Follow conventions**: Maintain consistency with naming, structure, organization
- **Reuse components**: Leverage existing utilities and components where appropriate
- **Integration points**: Properly integrate with existing APIs and interfaces

### Quality Assurance

- **Code review standards**: Follow established code review criteria
- **Testing integration**: Ensure tests fit existing testing framework
- **Documentation consistency**: Match existing documentation patterns
- **Performance considerations**: Consider impact on existing system performance

Execute the specified task with complete focus, thorough implementation, and rigorous validation against acceptance criteria.
