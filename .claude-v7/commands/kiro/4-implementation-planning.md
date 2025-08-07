---
description: "Kiro Stage 3: Transform design into coding task breakdown with strict scope discipline"
argument-hint: "feature-name (kebab-case)"
---

# Kiro Implementation Planning (Stage 3)

## 1. Argument Validation & Feature Selection

Let me check for available features and validate your input.

!ls .kiro/specs/ 2>/dev/null | grep -v "^total" | grep -E "^[a-zA-Z0-9-]+$" || echo "No features found in .kiro/specs/"

**Checking feature argument...**

If you didn't provide a feature name or the feature doesn't exist:

### Available Features in .kiro/specs/

[The list above shows your available features]

**Please specify which feature you'd like to work on for implementation planning:**

- Type the feature name exactly as shown (kebab-case format)
- Feature must have approved requirements from Stage 1
- Feature must have approved design from Stage 2
- Both requirements.md and design.md must exist

**Waiting for your feature selection...**

[Wait for user to provide valid feature name before continuing]

---

Once you provide a valid feature name, I'll continue with that feature.

## 2. State & Context Validation + Prerequisites Check

Loading project context for feature: **${feature-name}**

@.kiro/specs/${feature-name}/spec.yaml
@.kiro/specs/${feature-name}/requirements.md
@.kiro/specs/${feature-name}/design.md
@.kiro/steering/product.md
@.kiro/steering/tech.md  
@.kiro/steering/structure.md

**Validating prerequisites:**

!test -f ".kiro/specs/${feature-name}/spec.yaml" && echo "Found" || echo "Missing"
!test -f ".kiro/specs/${feature-name}/requirements.md" && echo "Found" || echo "Missing"
!test -f ".kiro/specs/${feature-name}/design.md" && echo "Found" || echo "Missing"

**Critical Stage 3 Prerequisites:**

- Feature initialized: ${feature-name}
- Requirements stage: **MUST be approved** (Stage 1 complete)
- Design stage: **MUST be approved** (Stage 2 complete)
- Both requirements.md and design.md exist and accessible
- Steering context loaded for implementation guidance

**Prerequisites Status:**

- Feature: ${feature-name} ✓
- Stage 1 (Requirements): [Checking approval status from spec.yaml]
- Stage 2 (Design): [Checking approval status from spec.yaml]
- Context Documents: [Verifying accessibility]

If previous stages are not approved, you must complete them first:

```
/kiro:2-requirements-clarification ${feature-name}  # if requirements not approved
/kiro:3-design-document-creation ${feature-name}    # if design not approved
```

**Ready to proceed with implementation planning.**

## 3. Implementation Scope Planning Phase

**Feature Context Loaded:** ${feature-name}  
**Current Status:** [Reading from spec.yaml, requirements.md, and design.md for task breakdown context]

**Implementation Planning Phase (Kiro Stage 3)**

Based on your approved design document, I need to break this into actionable coding tasks.

**Analyzing design.md for implementable components:**
[Extract components, interfaces, data models from design.md]

- [Component 1]: Specific coding tasks needed for implementation
- [Component 2]: Interface development and integration tasks
- [Data Model Implementation]: Database schema and data handling code
- [Integration Points]: API connections and external system interfaces

**Implementation Scope Boundaries (Clear Reasoning)**

**Will implement**: Coding tasks for components approved in design.md to satisfy requirements approved in requirements.md.

**Will not implement**:

- Features excluded during requirements approval (maintains user agreement)
- Components excluded during design approval (maintains architecture coherence)  
- Non-coding activities better suited for different stages/roles

**Coding Activity Focus (Kiro Stage 3 Constraints):**

**INCLUDED (Coding Tasks Only):**

- **Code writing**: Creating new functions, classes, modules for approved components
- **Code modification**: Updating existing code to implement design specifications
- **Test creation**: Writing unit, integration tests for implemented code
- **Configuration updates**: Modifying config files for code behavior
- **Database schema**: Creating/modifying data structure code
- **API implementation**: Creating/updating interface code for approved design

**NOT INCLUDED (Different Stages/Skills):**

- **User acceptance testing**: Human validation activities (different skillset/timing)
- **Deployment activities**: Infrastructure operations (different tools/permissions)
- **Performance metrics gathering**: Runtime analysis activities (different stage)
- **End-to-end manual testing**: Application flow validation (different process)

