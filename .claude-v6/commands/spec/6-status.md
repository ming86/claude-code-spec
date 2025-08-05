---
description: 'Comprehensive status tracking and progress analysis for spec-driven development'
argument-hint: '[feature-name]'
---

# Role and Objective

Provide comprehensive progress tracking and quality assessment for spec-driven development features with accurate, actionable status reports including detailed quality metrics and recommendations.

# Instructions

## Analysis Requirements

- **Analysis Focus**: Parse and analyze specification files, metadata, and implementation progress
- **File Analysis**: Examine `.spec-workflow/specs/{feature}/` directory structure and contents
- **Progress Calculation**: Calculate completion percentages and phase status based on actual file contents
- **Quality Assessment**: Evaluate compliance with format standards (EARS, task structure, etc.)
- **Actionable Insights**: Provide specific, prioritized recommendations for next steps

## Anti-Shortcut Quality Patterns

- Analyze actual file contents and metadata rather than making assumptions about progress status
- Calculate progress metrics based on verifiable data from tasks.md and spec.yaml, not estimates
- Generate recommendations based on systematic analysis of current state, not generic advice
- Validate file existence and accessibility before making status claims

# Execution Steps

## Step 1: File Structure Verification and Accessibility

**Objective**: Check existence and accessibility of all specification files

**Process**:

- Verify `.spec-workflow/specs/{feature}/` directory exists and is accessible
- Check for presence of all required specification files (spec.yaml, requirements.md, design.md, tasks.md)
- Validate file accessibility and basic formatting
- Document any missing or inaccessible files with specific impact on analysis

## Step 2: Phase Status Analysis

**Objective**: Analyze each phase for completion, quality, and approval status

### Phase Analysis Process

#### 1. Specification Initialization Status

- **Directory Structure**: Verify complete spec directory organization
- **Metadata Configuration**: Parse spec.yaml for basic configuration and timestamps
- **Template Quality**: Assess whether templates contain project-specific content

#### 2. Requirements Phase Status

- **Generation Status**: Check if requirements.md exists and contains substantive content
- **EARS Compliance**: Count functional requirements using proper EARS format (WHEN/THEN)
- **Approval Status**: Parse spec.yaml for requirements approval state
- **Quality Metrics**: Analyze requirement completeness and acceptance criteria coverage

#### 3. Design Phase Status

- **Generation Status**: Check if design.md exists with technical content
- **Architecture Documentation**: Verify component design and system architecture sections
- **Diagram Presence**: Check for mermaid diagrams and visual representations
- **Approval Status**: Parse spec.yaml for design approval state

#### 4. Implementation Planning Status

- **Generation Status**: Check if tasks.md exists with implementation plan
- **Task Structure**: Verify hierarchical numbering (1.1, 1.2, 2.1) and format compliance
- **Requirement Mapping**: Validate task-to-requirement traceability
- **Approval Status**: Parse spec.yaml for tasks approval state

#### 5. Implementation Execution Status

- **Progress Tracking**: Parse tasks.md to count total tasks vs completed tasks ([x] vs [ ])
- **Completion Percentage**: Calculate (Completed Tasks / Total Tasks) × 100
- **Phase Analysis**: Break down completion by implementation phases if structured
- **Quality Assessment**: Analyze implementation quality through codebase examination

## Step 3: Progress Calculation and Metrics

**Objective**: Calculate accurate completion percentages and phase status based on actual file contents

### Progress Calculation Methods

#### Overall Progress Calculation

```markdown
Phase Weighting:
- Initialization: 10%
- Requirements: 25%
- Design: 25%
- Implementation Planning: 15%
- Implementation Execution: 25%

Overall Progress = Sum of (Phase Completion × Phase Weight)
```

#### Implementation Progress Detail

- **Total Tasks**: Count all defined tasks in tasks.md
- **Completed Tasks**: Count tasks marked with [x]
- **Pending Tasks**: Count tasks marked with [ ]
- **Implementation Percentage**: (Completed / Total) × 100

## Step 4: Quality Metrics Assessment

**Objective**: Evaluate compliance with format standards and best practices

### Quality Assessment Areas

#### Requirements Quality

- **EARS Format Compliance**: Percentage of functional requirements using WHEN/THEN format
- **Acceptance Criteria Coverage**: Requirements with specific, testable acceptance criteria
- **Non-functional Coverage**: Performance, security, usability requirements present
- **Integration Requirements**: External system and API requirements documented

#### Design Quality

- **Architecture Completeness**: All system components and interactions documented
- **Component Coverage**: All requirements addressed in design with clear traceability
- **Testing Strategy**: Comprehensive testing approach defined
- **Visual Documentation**: Mermaid diagrams and architecture visualizations present

#### Implementation Quality

- **Task Completion**: Percentage of implementation tasks completed
- **Code Integration**: How well changes integrate with existing codebase
- **Pattern Consistency**: Adherence to existing code patterns and conventions
- **Test Coverage**: Unit and integration tests implemented per plan

## Step 5: Blocker Identification and Resolution

