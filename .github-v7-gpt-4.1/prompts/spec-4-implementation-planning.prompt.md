---
description: "Execute Kiro Stage 3 implementation planning with comprehensive task breakdown and scope discipline"
mode: agent
---

# Kiro Implementation Planning Workflow

## Methodology Reinforcement

You are executing Kiro Stage 3: systematic implementation planning with the following approach:

- **Design-to-Code Transformation**: Convert approved design components into discrete, actionable coding tasks exclusively
- **Complete Traceability**: Maintain mapping from requirements through design to implementation tasks without gaps
- **Cross-Stage Scope Discipline**: Inherit and preserve scope boundaries from BOTH requirements and design approval stages
- **Coding Task Exclusivity**: Focus exclusively on code writing, modification, and testing activities avoiding operational tasks
- **2-Level Maximum Hierarchy**: Use numbered checkbox format (1., 1.1, 1.2) for clear tracking and management
- **Incremental Development**: Sequence tasks for progressive implementation with logical dependency management
- **Quality Validation**: Transparent assessment frameworks ensuring comprehensive coverage and implementation excellence

## Systematic Task Analysis Framework

First, systematically analyze all approved design components to identify implementable elements requiring coding tasks.

Then, evaluate each component against requirements traceability to ensure complete coverage and proper scope boundaries.

Next, sequence tasks for incremental development ensuring each task builds logically on previous implementations.

Finally, validate the complete task breakdown against all quality criteria including scope discipline and coding task exclusivity.

# Context Loading and Prerequisites Validation

## Step 1: Feature Selection and Prerequisites Validation

**Before proceeding, think step by step about:**

1. What features are available and does the specified feature exist with proper initialization?
2. What are the critical Stage 3 prerequisites that must be validated?
3. What context documents should be loaded for comprehensive implementation planning?

**Execution Process:**

- Check for available features in .kiro/specs/ directory using appropriate tools
- If feature argument missing, display available features and wait for user selection
- If feature doesn't exist, provide guidance on using feature initialization first
- Validate feature has proper spec.yaml structure with approved requirements and design before proceeding

**Critical Stage 3 Prerequisites Assessment:**

- Feature must be properly initialized with valid spec.yaml structure
- Requirements stage MUST be approved (Stage 1 complete) - check requirements.approved in spec.yaml
- Design stage MUST be approved (Stage 2 complete) - check design.approved in spec.yaml
- Both requirements.md and design.md must exist and be accessible for implementation context
- All steering documents should be accessible for implementation guidance integration

## Step 2: Comprehensive Context Document Loading

**Systematic Context Loading Strategy:**

**Think through what context documents are available and needed:**

- Feature specification: .kiro/specs/[feature-name]/spec.yaml (required)
- Approved requirements: .kiro/specs/[feature-name]/requirements.md (required for Stage 3)
- Approved design: .kiro/specs/[feature-name]/design.md (required for Stage 3)
- Existing tasks: .kiro/specs/[feature-name]/tasks.md (if exists - for draft handling)
- Product steering: .kiro/steering/product.md (if exists)
- Technical steering: .kiro/steering/tech.md (if exists)
- Structure steering: .kiro/steering/structure.md (if exists)

**Load all available context documents systematically:**

- Read complete content of each available document for comprehensive understanding
- Validate document accessibility and completeness for implementation planning
- Note any missing context that might affect task breakdown quality and implementation sequencing
- Special handling: If existing tasks.md found, prepare for smart workflow routing with draft state analysis

## Step 3: Draft State Detection and Intelligent Workflow Routing

**After systematically analyzing all loaded project context, determine the most efficient workflow path:**

**State Analysis Framework:**

- **File Status**: .kiro/specs/[feature-name]/tasks.md [EXISTS/MISSING based on file loading]
- **Generation Status**: tasks.generated [true/false from spec.yaml]
- **Approval Status**: tasks.approved [true/false from spec.yaml]
- **Prerequisites**: Both requirements.approved AND design.approved [MUST be true to proceed]
- **State Consistency**: Validate spec.yaml flags match physical file existence

**Intelligent Workflow Routing Decision:**

**If tasks.generated: false OR tasks.md doesn't exist:**

- **Fresh Generation Path**: No existing implementation plan found or inconsistent state
- **Proceeding**: Implementation Scope Planning → Task Breakdown → Review
- Continue to Implementation Scope Planning Phase

**If tasks.generated: true AND tasks.approved: true:**

