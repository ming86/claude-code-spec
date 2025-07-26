---
description: Progress tracking and comprehensive status reporting with validation analysis
tools: ['codebase', 'search']
---

# Status Tracking Mode

Show current status and progress for feature: **${input:feature:Enter feature name}**

## Specification Analysis

### Phase Status Overview

Analyze each phase of the spec-driven development process:

#### 1. Requirements Phase

- **File Status**: Check `.spec-workflow/specs/${input:feature}/requirements.md`
- **EARS Compliance**: Verify WHEN/THEN format usage
- **Completeness**: Assess coverage of functional requirements
- **Quality Metrics**: Review acceptance criteria definition

#### 2. Design Phase

- **File Status**: Check `.spec-workflow/specs/${input:feature}/design.md`
- **Architecture**: Verify component design completeness
- **Research Integration**: Check for source citations if research conducted
- **Diagram Presence**: Confirm mermaid diagrams included

#### 3. Tasks Phase

- **File Status**: Check `.spec-workflow/specs/${input:feature}/tasks.md`
- **Task Structure**: Verify hierarchical numbering (1.1, 1.2, 2.1)
- **Requirement Mapping**: Confirm task-to-requirement traceability
- **Coding Focus**: Validate tasks focus on coding activities

#### 4. Implementation Phase

- **Progress Tracking**: Parse task completion checkboxes
- **File Changes**: Use codebase tool to identify modified files
- **Validation Status**: Check for any identified issues

## Progress Calculation

### Task Completion Analysis

Parse tasks.md to calculate:

- **Total tasks**: Count all defined tasks
- **Completed tasks**: Count checked checkboxes `- [x]`
- **Pending tasks**: Count unchecked checkboxes `- [ ]`
- **Completion percentage**: (Completed / Total) × 100

### Phase Completion Status

For each phase:

- ✅ **Complete**: All deliverables present and approved
- 🔄 **In Progress**: Work started but not completed
- ⏳ **Pending**: Waiting for previous phase completion
- ❌ **Issues**: Problems identified requiring attention

## Quality Assessment

### Requirements Quality

- **EARS Format Compliance**: Percentage of requirements using WHEN/THEN
- **Acceptance Criteria**: Coverage of testable conditions
- **Completeness**: All functional areas addressed

### Design Quality

- **Architecture Completeness**: All components designed
- **Integration Planning**: Existing system integration addressed
- **Testing Strategy**: Comprehensive testing approach defined

### Implementation Quality

- **Code Integration**: Changes follow existing patterns
- **Error Handling**: Appropriate error management implemented
- **Testing Coverage**: Unit tests included for new functionality

## Current Blockers

### Approval Status

Check for approval blockers:

- Requirements pending approval
- Design pending approval
- Tasks pending approval

### Technical Issues

Identify technical blockers:

- Compilation errors
- Test failures
- Integration problems
- Missing dependencies

### Process Issues

Check for process blockers:

- Incomplete specifications
- Missing phase deliverables
- Unclear requirements
- Design gaps

## Recommendations

### Next Steps

Based on current status, provide specific recommendations:

- **Requirements Phase**: Specific actions to complete requirements
- **Design Phase**: Design improvements or completions needed
- **Implementation Phase**: Next tasks to execute
- **Quality Issues**: Specific problems to address

### Priority Actions

Identify highest priority actions:

- Critical blockers to resolve
- Essential tasks to complete
- Quality improvements needed
- Process optimizations

## Reporting Format

### Executive Summary

Provide high-level status:

- Overall completion percentage
- Current phase
- Key blockers
- Estimated completion timeline

### Detailed Breakdown

- Phase-by-phase status
- Task completion details
- Quality metrics
- Issue identification

### Visual Progress

Use clear indicators:

- ✅ Completed phases/tasks
- 🔄 In progress items
- ⏳ Pending items
- ❌ Issues requiring attention

## Integration Health

### Codebase Analysis

Use codebase tool to assess:

- **Integration Quality**: How well changes integrate
- **Pattern Consistency**: Adherence to existing patterns
- **Architecture Alignment**: Consistency with design

### System Impact

Evaluate broader impact:

- **Existing Feature Impact**: Changes affecting other features
- **Performance Implications**: Potential performance impact
- **Security Considerations**: Security implications of changes

Provide comprehensive status visibility to enable informed decision-making and effective progress management.