**Objective**: Identify approval, technical, and process blockers with specific resolution steps

### Blocker Categories

#### Approval Blockers

- **Requirements Pending Review**: Human approval needed for requirements phase
- **Design Pending Review**: Technical design needs validation and approval
- **Tasks Pending Review**: Implementation plan needs approval before execution

#### Technical Issues

- **Compilation Errors**: Code that doesn't compile or has syntax errors
- **Test Failures**: Failing unit or integration tests blocking progress
- **Integration Problems**: Issues with existing code integration
- **Missing Dependencies**: Required libraries or components not available

#### Process Issues

- **Incomplete Specifications**: Missing phase deliverables or incomplete content
- **Sequence Violations**: Phases completed out of proper sequential order
- **Quality Gaps**: Standards not met for phase completion requirements

## Step 6: Recommendations and Next Steps Generation

**Objective**: Provide prioritized, actionable next steps based on current status analysis

### Recommendation Categories

#### Immediate Actions Required (based on current phase)

- **If in Requirements Phase**: Complete requirements document review and validation
- **If in Design Phase**: Review technical design for completeness and architectural alignment
- **If in Tasks Phase**: Review implementation plan for coverage and feasibility
- **If in Implementation Phase**: Continue with next pending tasks or address identified issues

#### Priority Recommendations (based on analysis findings)

1. **Highest Priority**: Critical blockers or issues preventing any progress
2. **High Priority**: Important next steps for advancing current phase
3. **Medium Priority**: Quality improvements and process optimizations
4. **Low Priority**: Optional enhancements and future considerations

# Output Requirements

## Status Report Structure

### Executive Summary

```markdown
## Status Report: {Feature Name}

### Overall Progress: {percentage}%

**Current Phase**: {current-phase}
**Status**: {✅ On Track | ⚠️ Issues Identified | ❌ Blocked}
**Last Updated**: {timestamp}

### Phase Breakdown

├── ✅ Initialization: Complete (100%)
├── ⚠️ Requirements: In Progress (75%)
├── ⏳ Design: Pending (0%)
└── ⏳ Implementation: Pending (0%)
```

### Detailed Phase Analysis

```markdown
### Phase Status Details

#### Requirements Phase

- **Status**: ✅ Generated, ⏳ Pending Approval
- **Quality Score**: 85% (EARS compliance, acceptance criteria coverage)
- **Issues**: 2 requirements lack specific acceptance criteria
- **Next Action**: Human review and approval required

#### Implementation Phase (if applicable)

- **Progress**: 6 of 12 tasks completed (50%)
- **Current Task**: 2.3 - User registration API endpoint
- **Blockers**: None identified
- **Estimated Completion**: 2-3 days at current pace
```

### Quality Dashboard

```markdown
### Quality Metrics

#### Requirements Quality

- EARS Format Compliance: 92%
- Acceptance Criteria Coverage: 88%
- Non-functional Requirements: Complete
- Integration Requirements: Complete

#### Implementation Quality (if applicable)

- Task Completion: 50%
- Code Quality: High (follows existing patterns)
- Test Coverage: 85%
- Integration Success: No issues detected
```

### Visual Progress Indicators

```markdown
### Progress Visualization

#### Timeline View

Requirements ████████████ 100% ✅ Approved
Design       ████████████ 100% ✅ Approved
Tasks        ████████████ 100% ✅ Approved
Implementation ████░░░░░░  40% 🔄 In Progress

#### Task Breakdown (if in implementation)

Data Layer:     ████████████ 100% (3/3 tasks)
API Layer:      ████████░░░░  67% (2/3 tasks)
Frontend:       ░░░░░░░░░░░░   0% (0/4 tasks)
Testing:        ░░░░░░░░░░░░   0% (0/2 tasks)
```

### Actionable Recommendations

```markdown
### Next Steps

#### Immediate Actions (Priority 1)

1. **Review and approve requirements** - Human approval needed to proceed to design
2. **Address missing acceptance criteria** - REQ-2.3 and REQ-3.1 need specific conditions

#### Upcoming Actions (Priority 2)

1. **Prepare for design phase** - Technical design can begin after requirements approval
2. **Plan implementation approach** - Consider team availability and dependencies

#### Quality Improvements (Priority 3)

1. **Enhance acceptance criteria specificity** - Make all criteria measurable and testable
2. **Add performance benchmarks** - Include specific performance requirements
```

# Status Categories

**✅ Complete**: All deliverables present and approved
**🔄 In Progress**: Work started but not completed
**⏳ Pending**: Waiting for previous phase completion
**❌ Issues**: Problems identified requiring attention

# Quality Assessment Areas

**Requirements Quality**: EARS format compliance, acceptance criteria coverage, completeness
**Design Quality**: Architecture completeness, integration planning, testing strategy
**Implementation Quality**: Code integration, pattern consistency, testing coverage

# Reporting Requirements

**Executive Summary**: High-level completion percentage, current phase, key blockers, timeline
**Detailed Breakdown**: Phase-by-phase status, task completion details, quality metrics
**Visual Progress**: Clear status indicators and progress visualization
**Recommendations**: Specific next steps and priority actions

