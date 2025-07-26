---
description: Multi-task execution with AI validation loops and self-correcting implementation
allowed-tools: Bash, Read, Write, Edit, MultiEdit, Update, Glob, Grep, Task, WebSearch, WebFetch
---

# Multi-Task Execution with AI Validation

Execute multiple implementation tasks with self-correcting validation loops for feature: **$ARGUMENTS**

## Pre-Execution Validation

### Implementation Readiness Check

- Spec metadata: @.kiro/specs/$ARGUMENTS/spec.json

### Critical Prerequisites Validation

!`if [ -f ".kiro/specs/$ARGUMENTS/spec.json" ]; then READY=$(cat .kiro/specs/$ARGUMENTS/spec.json | jq -r '.ready_for_implementation // false' 2>/dev/null || echo "false"); MULTI_TASK=$(cat .kiro/specs/$ARGUMENTS/spec.json | jq -r '.multi_task_execution // false' 2>/dev/null || echo "false"); TASKS_APPROVED=$(cat .kiro/specs/$ARGUMENTS/spec.json | jq -r '.approvals.tasks.approved // false' 2>/dev/null || echo "false"); echo "🔍 Readiness Check:"; echo "- Implementation Ready: $READY"; echo "- Multi-task Execution: $MULTI_TASK"; echo "- Tasks Approved: $TASKS_APPROVED"; if [ "$READY" = "true" ] && [ "$TASKS_APPROVED" = "true" ]; then echo "✅ Ready for execution"; else echo "❌ Missing prerequisites - cannot execute"; exit 1; fi; else echo "❌ Spec metadata not found"; exit 1; fi`

**CRITICAL STOP CONDITIONS**:
If any of these conditions are not met, STOP execution immediately:

- `ready_for_implementation: false` → Complete approval workflow first
- `approvals.tasks.approved: false` → Review and approve tasks first
- Missing tasks.md file → Generate tasks first
- No pending tasks found → All tasks already completed

### Task Structure Validation

- Tasks file: @.kiro/specs/$ARGUMENTS/tasks.md
- Requirements: @.kiro/specs/$ARGUMENTS/requirements.md
- Design: @.kiro/specs/$ARGUMENTS/design.md

### Task Parsing and Analysis

!`if [ -f ".kiro/specs/$ARGUMENTS/tasks.md" ]; then TOTAL_TASKS=$(grep -c "^- \[ \]" .kiro/specs/$ARGUMENTS/tasks.md 2>/dev/null || echo "0"); COMPLETED_TASKS=$(grep -c "^- \[x\]" .kiro/specs/$ARGUMENTS/tasks.md 2>/dev/null || echo "0"); PENDING_TASKS=$((TOTAL_TASKS - COMPLETED_TASKS)); echo "📊 Task Analysis:"; echo "- Total tasks: $TOTAL_TASKS"; echo "- Completed: $COMPLETED_TASKS"; echo "- Pending: $PENDING_TASKS"; if [ $PENDING_TASKS -eq 0 ]; then echo "🎉 All tasks completed!"; exit 0; elif [ $PENDING_TASKS -gt 0 ]; then echo "🚀 Ready to execute $PENDING_TASKS pending tasks"; else echo "❌ No valid tasks found"; exit 1; fi; else echo "❌ Tasks file not found"; exit 1; fi`

## Multi-Task Execution Framework

### 1. Task Discovery and Prioritization

#### Parse Pending Tasks

Extract all uncompleted tasks from tasks.md:
!`if [ -f ".kiro/specs/$ARGUMENTS/tasks.md" ]; then echo "📋 Pending Tasks:"; grep -n "^- \[ \]" .kiro/specs/$ARGUMENTS/tasks.md | head -10 | sed 's/^/  /'; else echo "❌ No tasks file"; fi`

#### Dependency Analysis

Analyze task dependencies for execution order:

- **Sequential Tasks**: Must complete before others can start
- **Parallel Tasks**: Can be executed simultaneously  
- **Conditional Tasks**: Dependent on validation outcomes
- **Blocking Tasks**: Must complete before proceeding

#### Task Execution Strategy Selection

**Execution Modes**:

1. **Single Task Mode**: Execute one task, validate, then prompt for next
2. **Multi-Task Sequential**: Execute multiple tasks in sequence with validation
3. **Multi-Task Parallel**: Execute independent tasks in parallel (advanced)

**Default Strategy**: Multi-Task Sequential with validation checkpoints

### 2. Task Execution Loop with AI Validation

#### Core Execution Algorithm

```markdown
FOR each pending task:
1. Parse task details (description, acceptance criteria, EARS mapping)
2. Execute task implementation
3. Update tasks.md to mark as completed
4. Run AI validation using Task tool
5. IF validation passes:
   - Continue to next task
6. IF validation fails:
   - Analyze validation feedback
   - Implement fixes
   - Re-run validation
   - Repeat until validation passes or manual intervention needed
7. Update progress tracking
8. Continue to next task
```

