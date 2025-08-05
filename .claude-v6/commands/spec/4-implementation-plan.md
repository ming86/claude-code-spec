---
description: 'Generate implementation tasks with requirement traceability and coding focus'
argument-hint: '[feature-name]'
---

# Role and Objective

Systematically break down approved technical designs into specific, actionable coding tasks with clear requirement traceability and optimal execution sequencing.

# Instructions

## ⚠️ CRITICAL: Scope Control Requirements ⚠️

**FEATURE EXPANSION CREATES SERIOUS MAINTENANCE BURDEN FOR MAINTAINERS**

- **MUST address ONLY approved requirements** - adding tasks beyond scope creates ongoing maintenance debt
- **MUST NOT expand scope** beyond what was explicitly approved in requirements and design phases
- **MUST trace every task** back to a specific approved requirement
- **MUST document additional ideas** for future consideration but EXCLUDE from current implementation
- **Task generation beyond approved scope** creates technical debt and maintenance overhead

## Implementation Planning Strategy

- **Prerequisites Dependency**: Both requirements and design must be approved before task generation
- **Coding Focus**: Tasks must focus exclusively on coding activities (no infrastructure, deployment, or external tasks)
- **Traceability**: All tasks must map back to specific requirements with clear references
- **Time Estimation**: Tasks should be sized at 2-4 hours for optimal execution and completion tracking
- **Quality Standards**: Tasks must include clear acceptance criteria and testing requirements

## Anti-Shortcut Quality Patterns

- Analyze approved specifications thoroughly rather than making assumptions about implementation scope
- Create task breakdown based on actual design components and requirements, not generic development patterns
- Use systematic requirement mapping to ensure complete coverage without scope expansion
- Generate specific, actionable tasks based on approved architecture rather than theoretical approaches

# Execution Steps

## Step 1: Prerequisites & Context Analysis

### ⚠️ CRITICAL: Prerequisites Validation ⚠️

**BOTH requirements and design must be approved before proceeding:**

Check `.spec-workflow/specs/{feature}/spec.yaml`:

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

- **Requirements**: `.spec-workflow/specs/{feature}/requirements.md` - Extract all functional and non-functional requirements
- **Design**: `.spec-workflow/specs/{feature}/design.md` - Understand technical architecture and component specifications  
- **Metadata**: `.spec-workflow/specs/{feature}/spec.yaml` - Verify approval status and project context

### Codebase Implementation Context

**Analysis Process**:

- Understand file structure and organization patterns
- Identify existing components that can be extended or integrated
- Examine testing frameworks and conventions (unit, integration, e2e)
- Analyze build and deployment processes and scripts
- Review code style and conventions (linting, formatting)
- Study database migration patterns and tools
- Understand API development patterns and existing endpoint structures

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

- [ ] **Task**: Create comprehensive unit tests for User model
- **Requirement**: Testing requirement for REQ-1.1
- **Acceptance Criteria**: Test coverage includes all validation scenarios and edge cases
- **Files**: `tests/models/User.test.js`
- **Dependencies**: Task 1.1 (User Model)
- **Estimated Time**: 2-3 hours
```

#### Integration Testing Tasks

```markdown
### 4.1 Integration Tests for User Registration

- [ ] **Task**: Create integration tests for user registration flow
- **Requirement**: End-to-end testing for REQ-2.1
- **Acceptance Criteria**: Tests cover success and error scenarios with database integration
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

Update `.spec-workflow/specs/{feature}/tasks.md` with:

- Complete task breakdown following hierarchical structure
- All tasks with requirement traceability
- Clear acceptance criteria and time estimates
- Proper dependency sequencing

### 2. Spec Metadata Update

Update `.spec-workflow/specs/{feature}/spec.yaml`:

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

# Task Transformations

Transform non-coding tasks to coding equivalents:

- **"Deploy to production"** → "Create deployment configuration files"
- **"User acceptance testing"** → "Create automated test suite"
- **"Performance monitoring"** → "Add performance logging to code"
- **"Marketing tasks"** → "Create technical documentation"
- **"Environment setup"** → "Create configuration management code"

# Requirement Traceability

- **Each task MUST reference** specific requirements using format: `(_Requirements: REQ-{ID}_)`
- **Requirements can be referenced by multiple tasks** when implementation spans multiple components
- **All requirements MUST be covered** by at least one task
- **Traceability matrix MUST be included** showing requirement-to-task mapping

# Task Dependencies

- **Sequential Dependencies**: Tasks that must be completed before others can start
- **Parallel Execution**: Tasks that can be worked on simultaneously
- **Phase Organization**: Logical grouping of related tasks
- **Execution Order**: Clear guidance on task sequencing

# Quality Validation

## Quality Review Checklist

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

## Task Quality Standards

- **Specificity**: Each task clearly defines what code to write/modify
- **Testability**: Clear acceptance criteria for task completion
- **Traceability**: Direct mapping to requirements and design components
- **Independence**: Tasks can be executed without external blockers
- **Completeness**: All design components covered by tasks

# Examples

## Argument Handling