- **Implementation Complete**: Task breakdown approved and ready for execution
- **Status**: Ready for Stage 4 progression
- **Next Step**: Use task execution command to proceed to Stage 4

**If tasks.generated: true AND tasks.approved: false AND tasks.md exists:**

- **Existing Draft Path**: Found existing implementation plan ready for review and revision
- **Efficiency Optimization**: Skip scope planning phase since scope was already established
- **Proceeding**: Direct to Task Review & Revision Cycle
- Jump to Review and Iteration Process section

**If tasks.generated: true AND tasks.md doesn't exist:**

- **State Corruption Detected**: spec.yaml indicates generated but file missing
- **Recovery Options**:
  - **Regenerate**: Create fresh task breakdown (reset to fresh generation path)
  - **Reset State**: Mark tasks.generated: false and proceed normally
- **User Choice Required**: Ask user preference for recovery approach

# Implementation Scope Planning Process

## Phase 1: Design Component Analysis

**Before proceeding with scope planning, systematically analyze approved design to understand implementation requirements:**

**Design Analysis Framework:**

1. What major components are defined in the approved design document?
2. What interfaces and integration points require coding implementation?
3. What data models and database schemas need implementation tasks?
4. What error handling and testing strategies require coding tasks?

**Component Extraction Process:**

- Identify all implementable components from design.md systematically
- Extract interface specifications that require coding implementation
- Document data model implementations needed for functional requirements
- Note integration points requiring API or external system connection code

## Phase 2: Implementation Scope Boundaries Analysis

**Systematic Scope Planning with Cross-Stage Boundary Inheritance:**

**Cross-Stage Scope Boundaries (Reasoning-Based)**

### Requirements Scope Reference (Stage 1 Inheritance)

**From requirements.md out-of-scope section:**
[Carry forward exact items with original reasoning from requirements approval]

- [Feature X] - Excluded from requirements because: [original reasoning from requirements approval]
- [Feature Y] - Not in requirements scope because: [original reasoning from requirements approval]

**Implementation guidance**: These exclusions represent conscious decisions made during requirements approval. Honoring them maintains project coherence and user agreement.

### Design Scope Reference (Stage 2 Inheritance)

**From design.md out-of-scope section:**
[Carry forward exact items with original reasoning from design approval]

- [Component X] - Not designed because: [original reasoning from design approval]
- [Pattern Y] - Not designed because: [original reasoning from design approval]

**Implementation guidance**: These architectural boundaries were established based on requirements analysis and research. Respecting them maintains system coherence and technical integrity.

### Implementation Activity Boundaries (Stage 3 Specific)

**Coding tasks only**: This stage focuses exclusively on code implementation because different activity types have different skill requirements, timing considerations, and success criteria.

**INCLUDED (Coding Tasks Only):**

- Code writing: Creating new functions, classes, modules for approved components
- Code modification: Updating existing code to implement design specifications
- Test creation: Writing unit, integration tests for implemented code
- Configuration updates: Modifying config files for code behavior
- Database schema: Creating/modifying data structure code
- API implementation: Creating/updating interface code for approved design

**NOT INCLUDED (Different Stages/Skills):**

- User acceptance testing: Human validation activities (different skillset/timing)
- Deployment activities: Infrastructure operations (different tools/permissions)
- Performance metrics gathering: Runtime analysis activities (different stage)
- End-to-end manual testing: Application flow validation (different process)

## Phase 3: Implementation Planning Questions and User Input

**Implementation Planning Context Gathering:**

**Analyzing design.md for implementable components:**
[Extract and present components, interfaces, data models from design analysis]

**Implementation Scope Confirmation:**
**Will implement**: Coding tasks for components approved in design.md to satisfy requirements approved in requirements.md.

**Will not implement**:

- Features excluded during requirements approval (maintains user agreement)
- Components excluded during design approval (maintains architecture coherence)
- Non-coding activities better suited for different stages/roles

**Implementation Planning Questions for User:**

- Any coding priorities from the design components you'd like me to consider?
- Testing approach preferences for the implementation sequence?
- Any technical constraints I should consider for task sequencing?
- Development environment considerations that affect task breakdown?

**Ready to proceed with focused implementation planning? Say 'proceed' to continue with task breakdown generation.**

# Task Breakdown Generation Process

## Pre-Generation Implementation Analysis

**Before generating task breakdown, systematically plan comprehensive approach:**

**Think step by step about:**

