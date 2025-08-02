---
description: Implementation planning and task structure standards for tasks.md generation
applyTo: ".spec-workflow/**/tasks.md"
---

# Implementation Planning Standards

Standards for generating implementation plans and task structures in the spec-driven development workflow.

## Document Structure Template

Tasks documents MUST follow this comprehensive structure:

```markdown
# Implementation Tasks: {Feature Name}

**Status:** {Tasks Generated/In Progress/Completed} ✅  
**Generated Date:** {YYYY-MM-DD}

## Implementation Overview

Brief summary of implementation approach and key findings from codebase analysis.

## Implementation Tasks

### 1. {Category Name}

#### 1.1 {Task Name} (_Requirements: REQ-{ID}_)

**Estimated Time:** {2-4} hours  
**Description:** {Clear description of what needs to be implemented}

**Acceptance Criteria:**

- {Specific, testable completion criterion}
- {Integration requirement or validation}
- {Quality standard or testing requirement}

**Files to Modify:**

- `{path/to/file1.ext}`
- `{path/to/file2.ext}`

**Testing Requirements:**

- {Unit tests specification}
- {Integration tests specification}

#### 1.2 {Next Task} (_Requirements: REQ-{ID}_)

[Same format structure]

### 2. {Next Category}

[Continue with same pattern]

---

## Task Dependencies & Execution Order

### Phase 1: {Phase Name} (Parallel Execution Possible)

- Tasks {list of task numbers}

### Phase 2: {Next Phase} (Sequential Dependencies)

- Task {X} (requires Phase 1 completion)

## Traceability Matrix

| Task | Requirements Addressed | Validation Method  |
| ---- | ---------------------- | ------------------ |
| 1.1  | REQ-{ID}               | {Testing approach} |
| 1.2  | REQ-{ID}               | {Testing approach} |

## Quality Gates

- **Definition of Done:** {Completion criteria}
- **Acceptance Criteria:** {Quality standards}
- **Performance Criteria:** {Performance requirements}
```

## Task Structure Requirements

### Mandatory Task Focus

- **MUST focus on coding tasks only** (writing, modifying, testing code)
- **MUST exclude deployment/user testing tasks**
- **MUST reference specific requirements** for each task using format: `(_Requirements: REQ-{ID}_)`
- **MUST use hierarchical numbering** (1.1, 1.2, 2.1, 2.2 - max 2 levels)
- **MUST use checkbox format** for task tracking: `- [ ]` or `- [x]`

### Task Quality Standards

- **Each task should be completable in 2-4 hours** of focused development work
- **Include clear acceptance criteria** for task completion with specific, testable conditions
- **Specify required files and components** in "Files to Modify" section
- **Include testing requirements** where applicable with specific testing approaches
- **Provide time estimates** in consistent format: "2-3 hours" or "3-4 hours"

### Task Format Requirements

Each task MUST include these structured fields:

```markdown
#### {Task Number} {Task Name} (_Requirements: REQ-{ID}_)

**Estimated Time:** {X-Y} hours  
**Description:** {Implementation description}

**Acceptance Criteria:**

- {Criterion 1}
- {Criterion 2}

**Files to Modify:**

- `{file/path}`

**Testing Requirements:**

- {Testing specifications}
```

## Task Inclusion Rules

**MUST INCLUDE these task types (coding focus only)**:

- ✅ **Code Implementation**: Writing new components, modules, functions
- ✅ **Code Modification**: Updating existing files and functions
- ✅ **Unit Testing**: Creating tests for new functionality
- ✅ **Integration Testing**: Testing component interactions
- ✅ **Code Documentation**: Inline comments and code-level docs
- ✅ **Database Work**: Migrations, schema changes, data layer code
- ✅ **API Implementation**: Endpoint creation and modification

## Task Exclusion Rules

**MUST EXCLUDE these task types (non-coding activities)**:

- ❌ **Infrastructure Setup**: Server configuration, environment setup
- ❌ **Deployment Tasks**: CI/CD pipeline, production deployment
- ❌ **Documentation Creation**: User guides, technical documentation
- ❌ **External Dependencies**: Installing libraries, configuring tools
- ❌ **Environment Config**: Setting up development environments
- ❌ **Monitoring Setup**: Logging, metrics, alerting configuration

## Task Transformations

Transform non-coding tasks to coding equivalents:

- **"Deploy to production"** → "Create deployment configuration files"
- **"User acceptance testing"** → "Create automated test suite"
- **"Performance monitoring"** → "Add performance logging to code"
- **"Marketing tasks"** → "Create technical documentation"
- **"Environment setup"** → "Create configuration management code"

## Requirement Traceability

- **Each task MUST reference** specific requirements using format: `(_Requirements: REQ-{ID}_)`
- **Requirements can be referenced by multiple tasks** when implementation spans multiple components
- **All requirements MUST be covered** by at least one task
- **Traceability matrix MUST be included** showing requirement-to-task mapping

## Task Dependencies

- **Sequential Dependencies**: Tasks that must be completed before others can start
- **Parallel Execution**: Tasks that can be worked on simultaneously
- **Phase Organization**: Logical grouping of related tasks
- **Execution Order**: Clear guidance on task sequencing

These standards ensure implementation plans focus on actionable coding work with clear structure, requirement traceability, and systematic planning for execution.