#### Task Execution Implementation

##### Task Parser Function

Extract task information:

- **Task Number**: Hierarchical numbering (1.1.1, 1.1.2, etc.)
- **Task Description**: Implementation details
- **EARS Mapping**: Referenced requirements
- **Acceptance Criteria**: Success conditions
- **Time Estimate**: Planning information

##### Implementation Engine

For each task:

1. **Context Loading**: Load requirements, design, and current codebase state
2. **Implementation**: Write/modify code according to task specification
3. **Testing**: Run relevant tests if specified
4. **Documentation**: Update code documentation as needed

##### Progress Tracking

Real-time updates to tasks.md:

```bash
# Mark task as completed in tasks.md
sed -i 's/^- \[ \] TASK_DESCRIPTION/- [x] TASK_DESCRIPTION/' .kiro/specs/$ARGUMENTS/tasks.md
```

### 3. AI Validation Integration

#### Task Tool Validation Framework

After each task completion, use Task tool for independent validation:

##### Validation Prompt Template

```markdown
Review completed task for: [TASK_DESCRIPTION]

**Validation Criteria**:
1. **Code Correctness**: Does the code compile and run without errors?
2. **Requirement Fulfillment**: Does the implementation satisfy the EARS requirements?
3. **Integration Quality**: Does the code integrate properly with existing codebase?
4. **Testing Coverage**: Are appropriate tests included/updated?
5. **Code Quality**: Does the code follow project conventions and best practices?

**EARS Requirement Reference**: [MAPPED_REQUIREMENTS]
**Acceptance Criteria**: [TASK_ACCEPTANCE_CRITERIA]

**Task Implementation Details**:
[SUMMARY_OF_CHANGES_MADE]

**Validation Instructions**:
- Analyze the implementation thoroughly
- Check for any issues, bugs, or missing requirements
- Verify EARS requirement satisfaction
- Provide specific feedback on any problems found
- Return PASS or FAIL with detailed reasoning

**Required Response Format**:
VALIDATION_RESULT: [PASS/FAIL]
DETAILED_FEEDBACK: [Specific analysis and recommendations]
CRITICAL_ISSUES: [Any blocking issues that must be resolved]
IMPROVEMENT_SUGGESTIONS: [Optional enhancements]
```

#### Validation Response Processing

Parse Task tool response and determine next actions:

- **PASS**: Continue to next task
- **FAIL**: Implement fixes based on feedback and re-validate
- **UNCLEAR**: Request clarification and manual intervention

#### Self-Correcting Loop Implementation

When validation fails:

1. **Analyze Feedback**: Parse specific issues identified by Task tool
2. **Implement Fixes**: Address each identified issue systematically
3. **Re-validate**: Run Task tool validation again with same criteria
4. **Iteration Limit**: Maximum 3 validation attempts before manual intervention
5. **Escalation**: Complex issues that require human decision-making

### 4. Multi-Task Coordination

#### Task Grouping Strategy

Group related tasks for efficient execution:

- **Setup Tasks**: Environment, dependencies, initial configuration
- **Core Implementation**: Main feature development
- **Integration Tasks**: API endpoints, database integration
- **Testing Tasks**: Unit, integration, and E2E tests
- **Documentation Tasks**: Code docs, user guides

#### Parallel Execution Capability

For advanced scenarios, identify tasks that can run in parallel:

- **Independent Components**: Separate frontend/backend tasks
- **Isolated Features**: Non-conflicting functionality
- **Testing Suites**: Different types of tests

#### Progress Monitoring

Real-time progress tracking:

- **Task Completion Percentage**: Visual progress indicators
- **Validation Success Rate**: Quality metrics
- **Time Tracking**: Actual vs estimated time
- **Issue Resolution**: Self-correction effectiveness

### 5. Advanced Validation Features

#### Context-Aware Validation

Validation considers:

- **EARS Requirements**: Specific requirement satisfaction
- **Design Alignment**: Consistency with approved design
- **Codebase Integration**: Harmony with existing patterns
- **Quality Standards**: Code quality and best practices

#### Validation History Tracking

Maintain validation history:

- **Validation Attempts**: Number of validation cycles per task
- **Issue Patterns**: Common validation failures
- **Resolution Strategies**: Successful fix approaches
- **Learning Integration**: Improve validation over time

#### Smart Validation Escalation

Escalate to human intervention when:

- **Multiple Validation Failures**: More than 3 failed attempts
- **Complex Design Questions**: Architectural decisions needed
- **External Dependencies**: Issues outside code control
- **Ambiguous Requirements**: Unclear EARS requirements

