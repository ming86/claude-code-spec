---
description: Generate implementation tasks for a specification
mode: agent
tools: ['search', 'codebase', 'editFiles']
---

# Implementation Tasks

Generate detailed implementation tasks for feature: **${input:feature:Enter feature name}**

## Approval Gate: Requirements & Design Check

**CRITICAL**: Tasks can only be generated after both requirements and design are approved.

### Approval Status Check

Check spec metadata: [spec.yaml](../../.spec-workflow/specs/${input:feature}/spec.yaml)

**STOP HERE** if spec.yaml shows:

```yaml
approvals:
  requirements:
    approved: false # Must be true
  design:
    approved: false # Must be true
```

**Required Actions for Full Approval**:

### If Requirements Not Approved:

1. **Review requirements.md** - Read through the generated requirements thoroughly
2. **Edit if needed** - Make any necessary changes directly in the requirements.md file
3. **Manual approval required** - Update spec.yaml to set `requirements.approved: true`

### If Design Not Approved:

1. **Review design.md** - Read through the generated design thoroughly
2. **Edit if needed** - Make any necessary changes directly in the design.md file
3. **Manual approval required** - Update spec.yaml to set `design.approved: true`
4. **Reasoning**: Human review ensures technical design accuracy before task breakdown

**Example full approval in spec.yaml**:

```yaml
approvals:
  requirements:
    generated: true
    approved: true # ← Human reviewed and approved
  design:
    generated: true
    approved: true # ← Human reviewed and approved
phase: "design-approved"
```

**Only proceed to task generation after both requirements and design are explicitly approved by human review.**

## Context Analysis

### Complete Spec Context (APPROVED)

- Requirements: [requirements.md](../../.spec-workflow/specs/${input:feature}/requirements.md)
- Design: [design.md](../../.spec-workflow/specs/${input:feature}/design.md)
- Current tasks: [tasks.md](../../.spec-workflow/specs/${input:feature}/tasks.md)
- Spec metadata: [spec.yaml](../../.spec-workflow/specs/${input:feature}/spec.yaml)

### Steering Context

Reference steering documents if available:

- Architecture patterns: [structure.md](../../.spec-workflow/steering/structure.md)
- Development practices: [tech.md](../../.spec-workflow/steering/tech.md)
- Product constraints: [product.md](../../.spec-workflow/steering/product.md)

## Task: Generate Implementation Plan

**Prerequisites Verified**: Both requirements and design are approved and ready for task breakdown.

Create comprehensive implementation plan in the language specified in spec.yaml:

### 1. Tasks Document Structure

Create tasks.md in the language specified in spec.yaml (check language field):

```markdown
# Implementation Plan

- [ ] 1. Project Setup and Core Structure

  - Create frontend (React/Vue/Next.js) and backend (FastAPI/Express) directory structure
  - Define TypeScript types and core data model interfaces
  - Set up development environment files (package.json, requirements.txt, docker-compose.yml)
  - _Requirements: 1.1, 1.2_

- [ ] 2. Database and Model Layer Implementation
- [ ] 2.1 Database Schema Design and Implementation

  - Define schemas using [ORM/Database] (Prisma/SQLAlchemy/Mongoose)
  - Create and run migration files
  - Implement database connection utilities
  - _Requirements: 2.1, 2.2_

- [ ] 2.2 Data Validation and Business Logic

  - Implement model validation functions
  - Implement and test business rules
  - Standardize error handling across models
  - _Requirements: 2.3_

- [ ] 3. API and Backend Services Implementation
- [ ] 3.1 Authentication and Authorization System

  - Implement JWT/session authentication with [Auth Library]
  - Create user registration and login endpoints
  - Implement access control middleware and route protection
  - _Requirements: 3.1, 3.2_

- [ ] 3.2 Core API Endpoints Implementation

  - Implement CRUD operations for main entities
  - Add input validation and sanitization
  - Create API documentation with OpenAPI/Swagger
  - _Requirements: 3.3, 3.4_

- [ ] 4. Frontend Component Implementation
- [ ] 4.1 Basic UI Component Creation

  - Select and configure component library ([Chakra UI/Material-UI/Tailwind])
  - Implement common components (Button, Input, Modal, Table)
  - Set up responsive design system and theme
  - _Requirements: 4.1, 4.2_

- [ ] 4.2 Feature-Specific Components

  - Implement main feature components based on requirements
  - Add form handling with validation ([Formik/React Hook Form])
  - Implement state management ([Redux/Zustand/Context])
  - _Requirements: 4.3, 4.4_

- [ ] 5. Integration and Testing
- [ ] 5.1 Test Suite Implementation

  - Create unit tests for backend services (Jest/pytest)
  - Implement API integration tests
  - Set up frontend component tests ([Testing Library])
  - _Requirements: All requirements test coverage_

- [ ] 5.2 End-to-End Testing and Deployment
  - Implement E2E tests ([Playwright/Cypress])
  - Set up CI/CD pipeline configuration
  - Configure production deployment and monitoring
  - _Requirements: 5.1, 5.2_
```

