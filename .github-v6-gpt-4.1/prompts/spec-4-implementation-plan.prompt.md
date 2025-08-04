---
description: Generate implementation tasks with requirement traceability and coding focus
mode: agent
tools: ['codebase', 'usages', 'problems', 'findTestFiles', 'editFiles', 'search', 'get_syntax_docs', 'mermaid-diagram-validator']
---

# Implementation Tasks Generation

Generate appropriate, actionable coding tasks for feature: **${input:feature:Enter feature name}** that bridge approved technical designs with executable development work.

**Task Execution Mode**: ${input:executionMode:single|multiple} task execution preference

# Execution Steps

## Step 1: Prerequisites & Context Analysis

### ⚠️ CRITICAL: Prerequisites Validation ⚠️

**BOTH requirements and design must be approved before proceeding:**

Check `.spec-workflow/specs/${input:feature}/spec.yaml`:

```yaml
approvals:
  requirements:
    approved: true # Must be true
  design:
    approved: true # Must be true
```

**If not fully approved**: Stop immediately with message: "Both requirements and design must be approved in spec.yaml before task generation can proceed. Please complete all approvals first."

### ⚠️ CRITICAL: STRICT SCOPE CONTROL ⚠️

**FEATURE EXPANSION CREATES SERIOUS MAINTENANCE BURDEN**

- **MUST generate tasks ONLY for approved requirements** - scope expansion creates ongoing maintenance debt
- **MUST trace every task back to approved requirement** - no additional functionality allowed
- **MUST NOT add optimizations, enhancements, or "nice-to-have" features** beyond approved scope
- **Document additional ideas separately** - exclude from current implementation tasks

### Complete Specification Review

**MUST READ AND ANALYZE** approved documents:

- **Requirements**: `.spec-workflow/specs/${input:feature}/requirements.md` - Extract all functional and non-functional requirements
- **Design**: `.spec-workflow/specs/${input:feature}/design.md` - Understand technical architecture and component specifications
- **Metadata**: `.spec-workflow/specs/${input:feature}/spec.yaml` - Verify approval status and project context

### Codebase Implementation Context

**Analysis Process**:

- Use `search` tool to locate project files and configuration
- Use `codebase` semantic search tool to understand:
  - **File structure** and organization patterns
  - **Existing components** that can be extended or integrated
  - **Testing frameworks** and conventions (unit, integration, e2e)
  - **Build and deployment** processes and scripts
  - **Code style** and conventions (linting, formatting)
  - **Database migration** patterns and tools
  - **API development** patterns and existing endpoint structures

## Step 2: Task Generation Guidelines

### ⚠️ CRITICAL: Task Scope Control ⚠️

**EVERY TASK MUST:**

- **Trace back to specific approved requirement** (REQ-X.X format)
- **Focus exclusively on coding activities** - no infrastructure or deployment
- **Stay within approved scope** - no feature expansion allowed
- **Include clear acceptance criteria** for completion validation

### Task Inclusion Rules

**MUST INCLUDE these task types (coding focus only)**:

- ✅ **Code Implementation**: Writing new components, modules, functions
- ✅ **Code Modification**: Updating existing files and functions
- ✅ **Unit Testing**: Creating tests for new functionality
- ✅ **Integration Testing**: Testing component interactions
- ✅ **Code Documentation**: Inline comments and code-level docs
- ✅ **Database Work**: Migrations, schema changes, data layer code
- ✅ **API Implementation**: Endpoint creation and modification

### Task Exclusion Rules

**MUST EXCLUDE these task types (non-coding activities)**:

- ❌ **Infrastructure Setup**: Server configuration, environment setup
- ❌ **Deployment Tasks**: CI/CD pipeline, production deployment
- ❌ **Documentation Creation**: User guides, technical documentation
- ❌ **External Dependencies**: Installing libraries, configuring tools
- ❌ **Environment Config**: Setting up development environments
- ❌ **Monitoring Setup**: Logging, metrics, alerting configuration

### Task Sizing Guidelines

**CRITICAL**: Maintain optimal task size of 2-4 hours of focused development work for effective execution and progress tracking

**Task Breakdown Examples**:

- **Too Large**: "Implement user authentication system" (8+ hours)
- **Right Size**: "Create user login API endpoint with validation" (3 hours)
- **Too Small**: "Add import statement" (15 minutes)

## Step 3: Task Structure and Format Generation

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

## Step 4: Requirement Traceability Matrix

Create a mapping between requirements and implementation tasks:

```markdown
## Requirement Traceability

| Requirement ID | Description          | Implementation Tasks |
| -------------- | -------------------- | -------------------- |
| REQ-1.1        | User data management | Task 1.1, Task 1.2   |
| REQ-2.1        | User registration    | Task 2.1, Task 3.1   |
| REQ-2.2        | User authentication  | Task 2.2, Task 3.2   |
```

