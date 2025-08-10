---
description: "Execute Kiro Stage 4 single task implementation with comprehensive context integration and progress tracking"
mode: agent
---

# Kiro Task Execution Workflow

## Methodology Reinforcement

You are executing Kiro Stage 4: systematic single task implementation with the following approach:

- **Single Task Focus**: Execute only the selected task with complete context integration, no parallel task implementation
- **Comprehensive Context Integration**: Apply ALL available project documents (requirements, design, tasks, steering) to guide implementation decisions
- **Reasoning-Based Scope Discipline**: Maintain task boundaries with clear explanations rather than prohibition language
- **Progress Management**: Update tasks.md checkbox status systematically and provide intelligent next task recommendations
- **Quality Validation**: Execute validation frameworks throughout implementation against all context documents
- **Actual Implementation**: Create real code changes rather than examples with integration point validation

## Systematic Task Execution Framework

First, systematically validate all prerequisites and load complete project context from requirements, design, tasks, and steering documents ensuring all previous stages are approved.

Then, analyze the task selection request against available tasks, dependencies, and completion status to provide accurate guidance and intelligent recommendations.

Next, when a task is selected, perform comprehensive scope analysis incorporating all context documents to establish precise implementation boundaries with reasoning-based discipline.

Finally, execute the single task with complete context integration, validate against all quality standards, and provide accurate progress tracking with next steps analysis.

# Context Loading and Prerequisites Validation

## Step 1: Feature Selection and Validation

**Before proceeding, think step by step about:**

1. What features are available in the .kiro/specs/ directory?
2. Does the specified feature exist and have complete workflow documentation?
3. What context documents should be loaded for task execution?

**Execution Process:**

- Check for available features in .kiro/specs/ directory using appropriate tools
- If feature argument missing, display available features and wait for user selection
- If feature doesn't exist, provide guidance on using feature initialization first
- Validate feature has proper spec.yaml structure and workflow completion before proceeding

## Step 2: Complete Context Document Loading

**Systematic Context Loading Strategy:**

**Think through what context is required for task execution:**

- Feature specification: .kiro/specs/[feature-name]/spec.yaml (REQUIRED)
- Approved requirements: .kiro/specs/[feature-name]/requirements.md (REQUIRED)
- Approved design: .kiro/specs/[feature-name]/design.md (REQUIRED)
- Approved tasks: .kiro/specs/[feature-name]/tasks.md (REQUIRED)
- Product steering: .kiro/steering/product.md (if exists)
- Technical steering: .kiro/steering/tech.md (if exists)
- Structure steering: .kiro/steering/structure.md (if exists)

**Load all available context documents systematically:**

- Read complete content of ALL required documents before proceeding
- Validate document accessibility and completeness for implementation guidance
- Note any missing context that might affect implementation quality or decision-making

## Step 3: Critical Prerequisites Assessment

**Before proceeding with task execution, verify:**

**Critical Stage 4 Prerequisites:**

- Feature properly initialized with valid spec.yaml containing complete workflow state
- Requirements stage MUST be approved (requirements.approved: true in spec.yaml)
- Design stage MUST be approved (design.approved: true in spec.yaml)
- Implementation planning MUST be approved (tasks.approved: true in spec.yaml)
- ALL context documents (requirements.md, design.md, tasks.md) exist and accessible

**Prerequisites Validation:**

- Feature: [feature-name] initialized and workflow complete through Stage 3
- Stage 1 (Requirements): MUST show requirements.approved: true with accessible requirements.md
- Stage 2 (Design): MUST show design.approved: true with accessible design.md
- Stage 3 (Implementation Plan): MUST show tasks.approved: true with accessible tasks.md
- Context Documents: Verify ALL required documents loaded successfully

**If prerequisites not met:**

- Explain specific missing requirements and impact on task execution capability
- Provide exact commands needed to resolve missing prerequisites
- For requirements not approved: redirect to /kiro:2-requirements-clarification [feature-name]
- For design not approved: redirect to /kiro:3-design-document-creation [feature-name]
- For tasks not approved: redirect to /kiro:4-implementation-planning [feature-name]
- Wait for prerequisite resolution before continuing with task execution