1. How will I transform each design component into specific, actionable coding tasks?
2. What task sequencing will enable incremental development with logical dependencies?
3. How will I maintain complete traceability from requirements through design to tasks?
4. What quality standards must be met for each task to ensure implementation excellence?

**Generation Strategy:**

- Apply exact Kiro task breakdown template with 2-level maximum hierarchy
- Transform design components systematically into discrete coding tasks
- Maintain complete requirements traceability for every task
- Sequence tasks for incremental development with dependency management
- Ensure coding task exclusivity avoiding operational or business process activities

## Comprehensive Task Breakdown Generation

**Create tasks.md at .kiro/specs/[feature-name]/tasks.md using the following template specification:**

<kiro_implementation_tasks_template>

```markdown
# [feature-name] Implementation Tasks

## Task List

- [ ] 1. [SPECIFICATION: Task description must reference specific design component from design.md with clear traceability]

  - [SPECIFICATION: Implementation details must specify exact code to write/modify with technical specificity]
  - [SPECIFICATION: Requirements mapping must reference specific requirements from requirements.md for traceability]
  - [SPECIFICATION: Files/components must list actual filenames and paths where possible for implementation clarity]
  - [SPECIFICATION: Integration points must describe specific interfaces and connections from design]

- [ ] 1.1 [SPECIFICATION: Sub-task for incremental development of Task 1 with logical progression]

  - [SPECIFICATION: Specific coding activity within Task 1 scope with measurable completion criteria]
  - [SPECIFICATION: Dependencies on Task 1 completion and outputs from previous work]
  - [SPECIFICATION: Testing requirements for this sub-component with validation approach]

- [ ] 1.2 [SPECIFICATION: Another sub-task building on Task 1.1 with incremental complexity]

  - [SPECIFICATION: Next incremental coding activity with clear implementation requirements]
  - [SPECIFICATION: Validation criteria for completion with specific acceptance criteria]

- [ ] 2. [SPECIFICATION: Task Description for next design component, building on Task 1 outputs]

  - [SPECIFICATION: Implementation specifics for this component with technical details]
  - [SPECIFICATION: Requirements traceability to specific approved requirements with mapping]
  - [SPECIFICATION: Dependencies on previous task outputs with integration requirements]
  - [SPECIFICATION: Integration requirements with Task 1 outputs and overall system architecture]

- [ ] 2.1 [SPECIFICATION: Sub-task for Task 2 incremental development with logical sequencing]

  - [SPECIFICATION: Specific coding activity details with implementation requirements]
  - [SPECIFICATION: Testing integration with previous tasks and overall system validation]

- [ ] 3. [SPECIFICATION: Task Description for integration/testing of implemented components]
  - [SPECIFICATION: Integration coding requirements for component connections]
  - [SPECIFICATION: Test implementation for component interactions and system validation]
  - [SPECIFICATION: Validation against requirements acceptance criteria with traceability]

## Implementation Scope Boundaries (Reasoning-Based)

### Requirements Scope Reference

**From requirements.md out-of-scope section:**
[Carry forward exact items with original reasoning]

- [Feature X] - Excluded because: [original reasoning from requirements approval]
- [Feature Y] - Excluded because: [original reasoning from requirements approval]

**Implementation guidance**: These exclusions represent conscious decisions made during requirements approval. Honoring them maintains project coherence and user agreement.

### Design Scope Reference

**From design.md out-of-scope section:**
[Carry forward exact items with original reasoning]

- [Component X] - Not designed because: [original reasoning from design approval]
- [Pattern Y] - Not designed because: [original reasoning from design approval]

**Implementation guidance**: These architectural boundaries were established based on requirements analysis and research. Respecting them maintains system coherence and technical integrity.

### Implementation Activity Boundaries

**Coding tasks only**: This stage focuses exclusively on code implementation because:

- Testing activities have different skill requirements and timing considerations
- Deployment activities require different tools, permissions, and operational knowledge
- User validation requires different processes involving actual users and stakeholders
- Each activity type has different success criteria and validation methods

**Focus benefit**: Concentrating on coding activities allows deep focus on implementation quality and technical excellence.

### Why These Boundaries Matter

**Resource Focus**: Implementing only approved components allows concentrated effort on quality and depth rather than spreading across unapproved features.

**Maintenance Sustainability**: Each additional feature creates permanent maintenance overhead - bug fixes, updates, testing, documentation that compounds over time.

**System Coherence**: Approved requirements and design create a coherent vision. Implementation should honor this careful planning rather than fragment it.

**Technical Debt Prevention**: Unplanned features typically lack proper architecture consideration, creating long-term maintenance challenges.

### Future Implementation Considerations

- [Enhancement 1] - Could be added after formal requirements/design updates if business value emerges
- [Capability 2] - Monitor usage patterns to evaluate need, implement only after proper planning
- [Integration 3] - Evaluate business case and technical fit before adding to future development cycles

**Implementation Philosophy**: Execute what was carefully planned and approved. Everything else awaits proper requirements analysis and design consideration.
```

