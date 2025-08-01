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

Verify in `.kiro/specs/${input:feature}/spec.yaml`:

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

- **Requirements**: `.kiro/specs/${input:feature}/requirements.md`
- **Design**: `.kiro/specs/${input:feature}/design.md`
- **Metadata**: `.kiro/specs/${input:feature}/spec.yaml`

### Codebase Implementation Context

Use codebase tool to understand:

- **File structure** and organization patterns
- **Existing components** that can be extended or integrated
- **Testing frameworks** and conventions
- **Build and deployment** processes
- **Code style** and conventions

## Task Generation Guidelines

### Task Inclusion Rules

**INCLUDE these task types (coding focus only)**:

- ✅ **Code Implementation**: Writing new components, modules, functions
- ✅ **Code Modification**: Updating existing files and functions
- ✅ **Unit Testing**: Creating tests for new functionality
- ✅ **Integration Testing**: Testing component interactions
- ✅ **Code Documentation**: Inline comments and code-level docs
- ✅ **Database Work**: Migrations, schema changes, data layer code
- ✅ **API Implementation**: Endpoint creation and modification

### Task Exclusion Rules

**EXCLUDE these task types (non-coding activities)**:

- ❌ **Infrastructure Setup**: Server configuration, environment setup
- ❌ **Deployment Tasks**: CI/CD pipeline, production deployment
- ❌ **Documentation Creation**: User guides, technical documentation
- ❌ **External Dependencies**: Installing libraries, configuring tools
- ❌ **Environment Config**: Setting up development environments
- ❌ **Monitoring Setup**: Logging, metrics, alerting configuration

### Task Sizing Guidelines

**Optimal Task Size**: 2-4 hours of focused development work

**Task Breakdown Examples**:

- **Too Large**: "Implement user authentication system" (8+ hours)
- **Right Size**: "Create user login API endpoint with validation" (3 hours)
- **Too Small**: "Add import statement" (15 minutes)

## Task Structure and Format

### Hierarchical Task Organization

Use numbered hierarchy for logical grouping:

```markdown
# Implementation Tasks

## 1. Data Layer Implementation

### 1.1 Create User Model

- [ ] **Task**: Implement User model class with validation
- **Requirement**: REQ-1.1 User data management
- **Acceptance Criteria**: Model includes all required fields with proper validation
- **Files**: `src/models/User.js`
- **Estimated Time**: 2-3 hours

### 1.2 Implement User Repository

- [ ] **Task**: Create database access layer for User operations
- **Requirement**: REQ-1.2 User data persistence
- **Acceptance Criteria**: CRUD operations implemented with error handling
- **Files**: `src/repositories/UserRepository.js`
- **Estimated Time**: 3-4 hours

## 2. API Layer Implementation

### 2.1 User Registration Endpoint

- [ ] **Task**: Implement POST /api/users/register endpoint
- **Requirement**: REQ-2.1 User registration functionality
- **Acceptance Criteria**: Validates input, creates user, returns success/error response
- **Files**: `src/controllers/UserController.js`, `src/routes/userRoutes.js`
- **Estimated Time**: 3-4 hours
```

### Task Detail Template

Each task must include:

```markdown
### {Task Number} {Task Title}

- [ ] **Task**: Clear description of what code to write/modify
- **Requirement**: Reference to specific requirement (REQ-X.X)
- **Acceptance Criteria**: Specific, testable conditions for completion
- **Files**: Files to be created or modified
- **Dependencies**: Other tasks that must be completed first (if any)
- **Estimated Time**: Realistic time estimate (2-4 hours)
- **Testing**: Unit tests and integration tests required
```

## Requirement Traceability Matrix

Create a mapping between requirements and implementation tasks:

```markdown
## Requirement Traceability

| Requirement ID | Description          | Implementation Tasks |
| -------------- | -------------------- | -------------------- |
| REQ-1.1        | User data management | Task 1.1, Task 1.2   |
| REQ-2.1        | User registration    | Task 2.1, Task 3.1   |
| REQ-2.2        | User authentication  | Task 2.2, Task 3.2   |
```

## Implementation Phases

Organize tasks into logical implementation phases:

### Phase 1: Data Layer (Foundation)