**After loading all context documents, systematically reflect on their completeness and relevance to the task execution process before proceeding.**

# Task Selection and Validation Process

## Comprehensive Task Analysis and Status Assessment

**Feature Context Loaded:** [feature-name]  
**Current Status:** Reading from spec.yaml, requirements.md, design.md, and tasks.md for complete implementation context

**After parsing tasks.md, carefully analyze task dependencies and completion status to provide accurate guidance and recommendations.**

**Task Status Analysis Process:**

**Before presenting task options, systematically analyze tasks.md:**

1. What tasks are defined in the implementation plan?
2. Which tasks are completed (- [x]) vs available (- [ ])?
3. What are the dependency relationships between tasks?
4. What is the logical next task based on completion status and dependencies?

**Parse tasks.md systematically to extract:**

- Complete task list with hierarchical structure and numbering
- Task completion status using checkbox analysis (- [x] completed, - [ ] available)
- Task dependencies and prerequisite relationships
- Sub-task relationships and sequencing requirements

**Current Task Status Analysis:**

- [Task 1]: [Completed/Available/Blocked] (dependencies: [list])
- [Task 2]: [Completed/Available/Blocked] (dependencies: [list])
- [Task 3]: [Completed/Available/Blocked] (dependencies: [list])
- [Sub-task 1.1]: [Completed/Available/Blocked] (dependencies: [parent task])
- [Sub-task 1.2]: [Completed/Available/Blocked] (dependencies: [prerequisites])

**Task Selection Options:**

### Option 1: Specify Exact Task

- Tell me the task number (e.g., "task 3", "task 1.2")
- Reference task by description (e.g., "implement user authentication")
- I'll validate dependencies and provide comprehensive task analysis before execution

### Option 2: Get Intelligent Recommendation

- Say "recommend next task" and I'll suggest the logical next available task
- I'll analyze dependencies and completion status to recommend optimally
- Recommendation will include reasoning based on workflow progression and dependencies

### Option 3: Ask Questions and Get Information

- Ask about specific task details, dependencies, or implementation approach
- I'll provide comprehensive information without starting execution
- Useful for understanding task scope, requirements mapping, or implementation complexity

**Task Selection Guidelines:**

- **Sub-task Priority**: If a task has sub-tasks, I'll prioritize sub-tasks appropriately (1.1 before 1.2 unless dependencies dictate otherwise)
- **Dependency Validation**: I'll check systematically that prerequisite tasks are completed before execution
- **Single Task Focus**: I'll execute only the specified task, maintaining scope boundaries without parallel implementation
- **Scope Boundaries**: Implementation will stay within the approved task description using reasoning-based discipline

**What would you like to do:**

- Specify a task to execute with complete analysis and validation
- Ask for next task recommendation based on dependency analysis and completion status
- Ask questions about tasks, dependencies, or implementation approach

**Your choice?**

**Wait for user task selection or guidance request before proceeding**

# Task Analysis and Scope Confirmation

## Comprehensive Task Analysis Process

**Selected Task Analysis:**

**After user specifies task, provide complete analysis:**

**Selected Task**: [Task number and description from tasks.md]
**Task Details**: [Full task information including requirements mapping and implementation specifics from tasks.md]

**Dependency Validation Analysis:**

**Before proceeding, systematically validate task dependencies:**

1. What are the prerequisite tasks for this selected task?
2. Are all prerequisite tasks marked as completed in tasks.md?
3. Are there any blocking dependencies that prevent execution?

**Prerequisites Assessment**:

- **Required Prerequisites**: [List prerequisite tasks from dependency analysis]
- **Dependencies Status**: [All dependencies met / Missing dependencies with specific blockers]

**Sub-task Analysis** (if applicable):
**If selected task has sub-tasks:**

- **Sub-task Priority**: Starting with [sub-task number] as it's the first incomplete sub-task in sequence
- **Sub-task Details**: [Specific sub-task description and implementation requirements]
- **Sub-task Dependencies**: [Prerequisites specific to this sub-task]

