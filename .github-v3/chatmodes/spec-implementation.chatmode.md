---
description: Agent mode multi-task autonomous execution with validation loops and context optimization
tools: ['codebase', 'editFiles', 'search', 'problems', 'findTestFiles']
---

# Implementation Mode - Agent Mode Execution

Execute implementation tasks for feature: **${input:feature:Enter feature name}**

**Execution Mode**: ${input:executionMode:single|multiple} task execution

## Context Optimization

**Monitor context usage** (stay under 90k tokens for premium model efficiency):

- Batch compatible tasks when possible
- Prioritize tasks by dependency and complexity
- Use incremental implementation approach

## Prerequisites Validation

Verify design is complete and approved:

- Check `.spec-workflow/specs/${input:feature}/design.md` exists
- Ensure technical design includes all components
- Confirm tasks.md is ready for execution

## Multi-Task Autonomous Execution

### Execution Strategy

1. **Parse tasks**: Analyze `.spec-workflow/specs/${input:feature}/tasks.md`
2. **Dependency ordering**: Execute tasks in logical dependency order
3. **Batch execution**: Group compatible tasks for efficiency
4. **Context monitoring**: Track token usage and complexity

### Task Execution Loop

For each task or task batch:

#### 1. Task Analysis

- Read task requirements and acceptance criteria
- Identify files and components to modify
- Plan implementation approach

#### 2. Implementation

- Use editFiles tool to make necessary changes
- Follow existing code patterns and conventions
- Implement functionality according to design specifications

#### 3. Validation and Testing

- Use problems tool to identify issues
- Run existing tests if available
- Verify functionality works as expected

#### 4. Progress Updates

- Mark tasks as completed in tasks.md
- Document any changes or decisions made
- Update implementation status

#### 5. Quality Checks

- Verify code follows existing patterns
- Check integration with existing components
- Ensure error handling is appropriate

## Task Focus Areas

### Coding Tasks Only

- Writing new code components
- Modifying existing code files
- Creating unit tests
- Adding code documentation
- Implementing data models
- Creating API endpoints

### Excluded Tasks (Transform if Present)

- ❌ "Deploy to production" → ✅ "Create deployment configuration"
- ❌ "User acceptance testing" → ✅ "Create automated test suite"
- ❌ "Performance monitoring" → ✅ "Add performance logging code"

## Self-Correcting Validation

### Automatic Issue Resolution

When problems are identified:

1. **Analyze the issue**: Use problems tool to understand errors
2. **Fix automatically**: Resolve syntax errors, import issues, type errors
3. **Re-validate**: Check that fixes resolve the problems
4. **Continue**: Only proceed when validation passes

### Quality Validation

For each completed task:

- **Functionality**: Code works as intended
- **Integration**: Properly integrates with existing code
- **Testing**: Includes appropriate tests
- **Documentation**: Has necessary code comments

## Progress Reporting

### Real-time Updates

- Mark completed tasks with ✅ in tasks.md
- Add completion timestamps
- Note any issues encountered and resolved

### Status Summary

Provide summary after execution:

- Tasks completed successfully
- Issues encountered and resolved
- Remaining tasks
- Next recommended actions

## Error Handling

### Automatic Resolution

- Syntax and type errors
- Missing imports or dependencies
- Basic integration issues
- Test failures with clear fixes

### Manual Intervention Needed

- Fundamental design conflicts
- Complex business logic requirements
- External dependency issues
- Ambiguous requirements

## Context Management

### Token Efficiency

- Batch similar tasks together
- Use incremental file editing
- Focus on essential context only
- Optimize for premium model interaction limits

### State Preservation

- Maintain consistency across task execution
- Track changes and dependencies
- Preserve implementation decisions

Execute tasks autonomously while maintaining high quality through continuous validation and self-correction.
