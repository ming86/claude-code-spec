---
description: Generate and write implementation plan (tasks.md) from approved design with coding-only focus
tools: ['codebase', 'search', 'editFiles']
---

# Implementation Plan Generation Mode

Generate comprehensive implementation plan for feature: **${input:feature:Enter feature name}**

## Prerequisites Validation

Verify design is complete and approved before proceeding:

- Check `.spec-workflow/specs/${input:feature}/design.md` exists
- Ensure technical design includes all components
- Confirm design phase approval in spec.yaml

## Context Analysis

### Complete Specification Review

Analyze approved documents:

- **Requirements**: `.spec-workflow/specs/${input:feature}/requirements.md`
- **Design**: `.spec-workflow/specs/${input:feature}/design.md`
- **Metadata**: `.spec-workflow/specs/${input:feature}/spec.yaml`

### Codebase Implementation Context

Use codebase tool to understand:

- **File structure** and organization patterns
- **Existing components** that can be extended or integrated
- **Testing frameworks** and conventions
- **Build and deployment** processes
- **Code style** and conventions

## Implementation Plan Generation

### Task Generation Rules

**INCLUDED Task Types (Coding Focus Only)**:

- ✅ **Writing new code** components and modules
- ✅ **Modifying existing code** files and functions
- ✅ **Creating unit tests** for new functionality
- ✅ **Adding integration tests** for new features
- ✅ **Code documentation** and comments
- ✅ **Database migrations** and schema changes
- ✅ **API endpoint implementation**
- ✅ **Configuration file updates**

**EXCLUDED Task Types (Transform to Coding Tasks)**:

Transform non-coding tasks to coding equivalents:

- ❌ "Deploy to production" → ✅ "Create deployment configuration files"
- ❌ "User acceptance testing" → ✅ "Create automated test suite"
- ❌ "Performance monitoring" → ✅ "Add performance logging and metrics code"
- ❌ "Marketing tasks" → ✅ "Create technical documentation"
- ❌ "Business planning" → ✅ "Create configuration for business rules"

### Task Structure Requirements

**Format as numbered checkbox list with maximum 2-level hierarchy**:

- Top-level items (1, 2, 3) for major components
- Sub-tasks numbered with decimal notation (1.1, 1.2, 2.1, 2.2)
- Each item must be a checkbox `- [ ]`
- Simple structure preferred over complex nesting

**Each task must include**:

- **Clear objective** involving writing, modifying, or testing code
- **Requirements reference** mapping to specific requirements from requirements.md
- **Time estimate** (2-4 hours per task)
- **Acceptance criteria** for completion verification
- **Dependencies** and prerequisite tasks

### Implementation Plan Structure

Generate `tasks.md` file with this structure:

```markdown
# Implementation Plan: {feature_name}

## Progress Tracking

- **Created**: {current_timestamp}
- **Status**: Ready for implementation
- **Total tasks**: {count}
- **Completed**: 0
- **Remaining**: {count}

## Implementation Tasks

- [ ] **1. Data Layer Implementation**

  - [ ] **1.1** Create database schema and migration files

    - Implement Entity models using [ORM/Database framework]
    - Create migration scripts for schema changes
    - Add database connection configuration
    - _Requirements: 2.1, 2.2_ | _Estimate: 3-4 hours_

  - [ ] **1.2** Implement data access layer
    - Create repository classes for data operations
    - Implement CRUD operations with error handling
    - Add data validation and business rules
    - _Requirements: 2.3, 2.4_ | _Estimate: 2-3 hours_

- [ ] **2. Business Logic Implementation**

  - [ ] **2.1** Implement core business logic
    - Create service classes for business operations
    - Implement validation and business rules
    - Add error handling for business exceptions
    - _Requirements: 3.1, 3.2_ | _Estimate: 3-4 hours_

- [ ] **3. API Layer Implementation**

  - [ ] **3.1** Create API endpoints and routing
    - Implement REST endpoints following existing patterns
    - Add input validation and sanitization
    - Implement authentication middleware integration
    - _Requirements: 4.1, 4.2_ | _Estimate: 4-5 hours_

- [ ] **4. Testing Implementation**

  - [ ] **4.1** Create comprehensive test suite
    - Implement unit tests for business logic
    - Create integration tests for API endpoints
    - Add test data fixtures and utilities
    - _Requirements: All requirements coverage_ | _Estimate: 6-8 hours_

- [ ] **5. Integration and Documentation**

  - [ ] **5.1** Integrate with existing system
    - Update existing components for new feature integration
    - Add code documentation and comments
    - Create configuration for feature settings
    - _Requirements: 1.3, 5.1_ | _Estimate: 2-4 hours_
```

## Quality Validation

### Task Completeness Check

Ensure implementation plan covers:

- [ ] All functional requirements have corresponding tasks
- [ ] All non-functional requirements addressed
- [ ] Task dependencies properly ordered
- [ ] Time estimates realistic (2-4 hours per task)
- [ ] Acceptance criteria specific and testable
- [ ] Requirements traceability maintained

### Implementation Readiness

Verify tasks include:

- [ ] Specific files and components to create/modify
- [ ] Integration points with existing code identified
- [ ] Testing requirements for all components
- [ ] Error handling approaches specified
- [ ] Code patterns consistent with existing codebase

## Task Planning Guidelines

### Incremental Development Approach

- **Build incrementally**: Each task builds on previous tasks
- **Early validation**: Prioritize core functionality for early testing
- **Test-driven emphasis**: Include testing in task planning
- **No big jumps**: Avoid complexity leaps between tasks
- **Integration focus**: Ensure no orphaned code components

### Requirement Traceability

Map every task to specific requirements:

```markdown
_Requirements: 1.1, 2.3_ - References specific requirement numbers from requirements.md
```

**Complete coverage verification**:

- Every requirement has corresponding implementation tasks
- No tasks exist without requirement justification
- Task complexity aligns with requirement complexity

## File Generation Process

### Create Implementation Plan File

Use editFiles tool to create: `.spec-workflow/specs/${input:feature}/tasks.md`

**Content includes**:

- Progress tracking section
- Numbered task list with checkboxes
- Requirement references for each task
- Time estimates and acceptance criteria
- Implementation dependencies and ordering

### Update Metadata

Update `.spec-workflow/specs/${input:feature}/spec.yaml`:

```yaml
phase: "implementation-plan-generated"
progress:
  requirements: 100
  design: 100
  implementation_plan: 100
approvals:
  requirements:
    generated: true
    approved: true
  design:
    generated: true
    approved: true
  implementation_plan:
    generated: true
    approved: false
updated_at: "{current_timestamp}"
```

## Boundaries and Constraints

### What This Phase DOES

- ✅ Analyze approved design document
- ✅ Generate detailed task breakdown
- ✅ Write tasks.md file with implementation plan
- ✅ Map tasks to specific requirements
- ✅ Provide time estimates and acceptance criteria
- ✅ Stop after plan generation for human review

### What This Phase DOES NOT DO

- ❌ Execute any implementation tasks
- ❌ Write actual application code
- ❌ Modify existing application files
- ❌ Run tests or validate implementations
- ❌ Proceed to task execution automatically

## Completion Process

After generating implementation plan:

1. **Write tasks.md file** with complete task breakdown
2. **Update spec.yaml** with generation status
3. **Stop for human review** - do not proceed to execution
4. **Request approval** - wait for user to review and approve plan
5. **Phase boundary**: Hand off to Phase 5 (spec-5-task-execution) after approval

Generate a comprehensive, actionable implementation plan that provides clear guidance for development while ensuring complete requirement coverage and maintaining proper phase separation.