```bash
/spec:4-implementation-plan user-authentication-system
/spec:4-implementation-plan payment-processing-integration
/spec:4-implementation-plan real-time-notifications
```

## Task Generation Process

1. **Prerequisites Check**: "Verifying approvals in spec.yaml... Both requirements and design approved ✓"
2. **Specification Analysis**: "Reading approved requirements.md and design.md... Analyzing scope..."
3. **Codebase Analysis**: "Understanding testing patterns and component structure..."
4. **Task Generation**: "Breaking down authentication feature into 8 tasks across 3 phases based on requirements REQ-1.1 through REQ-1.6..."
5. **Validation**: "All 6 requirements mapped to tasks, 24 total hours estimated, scope limited to approved requirements only..."

## Multi-Language Task Patterns

- **Python**: "Create User model class with validation (_Requirements: REQ-1.1_)"
- **C#**: "Implement User entity with data annotations (_Requirements: REQ-1.1_)"
- **JavaScript**: "Create User model with schema validation (_Requirements: REQ-1.1_)"

## Scope Control Examples

- **✅ Correct**: "Implement user login endpoint as specified in REQ-2.1"
- **❌ Scope Creep**: "Implement user login endpoint with OAuth integration and rate limiting"

## Complete Feature Implementation Plan

```markdown
# Implementation Tasks: User Authentication System

**Status:** Tasks Generated ✅
**Generated Date:** 2024-01-15

## Implementation Overview

Task breakdown for user authentication system based on approved requirements and design specifications. Implementation follows established project patterns and integrates with existing architecture.

## Implementation Tasks

### 1. Data Layer Implementation  

#### 1.1 Create User Model (_Requirements: REQ-1.1_)

**Estimated Time:** 2-3 hours
**Description:** Implement User data model with validation rules and constraints

**Acceptance Criteria:**
- User model includes all required fields (id, email, password_hash, created_at, updated_at)
- Password validation enforces minimum security requirements
- Email validation ensures proper format and uniqueness
- Model integrates with existing database ORM patterns

**Files to Modify:**
- `src/models/User.js`
- `src/models/index.js`

**Testing Requirements:**
- Unit tests for all validation rules
- Edge case testing for invalid inputs

#### 1.2 Implement User Repository (_Requirements: REQ-1.2_)

**Estimated Time:** 3-4 hours  
**Description:** Create data access layer for User operations

**Acceptance Criteria:**
- CRUD operations implemented (create, read, update, delete)
- Error handling for database connection issues
- Query optimization for user lookup operations
- Integration with existing repository patterns

**Files to Modify:**
- `src/repositories/UserRepository.js`
- `src/repositories/index.js`

**Testing Requirements:**
- Unit tests for all repository methods
- Database integration tests

### 2. API Layer Implementation

#### 2.1 User Registration Endpoint (_Requirements: REQ-2.1_)

**Estimated Time:** 3-4 hours
**Description:** Implement POST /api/users/register endpoint with validation

**Acceptance Criteria:**
- Validates input data according to User model requirements  
- Hashes password securely before storage
- Returns appropriate success/error responses
- Integrates with existing API middleware

**Files to Modify:**
- `src/controllers/UserController.js`
- `src/routes/userRoutes.js`
- `src/middleware/validation.js`

**Testing Requirements:**
- Unit tests for controller logic
- Integration tests for complete registration flow

### 3. Testing Implementation

#### 3.1 Unit Tests for Authentication (_Requirements: REQ-1.1, REQ-2.1_)

**Estimated Time:** 2-3 hours
**Description:** Comprehensive unit test coverage for authentication components

**Acceptance Criteria:**
- Test coverage exceeds 90% for authentication modules
- All edge cases and error conditions covered
- Tests follow existing project testing patterns

**Files to Modify:**
- `tests/models/User.test.js`
- `tests/controllers/UserController.test.js`

**Testing Requirements:**
- Automated test execution in CI pipeline
- Performance benchmarks for critical operations

---

## Task Dependencies & Execution Order

### Phase 1: Foundation (Parallel Execution Possible)
- Task 1.1 (User Model)
- Task 1.2 (User Repository) - depends on 1.1

### Phase 2: API Implementation (Sequential Dependencies)  
- Task 2.1 (Registration Endpoint) - depends on 1.1, 1.2

### Phase 3: Testing and Validation
- Task 3.1 (Unit Tests) - depends on all previous tasks

## Traceability Matrix

| Task | Requirements Addressed | Validation Method  |
| ---- | ---------------------- | ------------------ |
| 1.1  | REQ-1.1               | Unit tests + integration tests |
| 1.2  | REQ-1.2               | Repository tests + database tests |
| 2.1  | REQ-2.1               | API tests + end-to-end tests |
| 3.1  | REQ-1.1, REQ-2.1      | Test coverage reports |

## Quality Gates

- **Definition of Done:** All acceptance criteria met, tests passing, code reviewed
- **Acceptance Criteria:** Specific, measurable conditions for each task
- **Performance Criteria:** Response times under 200ms for authentication operations
```

Generate an appropriate implementation plan that provides clear, actionable coding tasks with full requirement traceability, realistic time estimates, and strict scope control to prevent maintenance burden.