</kiro_implementation_tasks_template>

## Post-Generation Quality Assessment

**After generating the complete task breakdown, systematically reflect on quality and completeness:**

**Task Breakdown Quality Assessment Framework:**

1. Do all tasks trace directly to approved design components without speculative additions?
2. Is coding task exclusivity maintained throughout with no operational activities?
3. Are all tasks sequenced for incremental development with logical dependencies?
4. Is complete requirements traceability maintained for every implementation task?
5. Is the 2-level maximum hierarchy maintained with clear, trackable structure?

# Quality Validation Framework

## Comprehensive Implementation Planning Quality Assessment

**Execute systematic quality validation across all critical task breakdown dimensions:**

### Task Format Validation

- Verify .kiro/specs/[feature-name]/tasks.md created successfully with proper file structure
- Check numbered checkbox format used consistently ("- [ ] 1.", "- [ ] 1.1")
- Confirm maximum 2-level hierarchy maintained throughout (no deeper nesting)
- Validate decimal notation used for sub-tasks (1.1, 1.2, 2.1, etc.) consistently
- Ensure simple structure without complex hierarchies for clarity and tracking
- Check all tasks have clear completion criteria with measurable outcomes

### Coding Task Exclusivity Validation

- Verify all tasks involve code writing, modification, or testing activities exclusively
- Check no user acceptance testing tasks included (different skillset/timing requirements)
- Confirm no deployment activity tasks included (different tools/permissions requirements)
- Validate no performance metrics gathering tasks included (different stage/process)
- Ensure no end-to-end manual testing tasks included (different validation process)
- Check no operational or business process tasks included maintaining technical focus

### Design Component Coverage Validation

- Verify all major design components from design.md addressed by implementation tasks
- Check all design interfaces have corresponding coding task implementation
- Confirm data model implementation tasks cover all schemas from design completely
- Validate integration points from design addressed in coding tasks appropriately
- Ensure error handling patterns from design addressed in implementation tasks
- Check testing strategy from design reflected in test implementation tasks

### Requirements Traceability Validation

- Verify tasks reference specific requirements from requirements.md (not just general categories)
- Check granular requirement mapping to individual tasks (not just user stories)
- Confirm all approved requirements have corresponding implementation tasks without gaps
- Validate no requirements left without implementation coverage
- Ensure task completion criteria enable validation against requirements acceptance criteria
- Check traceability matrix completeness from requirements through design to tasks

### Incremental Development Validation

- Verify tasks ordered by implementation dependencies (each builds on previous)
- Check each task produces outputs usable by subsequent tasks in sequence
- Confirm no orphaned or disconnected tasks identified in breakdown
- Validate early validation and testing opportunities integrated throughout sequence
- Ensure core functionality implementable and testable in early tasks
- Check complexity increases gradually across task sequence without overwhelming jumps

### Implementation Scope Discipline Validation

- Verify all tasks trace to approved design components (no speculative additions)
- Check no tasks implement features from requirements out-of-scope section
- Confirm no tasks implement elements from design out-of-scope section
- Validate task descriptions reference specific approved requirements and design elements
- Ensure scope boundaries carried forward with original reasoning intact
- Check implementation boundaries clearly documented with sound reasoning

**Present comprehensive quality validation results with transparent scoring methodology and specific improvement recommendations if needed.**

# Review and Iteration Process

## Task Breakdown Draft Presentation

**Present completed task breakdown with comprehensive quality assessment:**

**Generated Document Summary:**

- **Location**: .kiro/specs/[feature-name]/tasks.md
- **Quality Assessment**: [Comprehensive scoring across all validation dimensions with transparent methodology]
- **Key Highlights**: [Major task categories, implementation sequence, and scope boundaries with reasoning]
- **Design Coverage**: [Analysis showing how all design components addressed in task breakdown]
- **Requirements Traceability**: [Coverage analysis showing complete mapping from requirements through tasks]

**Quality Validation Results:**

