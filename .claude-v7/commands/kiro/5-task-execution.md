---
description: "Kiro Stage 4: Execute single tasks with context validation and progress tracking"
argument-hint: "feature-name (kebab-case)"
---

# Kiro Task Execution (Stage 4)

## 1. Argument Validation & Feature Selection

Let me check for available features and validate your input.

!ls .kiro/specs/ 2>/dev/null | grep -v "^total" | grep -E "^[a-zA-Z0-9-]+$" || echo "No features found in .kiro/specs/"

**Checking feature argument...**

If you didn't provide a feature name or the feature doesn't exist:

### Available Features in .kiro/specs/

[The list above shows your available features]

**Please specify which feature you'd like to work on for task execution:**

- Type the feature name exactly as shown (kebab-case format)
- Feature must have approved requirements from Stage 1
- Feature must have approved design from Stage 2
- Feature must have approved tasks from Stage 3
- All context documents (requirements.md, design.md, tasks.md) must exist

**Waiting for your feature selection...**

[Wait for user to provide valid feature name before continuing]

---

Once you provide a valid feature name, I'll continue with that feature.

## 2. State & Context Validation + Prerequisites Check

Loading project context for feature: **${feature-name}**

@.kiro/specs/${feature-name}/spec.yaml
@.kiro/specs/${feature-name}/requirements.md
@.kiro/specs/${feature-name}/design.md
@.kiro/specs/${feature-name}/tasks.md
@.kiro/steering/product.md
@.kiro/steering/tech.md  
@.kiro/steering/structure.md

**Validating prerequisites:**

!test -f ".kiro/specs/${feature-name}/spec.yaml" && echo "Found" || echo "Missing"
!test -f ".kiro/specs/${feature-name}/requirements.md" && echo "Found" || echo "Missing"
!test -f ".kiro/specs/${feature-name}/design.md" && echo "Found" || echo "Missing"
!test -f ".kiro/specs/${feature-name}/tasks.md" && echo "Found" || echo "Missing"

**Critical Stage 4 Prerequisites:**

- Feature initialized: ${feature-name}
- Requirements stage: **MUST be approved** (Stage 1 complete)
- Design stage: **MUST be approved** (Stage 2 complete)
- Implementation planning: **MUST be approved** (Stage 3 complete)
- ALL context documents must exist and be accessible for implementation guidance

**Prerequisites Status:**

- Feature: ${feature-name} ✓
- Stage 1 (Requirements): [Checking approval status from spec.yaml]
- Stage 2 (Design): [Checking approval status from spec.yaml]
- Stage 3 (Implementation Plan): [Checking approval status from spec.yaml]
- Context Documents: [Verifying accessibility of all required documents]

If previous stages are not approved, you must complete them first:

```
/kiro:2-requirements-clarification ${feature-name}  # if requirements not approved
/kiro:3-design-document-creation ${feature-name}    # if design not approved  
/kiro:4-implementation-planning ${feature-name}     # if tasks not approved
```

**Context documents are required for accurate implementation. Cannot proceed without complete context.**

**Ready to proceed with task execution.**

## 3. Task Selection & Validation Process

**Feature Context Loaded:** ${feature-name}  
**Current Status:** [Reading from spec.yaml, requirements.md, design.md, and tasks.md for implementation context]

**Task Selection Phase (Kiro Stage 4)**

Based on your approved implementation plan, I need to understand which task you'd like me to execute.

**Analyzing tasks.md for available tasks:**
[Parse tasks.md to extract task list with completion status]

**Current Task Status:**

- [Task 1]: ✅ Completed / ⏳ Available / 🔒 Blocked (dependencies not met)
- [Task 2]: ✅ Completed / ⏳ Available / 🔒 Blocked
- [Task 3]: ✅ Completed / ⏳ Available / 🔒 Blocked
- [Sub-task 1.1]: ✅ Completed / ⏳ Available / 🔒 Blocked
- [Sub-task 1.2]: ✅ Completed / ⏳ Available / 🔒 Blocked

**Task Selection Options:**

**Option 1: Specify Exact Task**

- Tell me the task number (e.g., "task 3", "task 1.2")
- Reference task by description (e.g., "implement user authentication")

