---
description: Generate implementation tasks with requirement traceability and coding focus
mode: agent
tools: ['codebase', 'search', 'editFiles']
---

# Implementation Tasks Generation

Generate detailed implementation tasks for feature: **${input:feature:Enter feature name}**

**Task Execution Mode**: ${input:executionMode:single|multiple} task execution preference

## Prerequisites Validation

**CRITICAL**: Tasks can only be generated after both requirements and design are approved.

### Approval Status Check

Verify in `.spec-workflow/specs/${input:feature}/spec.yaml`:

```yaml
approvals:
  requirements:
    approved: true # Must be true
  design:
    approved: true # Must be true
```

**If not fully approved**: Complete review and approval of requirements and design first.

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

### Steering Guidelines

Reference for implementation approach:

- **Architecture patterns**: `.spec-workflow/steering/structure.md`
- **Development practices**: `.spec-workflow/steering/tech.md`
- **Project constraints**: `.spec-workflow/steering/product.md`

## Task Generation Rules

### INCLUDED Task Types (Coding Focus)

- ✅ **Writing new code** components and modules
- ✅ **Modifying existing code** files and functions
- ✅ **Creating unit tests** for new functionality
- ✅ **Adding integration tests** for new features
- ✅ **Code documentation** and comments
- ✅ **Database migrations** and schema changes
- ✅ **API endpoint implementation**
- ✅ **Configuration file updates**

### EXCLUDED Task Types (Transform to Coding Tasks)

Transform non-coding tasks to coding equivalents:

- ❌ "Deploy to production" → ✅ "Create deployment configuration files"
- ❌ "User acceptance testing" → ✅ "Create automated test suite"
- ❌ "Performance monitoring" → ✅ "Add performance logging and metrics code"
- ❌ "Marketing tasks" → ✅ "Create technical documentation"
- ❌ "Business planning" → ✅ "Create configuration for business rules"

## Task Structure and Format

### Hierarchical Organization

Use **maximum 2-level hierarchy** (1.1, 1.2, 2.1, 2.2):

```markdown
# Implementation Plan

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

- [ ] **2. API Layer Implementation**

  - [ ] **2.1** Create API endpoints and routing

    - Implement REST endpoints following existing patterns
    - Add input validation and sanitization
    - Implement authentication middleware integration
    - _Requirements: 3.1, 3.2_ | _Estimate: 4-5 hours_

  - [ ] **2.2** Add API documentation and testing
    - Create OpenAPI/Swagger documentation
    - Implement API integration tests
    - Add error response handling
    - _Requirements: 3.3_ | _Estimate: 2-3 hours_
```

### Task Quality Requirements

Each task must include:

- **Task number**: Hierarchical numbering (1.1, 1.2, 2.1, 2.2)
- **Clear description**: Specific, actionable implementation steps
- **Requirements reference**: `_Requirements: 1.1, 2.3_` mapping to requirements.md
- **Time estimate**: Realistic 2-4 hour estimates per task
- **Acceptance criteria**: Clear definition of "done"
- **Dependencies**: Prerequisites and order dependencies

### Requirement Traceability

Map every task to specific requirements:

```markdown
_Requirements: 1.1, 2.3_ - References specific requirement numbers from requirements.md
```

Ensure **complete coverage**:

- Every requirement has corresponding implementation tasks
- No tasks exist without requirement justification
- Task complexity aligns with requirement complexity

## Task Categories and Examples

### 1. Data Model Implementation

```markdown
- [ ] **1.1** Implement [Entity] data model
  - Create TypeScript interfaces for data structures
  - Implement database entity with ORM annotations
  - Add data validation rules and constraints
  - _Requirements: 2.1_ | _Estimate: 2-3 hours_
```

### 2. Business Logic Implementation

```markdown
- [ ] **2.1** Implement [Feature] business logic
  - Create service classes for business operations
  - Implement validation and business rules
  - Add error handling for business exceptions
  - _Requirements: 3.1, 3.2_ | _Estimate: 3-4 hours_
```

### 3. API Implementation

```markdown
- [ ] **3.1** Create [Feature] API endpoints
  - Implement REST controller with CRUD operations
  - Add request/response DTOs and validation
  - Integrate with authentication and authorization
  - _Requirements: 4.1, 4.2_ | _Estimate: 4-5 hours_
```

### 4. Testing Implementation

```markdown
- [ ] **4.1** Create comprehensive test suite
  - Implement unit tests for business logic
  - Create integration tests for API endpoints
  - Add test data fixtures and utilities
  - _Requirements: All requirements coverage_ | _Estimate: 6-8 hours_
```

### 5. Integration Implementation

```markdown
- [ ] **5.1** Integrate with existing system
  - Update existing components for new feature integration
  - Implement data migration scripts if needed
  - Add configuration for feature flags or settings
  - _Requirements: 1.3, 5.1_ | _Estimate: 2-4 hours_
```

## Context Optimization for Implementation

### Single Task Mode

When `executionMode = single`:

- Focus on one task at a time
- Provide detailed implementation guidance
- Include comprehensive acceptance criteria
- Stop after each task for review

### Multiple Task Mode

When `executionMode = multiple`:

- Group compatible tasks for efficiency
- Monitor context usage (stay under 90k tokens)
- Batch tasks by component or layer
- Optimize for interaction efficiency

## Quality Validation

### Task Completeness Check

- [ ] All functional requirements covered by tasks
- [ ] All non-functional requirements addressed
- [ ] Task dependencies properly ordered
- [ ] Time estimates realistic and achievable
- [ ] Acceptance criteria specific and testable

### Implementation Readiness

- [ ] Tasks reference specific files and components
- [ ] Integration points with existing code identified
- [ ] Testing requirements included for all components
- [ ] Error handling approaches specified

## Metadata Updates

Update spec.yaml upon completion:

```yaml
phase: "tasks-generated"
progress:
  requirements: 100
  design: 100
  tasks: 100
approvals:
  requirements:
    generated: true
    approved: true
  design:
    generated: true
    approved: true
  tasks:
    generated: true
    approved: false
updated_at: "{current_timestamp}"
```

## Next Steps

After task generation:

1. **Human Review**: Thoroughly review implementation plan
2. **Task Validation**: Ensure proper sizing and requirement coverage
3. **Edit as Needed**: Adjust tasks, estimates, or dependencies
4. **Approve Tasks**: Update spec.yaml to set `tasks.approved: true`
5. **Begin Implementation**: Use spec-implementation mode or execute-tasks

Generate a comprehensive, well-structured implementation plan that provides clear guidance for development while ensuring complete requirement coverage and quality implementation.