**Reasoning**: This maintains focus on technical implementation excellence while honoring the careful boundary decisions made in previous stages.

**Implementation Planning Questions:**

- Any coding priorities from the design components?
- Testing approach preferences for the implementation?
- Any technical constraints I should consider for task sequencing?

**Ready to proceed with focused implementation planning? Say 'proceed'**

[Wait for user confirmation before task breakdown generation]

## 4. Task Breakdown Generation (Kiro Stage 3)

**Generating implementation task breakdown incorporating:**

- Approved design components and architecture from design.md
- Requirements traceability mapping from requirements.md  
- Steering document guidance for implementation patterns
- Exact Kiro behavioral constraints for coding task exclusivity
- Incremental development principles with dependency management

**CRITICAL KIRO STAGE 3 CONSTRAINTS:**

- Break design components into discrete coding tasks only
- Use numbered checkbox format with 2-level maximum hierarchy
- Ensure incremental development - each task builds on previous
- Map all tasks to specific requirements for traceability
- Maintain coding task exclusivity - no operational activities

**Generating tasks.md...**

Creating comprehensive task breakdown at: `.kiro/specs/${feature-name}/tasks.md`

**KIRO IMPLEMENTATION TASKS TEMPLATE:**

```markdown
# ${feature-name} Implementation Tasks

## Task List

- [ ] 1. [Task Description for specific design component]
  - [Implementation details: what code to write/modify]
  - [Requirements mapping: References specific requirements from requirements.md]
  - [Files/components to be created or modified]
  - [Integration points with existing code]

- [ ] 1.1 [Sub-task for incremental development of Task 1]
  - [Specific coding activity within Task 1 scope]
  - [Dependencies on Task 1 completion]
  - [Testing requirements for this sub-component]

- [ ] 1.2 [Another sub-task building on Task 1.1]
  - [Next incremental coding activity]
  - [Validation criteria for completion]

- [ ] 2. [Task Description for next design component, building on Task 1]
  - [Implementation specifics for this component]
  - [Requirements traceability to specific approved requirements]
  - [Dependencies on previous task outputs]
  - [Integration requirements with Task 1 outputs]

- [ ] 2.1 [Sub-task for Task 2 incremental development]
  - [Specific coding activity details]
  - [Testing integration with previous tasks]

- [ ] 3. [Task Description for integration/testing of implemented components]
  - [Integration coding requirements]
  - [Test implementation for component interactions]
  - [Validation against requirements acceptance criteria]

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

[Generate actual comprehensive task breakdown based on all gathered context and approved design components]

## 5. Quality Validation Framework

**Executing Kiro Stage 3 quality validation checkpoints...**

### Task Format Validation

- Check: `.kiro/specs/${feature-name}/tasks.md` created successfully  
- Check: Numbered checkbox format used ("- [ ] 1.", "- [ ] 1.1")
- Check: Maximum 2-level hierarchy maintained (no deeper nesting)
- Check: Decimal notation used for sub-tasks (1.1, 1.2, 2.1, etc.)
- Check: Simple structure without complex hierarchies
- Check: All tasks have clear completion criteria

### Coding Task Exclusivity Validation  

- Check: All tasks involve code writing, modification, or testing activities only
- Check: No user acceptance testing tasks included (different skillset/timing)
- Check: No deployment activity tasks included (different tools/permissions)
- Check: No performance metrics gathering tasks included (different stage/process)
- Check: No end-to-end manual testing tasks included (different validation process)
- Check: No operational or business process tasks included

### Design Component Coverage Validation

- Check: All major design components from design.md addressed by implementation tasks
- Check: All design interfaces have corresponding coding task implementation
- Check: Data model implementation tasks cover all schemas from design
- Check: Integration points from design addressed in coding tasks
- Check: Error handling patterns from design addressed in implementation tasks
- Check: Testing strategy from design reflected in test implementation tasks

### Requirements Traceability Validation

- Check: Tasks reference specific requirements from requirements.md (not just general categories)
- Check: Granular requirement mapping to individual tasks (not just user stories)
- Check: All approved requirements have corresponding implementation tasks
- Check: No requirements left without implementation coverage
- Check: Task completion criteria enable validation against requirements acceptance criteria

### Incremental Development Validation

- Check: Tasks ordered by implementation dependencies (each builds on previous)
- Check: Each task produces outputs usable by subsequent tasks
- Check: No orphaned or disconnected tasks identified
- Check: Early validation and testing opportunities integrated throughout sequence
- Check: Core functionality implementable and testable in early tasks
- Check: Complexity increases gradually across task sequence

### Implementation Scope Validation

- Check: All tasks trace to approved design components (no speculative additions)
- Check: No tasks implement features from requirements out-of-scope section
- Check: No tasks implement elements from design out-of-scope section
- Check: Task descriptions reference specific approved requirements and design elements
- Check: Out-of-scope boundaries carried forward with original reasoning intact
- Check: Implementation boundaries clearly documented with sound reasoning

**Quality Validation Results:**

**Kiro Stage 3 Quality Assessment:**

- **Task Format Compliance**: Perfect numbered checkbox structure with appropriate hierarchy
- **Coding Task Exclusivity**: All tasks focused on code implementation activities only
- **Design Component Coverage**: All approved design elements addressed in task breakdown
- **Requirements Traceability**: All tasks mapped to specific approved requirements  
- **Incremental Development**: Tasks sequenced for progressive implementation with dependencies
- **Implementation Scope Discipline**: Task boundaries honor previous stage decisions with clear reasoning

**Overall Quality Score: [Calculated based on validation results]**

## 6. Task Review & Revision Cycle

## Implementation Tasks Complete

I've generated a comprehensive task breakdown following all Kiro Stage 3 standards:

- **Design Coverage**: All approved design components addressed through specific coding tasks
- **Coding Task Focus**: Only code writing, modification, and testing tasks included  
- **Requirements Traceability**: All tasks mapped to specific approved requirements for validation
- **Incremental Development**: Tasks sequenced for progressive implementation with clear dependencies
- **Scope Discipline**: Implementation boundaries honor previous stage decisions with sound reasoning

**Generated Document:**
**Location**: `.kiro/specs/${feature-name}/tasks.md`
**Quality Score**: [Score] (meeting all Kiro validation standards and scope discipline)

[Display key task breakdown highlights and implementation sequence]

**Please review your implementation tasks.**

**Consider:**

- Do the tasks comprehensively cover all design components?
- Is the task sequence logical for incremental development?
- Are the coding activities appropriately scoped and specific?
- Do task descriptions provide enough detail for implementation?
- Are testing tasks integrated appropriately throughout the sequence?
- Is the task granularity appropriate for tracking progress?
- Do the scope boundaries make sense for your project context?

**Your options:**

- **Request Changes**: Tell me what tasks need modification or additional detail
- **Task Sequence Adjustments**: Reorder tasks for better implementation flow
- **Scope Clarifications**: Adjust reasoning for scope boundaries or task inclusion
- **Granularity Adjustments**: Make tasks more or less detailed as needed
- **Ready to Approve**: If satisfied, say "looks good", "approved", or "yes"

**What's your feedback?**

[Handle user feedback and revision cycle]

---

### Revision Cycle (if changes requested)

[If user requests changes:]

1. **Analyze specific feedback** and identify task breakdown adjustments needed
2. **Update tasks.md** with requested changes while maintaining Kiro compliance and scope discipline
3. **Re-run quality validation** to ensure all standards maintained including traceability
4. **Present updated version** for another review cycle with task highlights
5. **Continue until explicit approval received**

## 7. Final Approval & State Management

### Implementation Plan Approved

Thank you for the approval! The implementation task breakdown is now finalized and ready for task execution.

**Updating project state...**

```yaml
# Updating .kiro/specs/${feature-name}/spec.yaml
approvals:
  tasks:
    generated: true
    approved: true
updated_at: "[current timestamp]"
```

**State Updated Successfully:**

- Implementation planning stage marked as completed and approved
- Project ready for Stage 4: Task Execution
- All task boundaries clearly established with reasoning
- Use `/kiro:5-task-execution ${feature-name}` to proceed

**Final Deliverables:**

- **Implementation Tasks**: `.kiro/specs/${feature-name}/tasks.md` (Kiro-compliant with reasoning-based scope discipline)
- **Updated Project State**: `.kiro/specs/${feature-name}/spec.yaml` (tasks approved)
- **Quality Validation**: All Kiro Stage 3 standards met with clear scope boundaries
- **Traceability**: Complete mapping from requirements through design to implementation tasks

### Next Steps

Ready to move to **Stage 4: Task Execution**? Run:

```
/kiro:5-task-execution ${feature-name}
```

**Kiro Stage 3 Complete - Implementation Planning Successful!**