### Implementation Phases

Organize tasks into logical implementation phases:

#### Phase 1: Data Layer (Foundation)

- Data model creation
- Database schema changes
- Repository pattern implementation

#### Phase 2: Business Logic Layer

- Service layer implementation
- Business rule validation
- Data processing logic

#### Phase 3: API Layer

- REST endpoint implementation
- Request/response handling
- Input validation and error handling

#### Phase 4: Integration and Testing

- Integration test implementation
- End-to-end testing scenarios
- Error handling validation

### Testing Strategy Integration

#### Unit Testing Tasks

For each code implementation task, include corresponding test tasks:

```markdown
### 1.3 Unit Tests for User Model

- [ ] **Task**: Create appropriate unit tests for User model
- **Requirement**: Testing requirement for REQ-1.1
- **Acceptance Criteria**: Appropriate code coverage with all validation scenarios tested
- **Files**: `tests/models/User.test.js`
- **Dependencies**: Task 1.1 (User Model)
- **Estimated Time**: 2-3 hours
```

#### Integration Testing Tasks

```markdown
### 4.1 Integration Tests for User Registration

- [ ] **Task**: Create integration tests for user registration flow
- **Requirement**: End-to-end testing for REQ-2.1
- **Acceptance Criteria**: Tests cover success and error scenarios
- **Files**: `tests/integration/userRegistration.test.js`
- **Dependencies**: Task 2.1, Task 1.1, Task 1.2
- **Estimated Time**: 3-4 hours
```

## Step 5: Task Dependencies and Sequencing

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

## Step 6: Document Generation & Validation

### 1. Tasks File Creation

Update `.spec-workflow/specs/${input:feature}/tasks.md` with:

- Complete task breakdown following hierarchical structure
- All tasks with requirement traceability
- Clear acceptance criteria and time estimates
- Proper dependency sequencing

### 2. Spec Metadata Update

Update `.spec-workflow/specs/${input:feature}/spec.yaml`:

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

- [ ] All approved requirements mapped to tasks with clear traceability
- [ ] All design components covered by implementation tasks
- [ ] Tasks focus exclusively on coding activities (no infrastructure/deployment)
- [ ] **SCOPE CONTROL**: Tasks include ONLY approved requirements - no additional features or optimizations
- [ ] Proper hierarchical numbering used throughout
- [ ] 2-4 hour task sizing maintained consistently
- [ ] Dependencies properly identified and sequenced
- [ ] Testing tasks included for all implementation tasks
- [ ] Acceptance criteria are specific and testable (no vague completion conditions)
- [ ] Critical path analysis provided
- [ ] All files updated with generated content

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

## Defensive Patterns

### Error Handling

- **If requirements/design not approved**: Stop immediately with clear message: "Both requirements and design must be approved in spec.yaml before task generation can proceed. Please complete all approvals first."
- **If specification analysis reveals gaps**: Document missing information clearly and request clarification before proceeding
- **If codebase context is unclear**: Use tools extensively to understand patterns before generating tasks
- **If tasks become too large (>4 hours)**: Break into smaller subtasks with clear intermediate deliverables and acceptance criteria
- **If dependency chains are overly complex**: Document critical path analysis and suggest parallel execution opportunities
- **If requirement coverage appears incomplete**: Identify specific gaps and request clarification before proceeding
- **If scope expansion is tempting**: Strictly limit tasks to approved requirements only - document any additional ideas for future consideration but do not include in current tasks

### Quality Validation

- **If any requirement lacks corresponding tasks**: Add specific tasks to address the gap
- **If task acceptance criteria are unclear**: Make them specific, testable, and unambiguous
- **If dependency ordering creates bottlenecks**: Restructure tasks to enable more parallel execution

## Success Criteria

Task generation is complete when:

- [ ] All approved requirements are mapped to specific implementation tasks with clear traceability
- [ ] All design components are covered by tasks
- [ ] Tasks focus exclusively on coding activities (no infrastructure/deployment)
- [ ] **SCOPE CONTROL**: Tasks include ONLY approved requirements - no additional features or optimizations
- [ ] Proper hierarchical numbering is used throughout
- [ ] 2-4 hour task sizing is maintained consistently
- [ ] Dependencies are properly identified and sequenced
- [ ] Testing tasks are included for all implementation tasks
- [ ] Acceptance criteria are specific and testable (no vague completion conditions)
- [ ] Critical path analysis is provided
- [ ] All files are updated with generated content

Generate an appropriate implementation plan that provides clear, actionable coding tasks with full requirement traceability, realistic time estimates, and strict scope control to prevent maintenance burden.