- **Task Format Compliance**: Perfect numbered checkbox structure with appropriate 2-level hierarchy
- **Coding Task Exclusivity**: All tasks focused on code implementation activities exclusively
- **Design Component Coverage**: All approved design elements addressed in systematic task breakdown
- **Requirements Traceability**: All tasks mapped to specific approved requirements with complete coverage
- **Incremental Development**: Tasks sequenced for progressive implementation with logical dependencies
- **Implementation Scope Discipline**: Task boundaries honor previous stage decisions with clear reasoning

## User Review Facilitation

**Guide user through systematic task breakdown review:**

**Key Review Considerations:**

- Do the tasks comprehensively cover all design components without over-engineering?
- Is the task sequence logical for incremental development and dependency management?
- Are the coding activities appropriately scoped and specific for implementation?
- Do task descriptions provide enough detail for systematic implementation execution?
- Are testing tasks integrated appropriately throughout the implementation sequence?
- Is the task granularity appropriate for progress tracking and completion validation?
- Do the scope boundaries make sense and align with your project context and previous decisions?
- Are the implementation priorities aligned with your development goals and constraints?

**User Feedback Options:**

- **Request Changes**: Specify what tasks need modification, additional detail, or restructuring
- **Task Sequence Adjustments**: Reorder tasks for better implementation flow and dependency management
- **Scope Clarifications**: Adjust reasoning for scope boundaries or task inclusion criteria
- **Granularity Adjustments**: Make tasks more or less detailed based on team needs and tracking preferences
- **Ready to Approve**: If satisfied with task breakdown quality and implementation approach

## Iteration and Refinement Process

**If user requests changes, execute systematic task breakdown refinement:**

**Before implementing modifications, carefully analyze specific feedback:**

1. What specific task breakdown changes are being requested and why?
2. How do requested changes align with approved design and requirements context?
3. What modifications maintain Kiro compliance while addressing implementation concerns?
4. How will changes affect incremental development sequencing and dependency management?

**Task Breakdown Refinement Execution Process:**

1. **Analyze specific feedback** and identify precise areas requiring task breakdown modification
2. **Update tasks.md** with requested changes while maintaining complete Kiro compliance and scope discipline
3. **Re-execute quality validation** to ensure all standards maintained including traceability and coding exclusivity
4. **Present updated version** for another review cycle with task breakdown improvements highlighted
5. **Continue iteration until explicit user approval** received with documented implementation satisfaction

# Final Approval and State Management

## Implementation Plan Approval Process

**Upon receiving explicit user approval:**

**Update project state systematically:**

- Mark implementation planning stage as generated: true and approved: true in spec.yaml
- Update project timestamp to reflect Stage 3 completion
- Prepare project for Stage 4 transition with implementation foundation established
- Document implementation plan approval for workflow traceability and task execution preparation

**State Management Updates:**

```yaml
# Update .kiro/specs/[feature-name]/spec.yaml
approvals:
  tasks:
    generated: true
    approved: true
updated_at: "[current ISO timestamp]"
```

**Completion Validation:**

- Implementation task breakdown finalized with complete user approval and implementation satisfaction
- Project state accurately reflects Stage 3 completion with implementation foundation established
- All quality standards met with comprehensive validation and transparent assessment
- Stage 4 prerequisites established and documented for systematic task execution
- Cross-stage traceability maintained from requirements through design to implementation tasks

## Workflow Transition Guidance

**Provide clear guidance for next steps in Kiro workflow:**

**Stage 3 Completion Summary:**

- **Implementation Tasks**: Complete and approved following all Kiro standards with coding task exclusivity
- **Quality Validation**: Comprehensive assessment passed with transparent methodology and educational feedback
- **Design Coverage**: All approved design components addressed in systematic task breakdown with complete coverage
- **Requirements Traceability**: All tasks mapped to specific requirements with complete implementation coverage
- **Scope Discipline**: Implementation boundaries clearly established carrying forward requirements and design reasoning
- **Incremental Development**: Logical task sequence established for progressive implementation with dependency management

**Next Stage Preparation:**

- **Stage 4 Ready**: Task execution can proceed with comprehensive implementation plan and clear task sequence
- **Context Available**: Complete task breakdown will guide execution decisions and progress tracking
- **Scope Inheritance**: Task execution will maintain established scope boundaries from all previous stages
- **Quality Standards**: Implementation approval demonstrates validation approach for task execution and completion assessment

Ready to proceed with Stage 4: Task Execution using the established implementation plan and systematic task breakdown.