- Data model creation
- Database schema changes
- Repository pattern implementation

### Phase 2: Business Logic Layer

- Service layer implementation
- Business rule validation
- Data processing logic

### Phase 3: API Layer

- REST endpoint implementation
- Request/response handling
- Input validation and error handling

### Phase 4: Integration and Testing

- Integration test implementation
- End-to-end testing scenarios
- Error handling validation

## Testing Strategy Integration

### Unit Testing Tasks

For each code implementation task, include corresponding test tasks:

```markdown
### 1.3 Unit Tests for User Model

- [ ] **Task**: Create comprehensive unit tests for User model
- **Requirement**: Testing requirement for REQ-1.1
- **Acceptance Criteria**: 90%+ code coverage, all validation scenarios tested
- **Files**: `tests/models/User.test.js`
- **Dependencies**: Task 1.1 (User Model)
- **Estimated Time**: 2-3 hours
```

### Integration Testing Tasks

```markdown
### 4.1 Integration Tests for User Registration

- [ ] **Task**: Create integration tests for user registration flow
- **Requirement**: End-to-end testing for REQ-2.1
- **Acceptance Criteria**: Tests cover success and error scenarios
- **Files**: `tests/integration/userRegistration.test.js`
- **Dependencies**: Task 2.1, Task 1.1, Task 1.2
- **Estimated Time**: 3-4 hours
```

## Task Dependencies and Sequencing

### Dependency Rules

1. **Data Layer First**: Complete data models before business logic
2. **Service Layer Second**: Implement business logic before API endpoints
3. **API Layer Third**: Create endpoints after business logic
4. **Testing Last**: Unit tests after implementation, integration tests after API layer

### Critical Path Analysis

Identify tasks that block other tasks:

```markdown
## Task Dependencies

### Critical Path Tasks (blocking other work):

- Task 1.1 (User Model) → Blocks Tasks 1.2, 2.1, 3.1
- Task 1.2 (User Repository) → Blocks Tasks 2.1, 4.1
- Task 2.1 (Registration Endpoint) → Blocks Task 4.1

### Parallel Tasks (can be done simultaneously):

- Task 1.3 (Unit Tests) and Task 2.1 (API Endpoint)
- Task 3.1 (Frontend Form) and Task 3.2 (Form Validation)
```

## Implementation Task Document Generation

### 1. Tasks File Creation

Update `.kiro/specs/${input:feature}/tasks.md` with:

- Complete task breakdown following hierarchical structure
- All tasks with requirement traceability
- Clear acceptance criteria and time estimates
- Proper dependency sequencing

### 2. Spec Metadata Update

Update `.kiro/specs/${input:feature}/spec.yaml`:

```yaml
updated_at: "{current_timestamp}"
phase: "tasks-generated"
approvals:
  tasks:
    generated: true
    approved: false # Requires human approval
task_summary:
  total_tasks: { count }
  estimated_hours: { total_hours }
  phases: { phase_count }
```

### 3. Quality Review Checklist

Before completion, verify:

- [ ] All requirements mapped to tasks
- [ ] All design components covered
- [ ] Tasks focus on coding activities only
- [ ] Proper hierarchical numbering used
- [ ] 2-4 hour task sizing maintained
- [ ] Dependencies properly identified
- [ ] Testing tasks included
- [ ] Acceptance criteria are specific and testable

## Task Execution Modes

### Single Task Mode

For methodical, step-by-step execution:

- Execute one task at a time
- Complete full testing before next task
- Detailed validation at each step

### Multiple Task Mode

For parallel or batch execution:

- Group related tasks for batch execution
- Focus on completing entire phases
- Bulk testing after implementation phases

## Next Steps Guidance

After task generation:

1. **Human Review Required**: Review implementation plan for feasibility and completeness
2. **Task Validation**: Confirm tasks cover all requirements and design elements
3. **Time Estimation Review**: Validate time estimates are realistic
4. **Manual Approval**: Update `spec.yaml` to mark tasks as approved
5. **Begin Implementation**: Use spec-execution chat mode after task approval

Generate a comprehensive implementation plan that provides clear, actionable coding tasks with full requirement traceability and realistic time estimates.