# Examples

## Argument Handling

```bash
/spec:6-status user-authentication-system
/spec:6-status payment-processing-integration
/spec:6-status real-time-notifications
```

## Status Analysis Examples

### Early Phase Status

```markdown
## Status Report: User Authentication System

### Overall Progress: 65%

**Current Phase**: Requirements Review
**Status**: ⚠️ Issues Identified
**Last Updated**: 2024-01-15 14:30

**Key Issues**:
- 3 requirements lack specific acceptance criteria
- Non-functional performance requirements need metrics
- Awaiting human approval to proceed to design phase

**Next Action**: Address requirement quality issues, then seek approval
```

### Implementation Phase Status

```markdown
## Status Report: Payment Processing Integration

### Overall Progress: 78%

**Current Phase**: Implementation Execution
**Status**: ✅ On Track
**Last Updated**: 2024-01-15 16:45

**Progress Details**:
- 8 of 12 implementation tasks completed (67%)
- Current: Task 3.2 - Payment gateway integration
- No blockers identified
- Testing phase scheduled to begin tomorrow

**Next Action**: Continue with remaining API integration tasks
```

## Complete Status Report Example

```markdown
## Status Report: User Profile Management

### Overall Progress: 82%

**Current Phase**: Implementation Execution
**Status**: ✅ On Track
**Last Updated**: 2024-01-15 10:30

### Phase Breakdown

├── ✅ Initialization: Complete (100%)
├── ✅ Requirements: Complete (100%) - Approved
├── ✅ Design: Complete (100%) - Approved
├── ✅ Tasks: Complete (100%) - Approved
└── 🔄 Implementation: In Progress (67%)

### Phase Status Details

#### Implementation Phase

- **Progress**: 8 of 12 tasks completed (67%)
- **Current Task**: 3.1 - Frontend user profile form
- **Recently Completed**: User profile API endpoints (Tasks 2.1-2.3)
- **Blockers**: None identified
- **Estimated Completion**: 1-2 days

### Quality Metrics

#### Requirements Quality ✅

- EARS Format Compliance: 95%
- Acceptance Criteria Coverage: 100%
- Non-functional Requirements: Complete
- Integration Requirements: Complete

#### Design Quality ✅

- Architecture Completeness: 100%
- Component Coverage: All requirements addressed
- Testing Strategy: Comprehensive plan defined
- Visual Documentation: Complete with mermaid diagrams

#### Implementation Quality 🔄

- Task Completion: 67%
- Code Quality: High (follows existing patterns)
- Test Coverage: 88% (exceeds project standard)
- Integration Success: No issues detected

### Progress Visualization

#### Timeline View

Requirements ████████████ 100% ✅ Approved
Design       ████████████ 100% ✅ Approved
Tasks        ████████████ 100% ✅ Approved
Implementation ████████░░░░  67% 🔄 In Progress

#### Task Breakdown

Data Layer:     ████████████ 100% (3/3 tasks)
API Layer:      ████████████ 100% (3/3 tasks)
Frontend:       ████░░░░░░░░  25% (1/4 tasks)
Testing:        ░░░░░░░░░░░░   0% (0/2 tasks)

### Next Steps

#### Immediate Actions (Priority 1)

1. **Continue frontend development** - Complete user profile form (Task 3.1)
2. **Prepare for testing phase** - Testing tasks ready to begin after frontend completion

#### Upcoming Actions (Priority 2)

1. **Execute testing phase** - Unit and integration tests (Tasks 4.1-4.2)
2. **Final integration validation** - Ensure all components work together

#### Success Criteria

- All 12 implementation tasks completed
- Test coverage maintains >85%
- No integration issues detected
- Feature ready for deployment

### Quality Assurance

- **Code Standards**: All code follows project conventions
- **Testing Strategy**: On track to complete as planned
- **Integration**: Seamless integration with existing user management
- **Performance**: Response times meet design specifications
```

# Quality Validation

## Analysis Completion Criteria

- [ ] All specification files verified for existence and accessibility
- [ ] Phase status analyzed based on actual file contents and metadata
- [ ] Progress metrics calculated using verifiable data from task completion
- [ ] Quality assessments based on concrete format compliance and content analysis
- [ ] Blockers identified with specific resolution approaches
- [ ] Recommendations prioritized and made actionable based on current state
- [ ] Visual progress indicators accurately reflect analyzed status
- [ ] Report provides clear next steps for project advancement

## Accuracy Standards

- [ ] All progress percentages based on actual task completion counts
- [ ] Quality scores derived from measurable criteria (EARS compliance, acceptance criteria coverage)
- [ ] All status claims supported by evidence from file analysis
- [ ] Blocker identification based on systematic analysis of approval states and technical issues
- [ ] Recommendations tailored to specific current state rather than generic advice

Provide comprehensive, accurate visibility into specification progress, quality metrics, and actionable next steps for effective project management and decision-making.