**Option 2: Get Recommendation**  

- Say "recommend next task" and I'll suggest the logical next available task
- I'll analyze dependencies and completion status to recommend properly

**Option 3: Ask Questions**

- Ask about task details, dependencies, or implementation approach
- I'll provide information without starting execution

**Task Selection Guidelines:**

- **Sub-task Priority**: If a task has sub-tasks, I'll start with sub-tasks first (1.1 before 1.2)
- **Dependency Validation**: I'll check that prerequisite tasks are completed
- **Single Task Focus**: I'll execute only the specified task, nothing else
- **Scope Boundaries**: Implementation will stay within the approved task description

**What would you like to do:**

- Specify a task to execute
- Ask for next task recommendation  
- Ask questions about tasks or implementation approach

**Your choice?**

[Wait for user task selection or guidance request]

---

## Task Analysis & Validation

**Selected Task Analysis:**

[If user specifies task:]
**Selected Task**: [Task number and description from tasks.md]
**Task Details**: [Full task information including requirements mapping and implementation specifics]

**Dependency Validation**:

- **Prerequisites**: [List prerequisite tasks and their completion status]
- **Dependencies Status**: [All dependencies met ✅ / Missing dependencies ❌]

**Sub-task Analysis**:
[If task has sub-tasks:]

- **Sub-task Priority**: Starting with [sub-task number] as it's the first incomplete sub-task
- **Sub-task Details**: [Specific sub-task description and requirements]

[If dependencies not met:]
**⚠️ Dependency Issue**: This task requires completion of [prerequisite tasks] first.
**Recommended Action**: Complete [specific prerequisite task] before proceeding with this task.
**Would you like me to recommend the prerequisite task instead?**

**Task Scope Confirmation**:

**This task will implement:**

- [Specific functionality from task description]  
- [Code components to be created/modified]
- [Testing requirements from task details]
- [Integration points with existing code]

**This task will NOT implement:**

