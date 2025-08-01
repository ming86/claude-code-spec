---
description: Comprehensive status tracking and progress analysis for spec-driven development
mode: agent
tools: ['codebase', 'search']
---

# Specification Status and Progress Analysis

Show current status and progress for feature: **${input:feature:Enter feature name}**

## Specification File Analysis

### File Existence and Structure Check

Verify specification completeness:

- **Spec directory**: `.spec-workflow/specs/${input:feature}/`
- **Metadata file**: `.spec-workflow/specs/${input:feature}/spec.yaml`
- **Requirements file**: `.spec-workflow/specs/${input:feature}/requirements.md`
- **Design file**: `.spec-workflow/specs/${input:feature}/design.md`
- **Tasks file**: `.spec-workflow/specs/${input:feature}/tasks.md`

### Metadata Analysis

Parse `spec.yaml` to extract:

- Current phase and status
- Approval states for each phase
- Progress percentages
- Creation and update timestamps
- Feature description and context

## Phase-by-Phase Status Analysis

### 1. Requirements Phase Analysis

#### Status Indicators

- ✅ **Generated**: Requirements document exists and has content
- ✅ **EARS Compliance**: Count WHEN/THEN format usage
- ✅ **Approval Status**: Check spec.yaml approval state
- 📊 **Quality Metrics**: Analyze requirement completeness

#### Quality Assessment

- **Requirement Count**: Total functional requirements identified
- **EARS Format Usage**: Percentage using WHEN/THEN structure
- **Acceptance Criteria**: Coverage of testable conditions
- **Non-functional Requirements**: Performance, security, usability coverage
- **Integration Requirements**: External system and API requirements

### 2. Design Phase Analysis

#### Status Indicators

- ✅ **Generated**: Design document exists with technical content
- ✅ **Architecture Documented**: Component design and system architecture
- ✅ **Diagrams Present**: Mermaid diagrams and visual representations
- ✅ **Research Integration**: Source citations and research findings
- ✅ **Approval Status**: Check spec.yaml approval state

#### Quality Assessment

- **Component Coverage**: All requirements addressed in design
- **Architecture Alignment**: Consistency with existing system patterns
- **API Design**: Endpoint specifications and data models
- **Testing Strategy**: Comprehensive testing approach defined
- **Security Considerations**: Security requirements addressed

### 3. Tasks Phase Analysis

#### Status Indicators

- ✅ **Generated**: Tasks document with implementation plan
- ✅ **Hierarchical Structure**: Proper numbering (1.1, 1.2, 2.1)
- ✅ **Requirement Mapping**: Task-to-requirement traceability
- ✅ **Coding Focus**: Tasks focus on coding activities
- ✅ **Approval Status**: Check spec.yaml approval state

#### Quality Assessment

- **Task Count**: Total implementation tasks defined
- **Requirement Coverage**: All requirements mapped to tasks
- **Time Estimates**: Realistic 2-4 hour task sizing
- **Dependency Order**: Logical task sequencing
- **Acceptance Criteria**: Clear task completion definition

### 4. Implementation Phase Analysis

#### Progress Tracking

Parse tasks.md checkbox status:

- **Total Tasks**: Count all defined tasks (`- [ ]` and `- [x]`)
- **Completed Tasks**: Count checked tasks (`- [x]`)
- **Pending Tasks**: Count unchecked tasks (`- [ ]`)
- **Completion Percentage**: (Completed / Total) × 100

#### Implementation Quality

Use codebase tool to analyze:

- **Files Modified**: Changed files for this feature
- **Code Integration**: How changes integrate with existing code
- **Pattern Consistency**: Adherence to existing code patterns
- **Testing Coverage**: Unit tests implemented for new code

## Current Status Summary

### Overall Progress

```
📊 Feature: {feature-name}
📅 Created: {creation-date}
📈 Phase: {current-phase}
🎯 Progress: {overall-percentage}%

Phase Breakdown:
├── ✅ Requirements: {requirements-status} ({requirements-percentage}%)
├── ✅ Design: {design-status} ({design-percentage}%)
├── ✅ Tasks: {tasks-status} ({tasks-percentage}%)
└── 🔄 Implementation: {implementation-status} ({implementation-percentage}%)
```

### Approval Status

```
Approvals Required:
├── Requirements: {✅ Approved | ⏳ Pending | ❌ Not Generated}
├── Design: {✅ Approved | ⏳ Pending | ❌ Not Generated}
└── Tasks: {✅ Approved | ⏳ Pending | ❌ Not Generated}
```

## Current Blockers and Issues

### Approval Blockers

Identify what's blocking progress:

- **Requirements pending review**: Human approval needed
- **Design pending review**: Technical design needs validation
- **Tasks pending review**: Implementation plan needs approval

### Technical Issues

Use codebase analysis to identify:

- **Compilation errors**: Code that doesn't compile
- **Test failures**: Failing unit or integration tests
- **Integration problems**: Issues with existing code integration
- **Missing dependencies**: Required libraries or components

### Process Issues

Check for workflow problems:

- **Incomplete specifications**: Missing phase deliverables
- **Sequence violations**: Phases completed out of order
- **Quality gaps**: Standards not met for phase completion

## Quality Metrics Dashboard

### Requirements Quality Score

```
EARS Format Compliance: {percentage}%
Acceptance Criteria Coverage: {percentage}%
Non-functional Requirements: {complete|partial|missing}
Integration Requirements: {complete|partial|missing}
```

### Design Quality Score

```
Architecture Completeness: {percentage}%
Component Coverage: {percentage}%
Testing Strategy: {comprehensive|basic|missing}
Security Considerations: {complete|partial|missing}
```

### Implementation Quality Score

```
Task Completion: {percentage}%
Code Quality: {high|medium|low}
Test Coverage: {percentage}%
Integration Success: {success|issues|pending}
```

## Recommendations and Next Steps

### Immediate Actions Required

Based on current status, provide specific next steps:

#### If in Requirements Phase

- Complete requirements document review
- Validate EARS format compliance
- Approve requirements to proceed to design

#### If in Design Phase

- Review technical design for completeness
- Validate architecture alignment with existing system
- Approve design to proceed to task planning

#### If in Tasks Phase

- Review implementation plan for coverage and feasibility
- Validate task sizing and dependency ordering
- Approve tasks to begin implementation

#### If in Implementation Phase

- Continue with next pending tasks
- Address any identified technical issues
- Validate completed tasks meet acceptance criteria

### Priority Recommendations

1. **Highest Priority**: {Critical blockers or issues}
2. **High Priority**: {Important next steps}
3. **Medium Priority**: {Quality improvements}
4. **Low Priority**: {Optional enhancements}

## Progress Visualization

### Timeline View

```
Requirements ████████████ 100% ✅ Approved
Design       ████████████ 100% ✅ Approved
Tasks        ████████████ 100% ✅ Approved
Implementation ████░░░░░░  40% 🔄 In Progress
```

### Task Breakdown (if in implementation)

```
Data Layer:     ████████████ 100% (3/3 tasks)
API Layer:      ████████░░░░  67% (2/3 tasks)
Frontend:       ░░░░░░░░░░░░   0% (0/4 tasks)
Testing:        ░░░░░░░░░░░░   0% (0/2 tasks)
```

Provide comprehensive visibility into specification progress, quality metrics, and actionable next steps for effective project management and decision-making.