**Key Format Rules**:

- Hierarchical numbering: Major phases (1, 2, 3) and sub-tasks (1.1, 1.2)
- Each task contains 2-4 concrete, actionable items
- Specify technologies in brackets: [React], [FastAPI], [Prisma]
- End with requirement mapping: _Requirements: X.X, Y.Y_
- Tasks should be completable in 2-4 hours each
- Include testing tasks for each major component

### 2. Task Quality Guidelines

- **Hierarchical Structure**: Group related tasks into phases
- **Discrete Tasks**: Each task should be completable in 2-4 hours
- **Clear Acceptance Criteria**: Define what "done" means
- **Requirements Mapping**: Link tasks to specific requirements
- **Dependency Management**: Order tasks by dependencies
- **Testable Outcomes**: Each task should have verifiable results

### 3. Task Categories

Include tasks for:

- **Data Models**: Database schema and model creation
- **API Endpoints**: Backend service implementation
- **UI Components**: Frontend component development
- **Integration**: Service integration and workflow
- **Testing**: Unit, integration, and E2E tests
- **Documentation**: Code documentation and user guides

### 4. Requirements Mapping

For each task, reference the specific requirements from requirements.md:

- Map to user stories (Requirement 1, Requirement 2, etc.)
- Include acceptance criteria references
- Ensure full requirements coverage

### 5. Progress Tracking

Include progress tracking section:

```markdown
## Progress Status

- Created: [timestamp]
- Status: Ready for implementation
- Total tasks: [count]
- Completed: 0
- Remaining: [count]
```

### 6. Document Generation Only

Generate the tasks document content ONLY. Do not include any review or approval instructions in the actual document file.

### 7. Update Metadata

Update spec.yaml with:

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

## Refinement Options

What would you like me to refine about this implementation plan?

- **Adjust phase breakdown**: Modify task grouping or sequencing?
- **Change task granularity**: Larger or smaller task chunks?
- **Update technology specifications**: Different tools or frameworks in [brackets]?
- **Modify time estimates**: Adjust 2-4 hour task sizing?
- **Enhance testing approach**: More comprehensive test coverage?
- **Update deployment strategy**: Different deployment or monitoring approach?
- **Proceed if satisfied** with implementation plan?

I can iterate on the implementation plan in our conversation until you're satisfied.

## Human Review Process

After generation, the tasks must be reviewed and approved before starting implementation:

1. **Human reviews** the generated tasks.md
2. **Manual edits** can be made directly to the file if needed
3. **Approval** is granted by manually updating spec.yaml:
   ```yaml
   approvals:
     requirements:
       generated: true
       approved: true
     design:
       generated: true
       approved: true
     tasks:
       generated: true
       approved: true
   phase: "ready-for-implementation"
   ready_for_implementation: true
   ```
4. **Only after approval** can implementation begin

## Instructions

1. **Check spec.yaml for language** - Use the language specified in the metadata
2. **Analyze requirements and design** to understand full scope
3. **Create hierarchical task structure** with clear phases
4. **Define discrete, actionable tasks** with acceptance criteria
5. **Map all tasks to requirements** to ensure coverage
6. **Order tasks by dependencies** for logical implementation flow
7. **Include testing and documentation** tasks
8. **Update tracking metadata** upon completion

Generate tasks that provide clear roadmap for implementation.
