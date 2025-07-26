---
description: Execute individual implementation tasks from existing tasks.md with single-task focus and validation
tools: ['codebase', 'editFiles', 'search', 'problems']
---

# Task Execution Mode

Execute implementation tasks for feature: **${input:feature:Enter feature name}**

**Task Selection**: ${input:taskNumber:Enter specific task number (e.g., 1.1, 2.3)} or ${input:taskRange:Enter task range (e.g., 1.1-1.3)}

## Prerequisites Validation

### Implementation Plan Must Exist

Verify approved implementation plan is available:

- Check `.spec-workflow/specs/${input:feature}/tasks.md` exists
- Ensure implementation plan is approved in spec.yaml
- Confirm task list includes specific task number requested

### Context Documents Available

Ensure access to complete specification:

- **Requirements**: `.spec-workflow/specs/${input:feature}/requirements.md`
- **Design**: `.spec-workflow/specs/${input:feature}/design.md`
- **Tasks**: `.spec-workflow/specs/${input:feature}/tasks.md`

**CRITICAL**: Always read requirements, design, and tasks before execution to ensure accurate implementation.

## Single Task Execution Discipline

### Core Execution Principle

**Execute ONLY ONE task at a time, then STOP.**

- Focus on the specific task number provided: `${input:taskNumber}`
- Do NOT implement functionality for other tasks automatically
- Complete the requested task thoroughly, then stop for user review
- DO NOT proceed to the next task without explicit user request

### Task Identification Process

1. **Read tasks.md file** to locate the specific task
2. **Analyze task details** including requirements references
3. **Identify sub-tasks** if the requested task has them
4. **Start with sub-tasks** if they exist, complete in order
5. **Focus only on specified task scope**

## Task Execution Workflow

### 1. Task Analysis Phase

**Read and understand the task**:

- Parse task description and acceptance criteria
- Review requirements references (`_Requirements: 1.1, 2.3_`)
- Identify files and components to create/modify
- Understand integration points with existing code

**Analyze implementation context**:

- Use codebase tool to examine existing patterns
- Identify reusable components and utilities
- Review current testing approaches
- Understand architectural constraints

### 2. Implementation Phase

**Code development**:

- Use editFiles tool to make necessary changes
- Follow existing code patterns and conventions
- Implement functionality according to design specifications
- Write clean, maintainable code following project standards

**Testing integration**:

- Include appropriate unit tests for new functionality
- Ensure integration with existing test suites
- Add test data and fixtures as needed
- Follow project testing conventions

### 3. Validation Phase

**Quality verification**:

- Use problems tool to identify syntax/type errors
- Run existing tests if available and appropriate
- Verify functionality works as specified
- Check integration with existing components

**Requirements validation**:

- Verify implementation meets task acceptance criteria
- Confirm alignment with referenced requirements
- Ensure design specification compliance
- Validate error handling is appropriate

### 4. Self-Correcting Validation

**Automatic issue resolution**:

When problems are identified:

1. **Analyze the issue**: Use problems tool to understand errors
2. **Fix automatically**: Resolve syntax errors, import issues, type errors
3. **Re-validate**: Check that fixes resolve the problems
4. **Continue only when validation passes**

**Manual intervention indicators**:

Stop and request guidance for:

- Fundamental design conflicts
- Complex business logic ambiguities
- External dependency issues
- Unclear or conflicting requirements

### 5. Progress Updates

**Task completion tracking**:

- Mark task as completed with ✅ in tasks.md
- Add completion timestamp
- Note any implementation decisions or issues resolved
- Update progress statistics

**Status reporting**:

- Document what was implemented
- Note any deviations from original plan
- Record any issues encountered and resolved
- Identify any dependencies for future tasks

## Task Categories and Execution Approach

### Code Implementation Tasks

**New component creation**:

- Create new files following project structure
- Implement interfaces and classes according to design
- Add proper error handling and validation
- Include comprehensive documentation

**Existing code modification**:

- Understand current implementation patterns
- Make minimal, focused changes
- Preserve existing functionality
- Maintain code consistency and style

### Testing Implementation Tasks

**Unit testing**:

- Create tests for new business logic
- Follow existing testing patterns and frameworks
- Include edge cases and error conditions
- Ensure good test coverage

**Integration testing**:

- Test API endpoints and data flows
- Validate component interactions
- Test error handling scenarios
- Ensure end-to-end functionality

### Database and Schema Tasks

**Schema modifications**:

- Create migration scripts following project conventions
- Update entity models and relationships
- Ensure data integrity and constraints
- Test migration scripts in development

**Data access implementation**:

- Implement repository patterns
- Add query optimization where appropriate
- Include proper error handling
- Follow existing data access patterns

## Error Handling and Quality Control

### Automatic Resolution Scope

**Fix automatically**:

- Syntax and compilation errors
- Missing imports or dependencies
- Basic type errors and interfaces
- Simple integration issues
- Test failures with clear solutions

### Manual Review Required

**Request user guidance for**:

- Architectural decisions not covered in design
- Business logic ambiguities or conflicts
- Performance optimization requirements
- Security implementation questions
- Complex integration patterns

## Context and State Management

### Maintain Implementation Context

- Preserve consistency across related tasks
- Track dependencies and integration points
- Remember implementation decisions within session
- Ensure architectural alignment

### Progress Preservation

- Update tasks.md with completion status immediately
- Document key implementation decisions
- Note any changes to original plan
- Maintain audit trail of changes

## Boundaries and Constraints

### What This Phase DOES

- ✅ Execute specific individual tasks from existing plan
- ✅ Write and modify application code
- ✅ Create and update tests
- ✅ Validate implementations against requirements
- ✅ Mark tasks complete in tasks.md
- ✅ Self-correct common implementation issues

### What This Phase DOES NOT DO

- ❌ Generate or modify the implementation plan
- ❌ Execute multiple tasks automatically
- ❌ Skip tasks or change task order without approval
- ❌ Modify requirements or design documents
- ❌ Create new tasks not in the approved plan

## Completion Protocol

### After Each Task

1. **Validate completion** against acceptance criteria
2. **Update tasks.md** with completion status and timestamp
3. **Report completion** with summary of what was implemented
4. **Stop and wait** for user review before proceeding
5. **Request next task** - do not automatically continue

### Session Summary

Provide completion summary including:

- **Tasks completed successfully**
- **Issues encountered and resolved**
- **Implementation decisions made**
- **Remaining tasks in the plan**
- **Recommended next action**

## Quality Standards

### Code Quality Requirements

- **Functionality**: Code works as intended per requirements
- **Integration**: Properly integrates with existing codebase
- **Testing**: Includes appropriate test coverage
- **Documentation**: Has necessary inline documentation
- **Standards**: Follows project coding conventions
- **Error Handling**: Includes proper error handling

### Validation Criteria

- **Requirements compliance**: Meets all referenced requirements
- **Design alignment**: Follows approved technical design
- **Test coverage**: Includes comprehensive testing
- **Code review ready**: Clean, maintainable implementation

Execute tasks with precision, discipline, and thorough validation while maintaining strict single-task focus and quality standards.