## Execution Workflow Implementation

### Phase 1: Initialization and Setup

1. **Validate Prerequisites**: Ensure all approvals and files exist
2. **Parse Task Structure**: Extract and prioritize pending tasks
3. **Set Up Execution Environment**: Prepare validation framework
4. **Initialize Progress Tracking**: Set up real-time monitoring

### Phase 2: Task Execution Cycle

```markdown
REPEAT until all tasks completed OR manual intervention needed:
  1. SELECT next pending task based on dependencies
  2. LOAD task context (description, requirements, acceptance criteria)
  3. IMPLEMENT task according to specifications
  4. UPDATE tasks.md to mark task as completed
  5. VALIDATE implementation using Task tool
  6. IF validation PASSES:
     - LOG success and continue to next task
  7. IF validation FAILS:
     - ANALYZE feedback and implement fixes
     - RE-VALIDATE with same criteria
     - REPEAT validation cycle (max 3 attempts)
     - IF still failing: ESCALATE to manual intervention
  8. UPDATE progress tracking and statistics
```

### Phase 3: Completion and Reporting

1. **Final Validation**: Comprehensive system validation
2. **Progress Summary**: Complete execution report
3. **Quality Metrics**: Validation success rates and issues
4. **Next Steps**: Recommendations for post-implementation

## Error Handling and Recovery

### Validation Failure Recovery

When Task tool validation fails:

1. **Parse Specific Issues**: Extract actionable feedback
2. **Categorize Problems**: Code bugs, requirement misalignment, integration issues
3. **Implement Targeted Fixes**: Address each issue systematically
4. **Incremental Validation**: Validate fixes individually when possible

### Execution Error Handling

Handle implementation errors gracefully:

- **Compilation Errors**: Fix syntax and type issues
- **Runtime Errors**: Debug and resolve execution problems
- **Integration Errors**: Resolve API and service integration issues
- **Test Failures**: Fix failing tests and ensure coverage

### Manual Intervention Points

Clearly defined escalation criteria:

- **Complex Architectural Decisions**: Beyond automated capability
- **Ambiguous Requirements**: Need clarification or additional specification
- **External Dependencies**: Issues with APIs, services, or infrastructure
- **Quality Standards**: Subjective decisions about code quality

## Progress Reporting and Monitoring

### Real-Time Progress Updates

!`echo "📊 Execution Progress:"; if [ -f ".kiro/specs/$ARGUMENTS/tasks.md" ]; then TOTAL=$(grep -c "^- \[" .kiro/specs/$ARGUMENTS/tasks.md); COMPLETED=$(grep -c "^- \[x\]" .kiro/specs/$ARGUMENTS/tasks.md); if [ $TOTAL -gt 0 ]; then PERCENT=$((COMPLETED * 100 / TOTAL)); echo "- Progress: $COMPLETED/$TOTAL tasks ($PERCENT%)"; else echo "- No tasks found"; fi; fi`

### Validation Success Metrics

Track validation effectiveness:

- **First-Pass Success Rate**: Tasks that pass validation immediately
- **Average Validation Cycles**: Iterations needed per task
- **Issue Categories**: Types of problems commonly found
- **Resolution Time**: Time spent on validation and fixes

### Quality Assurance Metrics

Monitor implementation quality:

- **EARS Requirement Coverage**: Percentage of requirements implemented
- **Code Quality Score**: Based on validation feedback
- **Integration Success**: Seamless integration with existing code
- **Test Coverage**: Automated test coverage achieved

## Instructions for Multi-Task Execution

### 1. Pre-Execution Checklist

- ✅ Verify all approvals are in place
- ✅ Confirm task structure is valid and complete
- ✅ Ensure development environment is ready
- ✅ Set up validation framework and progress tracking

### 2. Execution Best Practices

- **Start with setup tasks**: Foundation before feature implementation
- **Validate incrementally**: Don't batch multiple tasks before validation
- **Address issues immediately**: Fix validation failures before proceeding
- **Track progress continuously**: Update tasks.md in real-time
- **Escalate when appropriate**: Don't persist with failing validation cycles

### 3. Quality Assurance

- **Every task must pass validation**: No exceptions for quality standards
- **EARS requirements are mandatory**: All implementations must satisfy EARS requirements
- **Integration testing is required**: Ensure compatibility with existing codebase
- **Documentation standards**: Maintain code documentation throughout

### 4. Success Criteria

- **All tasks completed**: 100% task completion rate
- **All validations passed**: No pending validation failures
- **EARS requirements satisfied**: Complete requirement coverage
- **Quality standards met**: Code quality and integration standards achieved

Execute multi-task implementation with AI-powered validation loops, ensuring high-quality, requirement-compliant code delivery through self-correcting automation.