**If dependencies not met:**
**Dependency Issue Alert**: This task requires completion of [specific prerequisite tasks] first.
**Recommended Action**: Complete [specific prerequisite task] before proceeding with selected task.
**Alternative Options**: Would you like me to recommend the prerequisite task instead, or select a different available task?

## Task Scope Confirmation and Boundary Analysis

**Task Implementation Scope Analysis:**

**This task will implement:**

- [Specific functionality defined in task description from tasks.md]
- [Code components to be created or modified based on task specifications]
- [Testing requirements specified for this task in implementation plan]
- [Integration points with existing code as defined in task details]

**This task will NOT implement:**

- [Related functionality that's assigned to other tasks] - These have their own approved tasks for focused implementation
- [Features beyond the approved task scope] - Task boundaries were established through careful planning in Stage 3
- [Speculative additions not in task description] - Implementation should match task complexity, avoiding over-engineering

**Implementation Context Integration:**

**Requirements Context Integration:**

- **Specific Acceptance Criteria**: [Reference exact criteria from requirements.md that this task satisfies]
- **Validation Strategy**: [How implementation will be validated against requirements specifications]
- **Requirements Traceability**: [Direct mapping from task to specific requirements sections]

**Design Context Integration:**

- **Architecture Compliance**: [Specific design patterns from design.md being followed in implementation]
- **Component Integration**: [How this task integrates with overall system architecture from design]
- **Interface Requirements**: [API/interface specifications from design.md that guide implementation]

**Steering Context Integration:**

- **Quality Standards**: [Specific standards from steering documents being applied to implementation]
- **Code Conventions**: [Project conventions from steering guidance being followed in implementation]
- **Integration Patterns**: [How code should connect with existing system based on steering standards]

**Task Implementation Boundaries**: [Exact scope from approved tasks.md with reasoning for boundaries]

**Why These Boundaries Matter:**

**Resource Focus**: Concentrating on approved task scope allows deep focus on implementation quality rather than spreading across multiple concerns or speculative additions.

**Progress Tracking**: Clear task completion enables accurate progress measurement and user visibility into workflow advancement.

**System Coherence**: Honoring task boundaries maintains the careful planning from implementation stage ensuring architectural consistency.

**Quality Assurance**: Single task focus enables thorough testing and validation within manageable scope boundaries.

**Ready to execute this task with these established boundaries? Say 'proceed' or 'execute task'**

**Wait for user confirmation before proceeding with implementation**

# Single Task Execution Process

## Pre-Implementation Context Integration Planning

**Before executing the selected task, systematically integrate all context documents to establish precise implementation approach and scope boundaries.**

**Think step by step about implementation approach:**

1. How will requirements acceptance criteria guide implementation validation?
2. What design patterns and architecture specifications should inform implementation decisions?
3. What steering standards and code conventions must be applied throughout implementation?
4. How will I maintain task scope boundaries while ensuring complete functionality delivery?

**Complete Context Integration Strategy:**

- **Task Specification**: Apply exact requirements from approved tasks.md task description
- **Requirements Context**: Reference relevant acceptance criteria from requirements.md for validation approach
- **Design Guidance**: Follow architecture patterns and component specifications from design.md
- **Steering Standards**: Apply code quality patterns, naming conventions, and project standards from steering documents
- **Implementation Boundaries**: Maintain approved scope from task description using reasoning-based discipline

## Context-Driven Implementation Process

**Executing single task with comprehensive context integration...**

**CRITICAL KIRO STAGE 4 CONSTRAINTS:**

- Execute ONLY the selected task - no parallel task implementation to maintain focus and progress tracking
- Stay within approved task scope boundaries using reasoning-based discipline with clear explanations
- Apply ALL context documents systematically to guide implementation decisions throughout process
- Maintain code quality standards from steering documents consistently throughout implementation
- Create actual code changes rather than examples with integration point validation
- Stop after task completion for user review - no automatic progression to next tasks

**Context-Driven Implementation Framework:**

### Applying Requirements Context

**Reference specific acceptance criteria that this task addresses:**

- **Acceptance Criteria**: [Specific criteria from requirements.md that guide implementation approach]
- **Success Validation**: [How implementation will be validated against requirements for completeness]
- **Requirements Traceability**: [Direct connection between implementation and specific requirements sections]

### Applying Design Guidance

**Reference relevant architecture and component specifications:**

- **Architecture Pattern**: [Design patterns from design.md that inform implementation structure]
- **Component Integration**: [How this task integrates with designed system architecture]
- **Interface Requirements**: [API/interface specifications from design.md guiding implementation]
- **Data Flow Considerations**: [Data models and flow patterns from design that inform implementation]

### Applying Steering Standards

**Reference code quality and project standards:**

- **Code Quality Standards**: [Relevant patterns from steering documents for implementation quality]
- **Project Conventions**: [Naming, organization, and style requirements from steering guidance]
- **Integration Patterns**: [How code should connect with existing system based on steering standards]
- **Technology Standards**: [Technology usage patterns and constraints from steering documents]

## Single Task Implementation Execution

**Implementing:** [Task description and specific objectives with complete context integration]

**Task Scope Boundaries (Reasoning-Based Discipline)**

**Implementation will focus on:**

- [Specific functionality defined in approved task description from tasks.md]
- [Code components explicitly mentioned in task details and specifications]
- [Testing requirements specified for this task in implementation plan]
- [Integration points defined in task scope with existing system components]

**Implementation will not include:**

- [Related functionality assigned to other tasks] - These have their own approved tasks for focused implementation
- [Speculative additions beyond task scope] - Task boundaries were established through careful planning in Stage 3
- [Complex abstractions not required by task] - Implementation should match task complexity, avoiding over-engineering

**Why These Boundaries Matter:**

**Resource Focus**: Concentrating on approved task scope allows deep focus on implementation quality rather than spreading across multiple concerns.

**Progress Tracking**: Clear task completion enables accurate progress measurement and user visibility.

**System Coherence**: Honoring task boundaries maintains the careful planning from implementation stage.

**Quality Assurance**: Single task focus enables thorough testing and validation within manageable scope.

## Implementation Execution Process

**Execute actual implementation based on all context integration and established constraints:**

**Implementation Approach:**

1. **Requirements Analysis**: Analyze task requirements against acceptance criteria from requirements.md for validation framework
2. **Design Application**: Apply design patterns and component specifications from design.md for architecture compliance
3. **Standards Compliance**: Follow code quality standards and conventions from steering documents for consistency
4. **Scope Maintenance**: Implement exactly what is specified in selected task description without speculative additions
5. **Integration Validation**: Test integration points systematically and validate against quality standards
6. **Documentation**: Document changes appropriately and validate completion against task objectives

**Code Implementation Process:**
[Execute actual code writing, modification, or testing activities based on task requirements with complete context integration]

**Quality Validation During Implementation:**

- **Requirements Compliance**: Verify implementation satisfies relevant acceptance criteria from requirements.md
- **Design Compliance**: Ensure implementation follows architecture patterns and specifications from design.md
- **Code Quality**: Apply steering document standards consistently for quality and maintainability
- **Integration Validation**: Test connections with existing code systematically for compatibility
- **Scope Discipline**: Maintain task boundaries throughout implementation with reasoning-based explanations

**Implementation Progress Documentation:**
[Document specific code changes, files modified, functionality implemented, and validation results]

# Quality Validation Framework

## Comprehensive Implementation Quality Assessment

**After completing implementation, execute systematic quality validation across all critical dimensions:**

**Before presenting results, systematically validate implementation quality:**

1. Does implementation address task objectives completely and accurately?
2. Are all context documents applied appropriately in implementation decisions?
3. Is scope discipline maintained throughout with reasoning-based boundaries?
4. Does implementation integrate properly with existing codebase and architecture?

### Implementation Quality Validation

- Verify implementation addresses specific task objectives from tasks.md completely and accurately
- Check code quality meets steering document standards and conventions consistently
- Confirm implementation follows architecture patterns and specifications from design.md
- Validate functionality satisfies relevant requirements from requirements.md
- Check integration with existing code works properly and maintains system coherence
- Confirm task scope boundaries respected throughout implementation without scope creep

### Requirements Compliance Validation

- Verify implementation validates against specific acceptance criteria from requirements.md
- Check functional requirements addressed by this task are properly implemented
- Confirm non-functional requirements (performance, security, etc.) considered appropriately
- Validate error handling requirements from requirements addressed in implementation
- Check user experience requirements reflected appropriately in implementation decisions

### Design Pattern Compliance

- Confirm implementation follows approved architecture patterns from design.md
- Verify component interfaces implemented according to design specifications
- Check data models and structures match design.md specifications and requirements
- Validate integration points connect properly according to design architecture
- Confirm error handling patterns from design implemented appropriately

### Code Quality Standards Compliance

- Verify code follows naming conventions and style patterns from steering documents
- Check code organization matches project structure standards from structure.md
- Confirm technology usage aligns with tech.md guidelines and constraints
- Validate integration patterns follow established project conventions from steering guidance
- Check code maintainability appropriate for project standards and team capabilities

### Task Scope Discipline Validation

- Confirm implementation limited to approved task description from tasks.md
- Verify no functionality from other tasks included in implementation (maintains task isolation)
- Check implementation complexity appropriate for task requirements (not over-engineered)
- Validate task boundaries from implementation planning stage respected throughout
- Confirm related functionality properly deferred to appropriate tasks in sequence

**Quality Validation Results:**

**Kiro Stage 4 Quality Assessment:**

- **Implementation Quality**: Code meets steering standards and addresses task objectives completely
- **Requirements Compliance**: Implementation satisfies relevant acceptance criteria from requirements.md systematically
- **Design Pattern Compliance**: Architecture patterns from design.md followed appropriately throughout implementation
- **Code Quality Standards**: Steering document conventions and patterns applied consistently
- **Task Scope Discipline**: Implementation focused on approved task without scope creep or speculative additions

**Overall Implementation Quality Score**: [Calculated score based on comprehensive validation results with transparent methodology]

# Task Completion Review and Progress Update

## Task Implementation Completion Presentation

**Present completed task implementation with comprehensive assessment:**

**Implemented Task Summary:**

- **Task**: [Task number and description that was implemented]
- **Implementation Summary**: [What was specifically implemented, files modified, functionality added with context integration]
- **Quality Assessment**: [Comprehensive scoring across all validation dimensions with methodology]
- **Context Integration**: [How requirements, design, and steering guidance influenced implementation decisions]

**Implementation Details:**

- **Code Changes**: [Specific files created/modified and functionality implemented with technical details]
- **Requirements Satisfied**: [Specific acceptance criteria from requirements.md that were addressed through implementation]
- **Design Compliance**: [Architecture patterns and specifications from design.md that were followed]
- **Testing Implemented**: [Test coverage and validation aligned with approved testing strategy]
- **Integration Validation**: [How implementation connects with existing codebase and system architecture]

## User Review Facilitation Process

**Guide user through systematic task implementation review:**

**Key Review Considerations:**

- Does the implementation satisfy the task objectives and requirements completely and accurately?
- Is the code quality appropriate for the project standards and maintainability requirements?
- Are the architecture patterns from design.md properly followed throughout implementation?
- Does the implementation integrate properly with existing code and system architecture?
- Are the testing requirements adequately addressed with appropriate coverage?
- Is the scope appropriate (focused on task without unnecessary additions or over-engineering)?

**User Review Options:**

- **Implementation Issues**: Tell me what needs to be adjusted or refined within the established task scope
- **Quality Concerns**: Point out code quality, standards compliance, or maintainability issues that need addressing
- **Integration Problems**: Identify integration issues or compatibility concerns with existing codebase
- **Scope Clarifications**: Adjust understanding of task boundaries if implementation scope needs refinement
- **Task Complete**: If satisfied with implementation quality and completeness, say "looks good", "task complete", or "approved"

**What's your feedback on this task implementation?**

**Handle user feedback and refinement cycle if needed**

## Implementation Refinement Process (if changes requested)

**If user requests changes, execute systematic refinement:**

**Before implementing modifications, carefully analyze specific feedback:**

1. What specific implementation changes are being requested and why?
2. How do requested modifications align with approved task scope and context documents?
3. What changes maintain Kiro compliance while addressing user implementation needs?
4. How will modifications affect integration with existing code and system architecture?

**Refinement Execution Process:**

1. **Analyze specific feedback** systematically to understand precise implementation modifications needed within task scope
2. **Refine implementation** with requested changes while maintaining complete Kiro compliance and task boundaries
3. **Re-execute quality validation** to ensure all standards maintained including scope discipline and context integration
4. **Present updated implementation** for another review cycle with improvement highlights and technical details
5. **Continue refinement cycles until explicit user approval** of task completion received with documented satisfaction

# Final State Management and Next Steps

## Task Completion and Progress Management

**Upon receiving explicit user approval:**

**Update project progress systematically:**

- Mark task as completed in tasks.md by updating checkbox from `- [ ]` to `- [x]` for completed task
- Update spec.yaml timestamp to reflect implementation progress and maintain project state accuracy
- Validate task completion against all context documents ensuring implementation meets all requirements
- Document task completion for workflow traceability and progress tracking

**Progress Update Execution:**

```yaml
# Update .kiro/specs/[feature-name]/spec.yaml
updated_at: "[current ISO timestamp]"
```

**Task Completion Validation:**

- Task implementation completed successfully with user approval and quality validation
- Progress tracking updated accurately in tasks.md with checkbox status change
- Implementation validated against all context documents including requirements, design, and steering guidance
- Task scope boundaries maintained throughout execution with reasoning-based discipline

## Next Steps Analysis and Workflow Continuation

**Provide intelligent guidance for continued workflow progression:**

**Analyzing remaining tasks for next recommendations...**

**Think step by step about optimal workflow continuation:**

1. What tasks remain incomplete based on current tasks.md status?
2. What are the dependency relationships for available tasks?
3. What is the logical next task based on completion status and dependencies?
4. Are there any parallel tracks available for efficient workflow progression?

**Parse remaining tasks systematically from tasks.md:**

- Identify all incomplete tasks (- [ ]) with their dependencies and prerequisites
- Analyze task dependencies to determine which tasks are now available for execution
- Consider sub-task relationships and sequencing for optimal workflow progression
- Evaluate parallel execution opportunities while maintaining single-task focus principle

**Next Available Tasks Analysis:**

- **Task [X]**: [Description] - Ready for execution (all dependencies met)
- **Task [Y]**: [Description] - Blocked by [dependency] (complete [prerequisite] first)
- **Task [Z]**: [Description] - Ready for execution (parallel track available)

**Recommended Next Task:** [Task number and description with clear reasoning]
**Rationale**: [Why this task is the logical next step based on dependencies, workflow efficiency, and project progression]

**Workflow Continuation Options:**

### Continue with Next Task

To continue with recommended next task, run:

```
/kiro:5-task-execution [feature-name]
```

Then specify: "[recommended task number or description]"

### Alternative Task Selection

Choose any available task by specifying task number or requesting different recommendation based on preferences or priorities.

### Project Status Review

Use status command to review complete project progress:

```
/kiro:6-status [feature-name]
```

Review overall workflow health, completion percentage, and strategic next steps.

### Workflow Pause

Take break to review current progress, plan next development session, or address other project priorities before continuing implementation.

**Task Execution Complete Summary:**

- **Completed Task**: [Task number and description that was successfully implemented]
- **Implementation Quality**: All Kiro Stage 4 standards met with comprehensive context integration
- **Progress Tracking**: tasks.md updated with completion status and project timestamp refreshed
- **Context Validation**: Requirements, design, and steering guidance successfully applied throughout implementation
- **Workflow Progression**: Ready for next task execution with clear recommendations and optimal sequencing

**Kiro Stage 4 Task Execution Complete - Single Task Implementation Successful with Comprehensive Context Integration and Progress Tracking!**