- [Related functionality that's in other tasks]
- [Features beyond the approved task scope]  
- [Speculative additions not in task description]

**Implementation will be guided by:**

- **Requirements context**: [Specific requirements this task addresses]
- **Design guidance**: [Architecture patterns and components from design.md]
- **Steering standards**: [Code quality patterns from steering documents]
- **Task boundaries**: [Exact scope from approved tasks.md]

**Ready to execute this task with these boundaries? Say 'proceed' or 'execute task'**

[Wait for user confirmation before implementation]

## 4. Single Task Execution Process (Kiro Stage 4)

**Executing single task with full context integration...**

Now I'll implement the selected task using ALL available context:

- **Task specification**: [Exact requirements from tasks.md]
- **Requirements context**: [Relevant acceptance criteria from requirements.md]
- **Design guidance**: [Architecture patterns and component specifications from design.md]  
- **Steering standards**: [Code quality patterns, naming conventions, and project standards]
- **Implementation boundaries**: [Approved scope from task description]

**CRITICAL KIRO STAGE 4 CONSTRAINTS:**

- Execute ONLY the selected task - no parallel task implementation
- Stay within approved task scope boundaries with reasoning-based discipline
- Apply all context documents to guide implementation decisions
- Maintain code quality standards from steering documents
- Stop after task completion for user review - no automatic progression

**Implementation Process:**

### Context-Driven Implementation

**Applying Requirements Context:**
[Reference specific acceptance criteria that this task addresses]

- **Acceptance Criteria**: [Specific criteria from requirements.md that guide implementation]
- **Success Validation**: [How implementation will be validated against requirements]

**Applying Design Guidance:**  
[Reference relevant architecture and component specifications]

- **Architecture Pattern**: [Design patterns from design.md that inform implementation]
- **Component Integration**: [How this task integrates with designed system architecture]
- **Interface Requirements**: [API/interface specifications from design]

**Applying Steering Standards:**
[Reference code quality and project standards]  

- **Code Quality Standards**: [Relevant patterns from steering documents]
- **Project Conventions**: [Naming, organization, and style requirements]
- **Integration Patterns**: [How code should connect with existing system]

### Single Task Implementation

**Implementing:** [Task description and specific objectives]

**Task Scope Boundaries (Reasoning-Based)**

**Implementation will focus on:**

- [Specific functionality defined in task description]
- [Code components explicitly mentioned in task details]
- [Testing requirements specified for this task]

**Implementation will not include:**

- [Related functionality assigned to other tasks] - These have their own approved tasks for focused implementation
- [Speculative additions beyond task scope] - Task boundaries were established through careful planning in Stage 3
- [Complex abstractions not required] - Implementation should match task complexity, avoiding over-engineering

**Why These Boundaries Matter:**

- **Resource Focus**: Concentrating on approved task scope allows deep focus on implementation quality rather than spreading across multiple concerns
- **Progress Tracking**: Clear task completion enables accurate progress measurement and user visibility
- **System Coherence**: Honoring task boundaries maintains the careful planning from implementation stage
- **Quality Assurance**: Single task focus enables thorough testing and validation within manageable scope

### Implementation Execution

[Execute actual implementation based on all context and constraints]

**Code Implementation:**
[Actual code writing, modification, or testing activities based on task requirements]

**Quality Validation During Implementation:**

- **Requirements Compliance**: [Verify implementation satisfies relevant acceptance criteria]
- **Design Compliance**: [Ensure implementation follows architecture patterns]
- **Code Quality**: [Apply steering document standards for quality]
- **Integration Validation**: [Test connections with existing code]

**Implementation Progress:**
[Document specific code changes, files modified, functionality implemented]

## 5. Quality Validation Framework

**Executing Kiro Stage 4 quality validation checkpoints...**

### Implementation Quality Validation

- Check: Implementation addresses specific task objectives from tasks.md
- Check: Code quality meets steering document standards and conventions
- Check: Implementation follows architecture patterns from design.md
- Check: Functionality satisfies relevant requirements from requirements.md
- Check: Integration with existing code works properly
- Check: Task scope boundaries respected throughout implementation

### Requirements Compliance Validation

- Check: Implementation validates against specific acceptance criteria from requirements.md
- Check: Functional requirements addressed by this task are properly implemented
- Check: Non-functional requirements (performance, security, etc.) considered appropriately
- Check: Error handling requirements from requirements addressed in implementation
- Check: User experience requirements reflected in implementation decisions

### Design Pattern Compliance

- Check: Implementation follows approved architecture patterns from design.md
- Check: Component interfaces implemented according to design specifications  
- Check: Data models and structures match design.md specifications
- Check: Integration points connect properly according to design architecture
- Check: Error handling patterns from design implemented appropriately

### Testing Scope Validation (Context-Based)

- Check: Testing approach follows approved design.md testing strategy
- Check: Test coverage validates specific requirements acceptance criteria relevant to this task
- Check: No speculative testing beyond approved scope boundaries from previous stages
- Check: Testing complexity matches approved design patterns (not over-engineered)
- Check: Task-specific testing requirements from tasks.md addressed appropriately

### Code Quality Standards Compliance

- Check: Code follows naming conventions and style patterns from steering documents
- Check: Code organization matches project structure standards from structure.md
- Check: Technology usage aligns with tech.md guidelines and constraints
- Check: Integration patterns follow established project conventions
- Check: Code maintainability appropriate for project standards and team capabilities

### Task Scope Discipline Validation

- Check: Implementation limited to approved task description from tasks.md
- Check: No functionality from other tasks included in implementation (maintains task isolation)
- Check: Implementation complexity appropriate for task requirements (not over-engineered)  
- Check: Task boundaries from implementation planning stage respected throughout
- Check: Related functionality properly deferred to appropriate tasks in sequence

**Quality Validation Results:**

**Kiro Stage 4 Quality Assessment:**

- **Implementation Quality**: Code meets steering standards and task objectives
- **Requirements Compliance**: Implementation satisfies relevant acceptance criteria from requirements.md  
- **Design Pattern Compliance**: Architecture patterns from design.md properly followed
- **Testing Integration**: Testing aligned with approved strategy and scope boundaries
- **Code Quality Standards**: Steering document conventions and patterns applied consistently
- **Task Scope Discipline**: Implementation focused on approved task without scope creep

**Overall Implementation Quality Score: [Calculated based on validation results]**

## 6. Task Completion Review & Progress Update

## Task Implementation Complete

I've completed the selected task following all Kiro Stage 4 standards:

- **Single Task Focus**: Implementation limited to approved task scope with reasoning-based boundaries
- **Context Integration**: All requirements, design, and steering guidance applied to implementation decisions
- **Quality Standards**: Code meets steering document standards and validates against requirements
- **Task Isolation**: No implementation of functionality from other tasks, maintaining workflow discipline
- **Architecture Compliance**: Implementation follows approved design patterns and component specifications

**Implemented Task:**
**Task**: [Task number and description]
**Implementation Summary**: [What was specifically implemented, files modified, functionality added]
**Quality Score**: [Score] (meeting all Kiro validation standards and context compliance)

[Display key implementation highlights and completion evidence]

**Implementation Details:**

- **Code Changes**: [Specific files created/modified and functionality implemented]
- **Requirements Satisfied**: [Specific acceptance criteria from requirements.md that were addressed]
- **Design Compliance**: [Architecture patterns and specifications from design.md that were followed]
- **Testing Implemented**: [Test coverage and validation aligned with approved testing strategy]

**Please review the task implementation.**

**Consider:**

- Does the implementation satisfy the task objectives and requirements?
- Is the code quality appropriate for the project standards?
- Are the architecture patterns from design.md properly followed?
- Does the implementation integrate properly with existing code?
- Are the testing requirements adequately addressed?
- Is the scope appropriate (focused on task without unnecessary additions)?

**Your options:**

- **Implementation Issues**: Tell me what needs to be adjusted or refined within the task scope
- **Quality Concerns**: Point out code quality or standards compliance issues  
- **Scope Clarifications**: Adjust understanding of task boundaries if needed
- **Task Complete**: If satisfied, say "looks good", "task complete", or "approved"

**What's your feedback on this task implementation?**

[Handle user feedback and refinement cycle if needed]

---

### Implementation Refinement (if changes requested)

[If user requests changes:]

1. **Analyze specific feedback** and identify implementation adjustments needed within task scope
2. **Refine implementation** with requested changes while maintaining Kiro compliance and task boundaries
3. **Re-run quality validation** to ensure all standards maintained including scope discipline
4. **Present updated implementation** for another review cycle with improvement highlights
5. **Continue until user approval** of task completion received

## 7. Final State Management & Next Steps

### Task Execution Complete

Thank you for the review! The task implementation is now complete and ready for progress tracking.

**Updating task progress...**

[Update tasks.md checkbox from `- [ ]` to `- [x]` for completed task]

```yaml
# Updating .kiro/specs/${feature-name}/spec.yaml
updated_at: "[current timestamp]"
```

**Progress Updated Successfully:**

- Task marked as completed in tasks.md with checkbox update
- Project timestamp updated to reflect recent progress
- Implementation validated against all context documents
- Task scope boundaries maintained throughout execution

**Task Completion Summary:**

- **Completed Task**: [Task number and description]
- **Implementation Quality**: All Kiro Stage 4 standards met with context integration
- **Progress Tracking**: tasks.md updated with completion status
- **Context Validation**: Requirements, design, and steering guidance successfully applied

### Next Steps Analysis

**Analyzing remaining tasks for next recommendations...**

[Analyze tasks.md for next available task based on dependencies and completion status]

**Next Available Tasks:**

- **Task [X]**: [Description] - Ready for execution (all dependencies met)
- **Task [Y]**: [Description] - Blocked by [dependency] (complete [prerequisite] first)
- **Task [Z]**: [Description] - Ready for execution (parallel track available)

**Recommended Next Task:** [Task number and description]
**Rationale**: [Why this task is the logical next step based on dependencies and workflow]

**To continue with next task, run:**

```
/kiro:5-task-execution ${feature-name}
```

Then specify: "[recommended task number or description]"

**Alternative Options:**

- **Status Check**: `/kiro:6-status ${feature-name}` - Review complete project progress
- **Different Task**: Choose any available task for execution
- **Take Break**: Review current progress and plan next development session

**Kiro Stage 4 Task Execution Complete - Implementation Successful!**
