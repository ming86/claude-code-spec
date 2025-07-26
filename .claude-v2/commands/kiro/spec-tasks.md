---
description: Generate multi-task implementation plan with EARS requirement traceability
allowed-tools: Bash, Read, Write, Edit, Update, MultiEdit, Task
---

# Enhanced Implementation Tasks

Generate detailed multi-task implementation plan for feature: **$ARGUMENTS**

## Approval Gate: Requirements & Design Check

**CRITICAL**: Tasks can only be generated after both EARS requirements and research-informed design are approved.

### Approval Status Check

- Spec metadata: @.kiro/specs/$ARGUMENTS/spec.json

**STOP HERE** if spec.json shows:

```json
"approvals": {
  "requirements": {
    "approved": false  // Must be true
  },
  "design": {
    "approved": false  // Must be true
  }
}
```

**Required Actions for Full Approval**:

### If EARS Requirements Not Approved

1. **Review requirements.md** - Ensure EARS format compliance and completeness
2. **Edit if needed** - Make any necessary changes directly in requirements.md file
3. **Manual approval required** - Update spec.json to set `"requirements": {"approved": true}`

### If Research-Informed Design Not Approved

1. **Review design.md** - Read through research integration and technical design thoroughly
2. **Edit if needed** - Make any necessary changes directly in design.md file
3. **Manual approval required** - Update spec.json to set `"design": {"approved": true}`
4. **Reasoning**: Human review ensures technical design accuracy and research integration before task breakdown

**Only proceed to task generation after both requirements and design are explicitly approved by human review.**

## Context Analysis

### Complete Spec Context (APPROVED)

- EARS Requirements: @.kiro/specs/$ARGUMENTS/requirements.md
- Research-Informed Design: @.kiro/specs/$ARGUMENTS/design.md
- Current tasks: @.kiro/specs/$ARGUMENTS/tasks.md
- Spec metadata: @.kiro/specs/$ARGUMENTS/spec.json

### Steering Context

- Architecture patterns: @.kiro/steering/structure.md
- Development practices: @.kiro/steering/tech.md
- Product constraints: @.kiro/steering/product.md

### EARS Requirements Analysis

Extract key implementation requirements from EARS format:
!`grep -n "WHEN.*THEN\|GIVEN.*WHEN.*THEN" .kiro/specs/$ARGUMENTS/requirements.md | head -10`

## Task: Generate Multi-Task Implementation Plan

**Prerequisites Verified**: Both EARS requirements and research-informed design are approved and ready for task breakdown.

Create comprehensive implementation plan in the language specified in spec.json:

### 1. Enhanced Tasks Document Structure

Create tasks.md in the language specified in spec.json:

```markdown
# Implementation Plan

## EARS Requirements Summary
Brief summary of key EARS requirements for reference:
- **REQ-1**: [WHEN condition THEN outcome summary]
- **REQ-2**: [WHEN condition THEN outcome summary]  
- **REQ-3**: [WHEN condition THEN outcome summary]

## Task Structure Overview
Tasks are organized hierarchically with clear EARS requirement traceability:
- **Major Phase** (1, 2, 3): High-level implementation phases
- **Task Group** (1.1, 1.2): Related tasks within a phase
- **Sub-task** (1.1.1, 1.1.2): Specific implementation steps

## Implementation Tasks

### Phase 1: Core Infrastructure and Data Layer
_Foundation for EARS requirement implementation_

- [ ] **1.1 Project Setup and Environment**
  - [ ] 1.1.1 Create frontend and backend directory structure
    - Set up [React/Vue/Next.js] frontend with TypeScript configuration
    - Initialize [FastAPI/Express/Django] backend with proper structure
    - Configure development environment (package.json, requirements.txt, etc.)
    - **EARS Mapping**: Foundation for all WHEN/THEN behaviors
    - **Acceptance Criteria**: Project structure matches design specification
    - **Estimated Time**: 2-3 hours

  - [ ] 1.1.2 Configure development tooling and build system
    - Set up linting, formatting, and type checking
    - Configure testing framework ([Jest/pytest] + [Testing Library])
    - Set up CI/CD pipeline configuration files
    - **EARS Mapping**: Quality foundation for WHEN/THEN validation
    - **Acceptance Criteria**: All tooling passes without errors
    - **Estimated Time**: 2-3 hours

- [ ] **1.2 Data Models and Database Implementation**
  - [ ] 1.2.1 Database schema design and creation
    - Implement database models using [ORM/Database] (Prisma/SQLAlchemy/Mongoose)
    - Create and execute migration files for initial schema
    - Set up database connection utilities and configuration
    - **EARS Mapping**: REQ-1, REQ-2 (data storage for WHEN conditions)
    - **Acceptance Criteria**: All models created, migrations successful
    - **Estimated Time**: 3-4 hours

  - [ ] 1.2.2 Data validation and business logic implementation
    - Implement model validation functions based on EARS IF/THEN rules
    - Create business logic functions for WHEN/THEN requirement processing
    - Implement standardized error handling for IF condition failures
    - **EARS Mapping**: All IF/THEN validation requirements
    - **Acceptance Criteria**: All EARS validation rules implemented and tested
    - **Estimated Time**: 3-4 hours

### Phase 2: API Layer and Backend Services
_WHEN/THEN behavior implementation_

- [ ] **2.1 Authentication and Authorization System**
  - [ ] 2.1.1 Core authentication implementation
    - Implement [JWT/OAuth/Auth0] authentication system
    - Create user registration and login endpoints
    - Set up password hashing and token management
    - **EARS Mapping**: REQ-3 (WHEN user authentication THEN access granted)
    - **Acceptance Criteria**: Users can register, login, and receive valid tokens
    - **Estimated Time**: 4-5 hours

  - [ ] 2.1.2 Authorization middleware and route protection
    - Implement access control middleware for protected routes
    - Create role-based permission system (if required by EARS)
    - Add session management and token refresh logic
    - **EARS Mapping**: REQ-3 (GIVEN user context WHEN accessing resources THEN appropriate access)
    - **Acceptance Criteria**: All protected routes properly secured, roles enforced
    - **Estimated Time**: 3-4 hours

- [ ] **2.2 Core API Endpoints Implementation**
  - [ ] 2.2.1 Primary CRUD operations
    - Implement main entity CRUD endpoints based on EARS requirements
    - Add comprehensive input validation and sanitization
    - Create standardized API response format
    - **EARS Mapping**: REQ-1, REQ-2 (core WHEN/THEN operations)
    - **Acceptance Criteria**: All CRUD operations work correctly, validation enforced
    - **Estimated Time**: 4-6 hours

  - [ ] 2.2.2 Business logic endpoints and error handling
    - Implement complex business logic endpoints for multi-step WHEN/THEN flows
    - Add comprehensive error handling for all IF/THEN scenarios
    - Create API documentation with OpenAPI/Swagger
    - **EARS Mapping**: Complex WHEN/THEN business requirements
    - **Acceptance Criteria**: All business logic implemented, errors handled gracefully
    - **Estimated Time**: 4-5 hours

### Phase 3: Frontend Components and User Interface
_User interaction for WHEN conditions and THEN outcomes_

- [ ] **3.1 UI Foundation and Component System**
  - [ ] 3.1.1 Design system and base components
    - Set up component library ([Chakra UI/Material-UI/Tailwind])
    - Implement base components (Button, Input, Modal, Table, etc.)
    - Configure responsive design system and theme
    - **EARS Mapping**: Foundation for all WHEN user interactions
    - **Acceptance Criteria**: Design system implemented, base components functional
    - **Estimated Time**: 3-4 hours

  - [ ] 3.1.2 State management and API integration
    - Implement global state management ([Redux/Zustand/Context])
    - Set up API client with authentication integration
    - Create error handling and loading state management
    - **EARS Mapping**: State for WHEN conditions and THEN outcomes
    - **Acceptance Criteria**: State management working, API integration complete
    - **Estimated Time**: 3-4 hours

- [ ] **3.2 Feature-Specific Component Implementation**
  - [ ] 3.2.1 Core feature components
    - Implement main feature components based on EARS WHEN/THEN requirements
    - Add form handling with validation ([Formik/React Hook Form])
    - Create user feedback for THEN outcomes (success/error states)
    - **EARS Mapping**: REQ-1, REQ-2 (user interface for WHEN actions and THEN feedback)
    - **Acceptance Criteria**: All feature components functional, forms validate correctly
    - **Estimated Time**: 5-6 hours

  - [ ] 3.2.2 Advanced interactions and user flows
    - Implement complex user workflows for multi-step WHEN/THEN scenarios
    - Add real-time updates and notifications for THEN outcomes
    - Create responsive layouts for mobile and desktop
    - **EARS Mapping**: Complex WHEN/THEN user interaction flows
    - **Acceptance Criteria**: All user flows complete, responsive design works
    - **Estimated Time**: 4-5 hours

### Phase 4: Integration, Testing, and Validation
_EARS requirement validation and system integration_

- [ ] **4.1 Comprehensive Testing Implementation**
  - [ ] 4.1.1 Unit and integration testing
    - Create unit tests for all business logic functions (Jest/pytest)
    - Implement API integration tests for all endpoints
    - Add component tests for React components ([Testing Library])
    - **EARS Mapping**: All WHEN/THEN behaviors validated through tests
    - **Acceptance Criteria**: 90%+ test coverage, all EARS requirements tested
    - **Estimated Time**: 6-8 hours

  - [ ] 4.1.2 End-to-end testing and EARS validation
    - Implement E2E tests for complete WHEN/THEN user journeys ([Playwright/Cypress])
    - Create specific test cases for each EARS requirement
    - Add performance testing for WHEN/THEN response time requirements
    - **EARS Mapping**: Complete EARS requirement validation
    - **Acceptance Criteria**: All EARS requirements pass E2E validation
    - **Estimated Time**: 4-6 hours

- [ ] **4.2 System Integration and Deployment Preparation**
  - [ ] 4.2.1 Integration testing and error handling validation
    - Test all system integrations (database, external APIs, etc.)
    - Validate all IF/THEN error handling scenarios from EARS requirements
    - Performance testing for concurrent WHEN conditions
    - **EARS Mapping**: System-level WHEN/THEN behavior validation
    - **Acceptance Criteria**: All integrations work, error scenarios handled
    - **Estimated Time**: 3-4 hours

  - [ ] 4.2.2 Documentation and deployment configuration
    - Create API documentation and user guides
    - Set up production deployment configuration (Docker/Vercel/AWS)
    - Configure monitoring and logging for WHEN/THEN event tracking
    - **EARS Mapping**: Operational support for WHEN/THEN requirement monitoring
    - **Acceptance Criteria**: Documentation complete, deployment ready
    - **Estimated Time**: 3-4 hours

## Multi-Task Execution Support

### Task Validation Framework
Each task includes validation criteria for automated checking:
- **Technical Validation**: Code compiles, tests pass, no linting errors
- **EARS Validation**: Requirement fulfillment verification
- **Integration Validation**: Component integration with existing system

### Progress Tracking Integration
Compatible with enhanced `/execute-tasks` command:
- **Checkbox Status**: Track completion in tasks.md
- **Validation Status**: Pass/fail status for each task
- **EARS Traceability**: Requirement fulfillment tracking

### Task Dependencies
Clear dependency mapping for multi-task execution:
- **Sequential**: Tasks that must complete before others can start
- **Parallel**: Tasks that can be executed simultaneously
- **Conditional**: Tasks dependent on validation outcomes

## Progress Summary

### Implementation Statistics
- **Total Tasks**: [Calculated count]
- **Estimated Total Time**: [Sum of individual estimates]
- **EARS Requirements Covered**: [Count of REQ mappings]
- **Validation Points**: [Number of acceptance criteria]

### Completion Tracking
- **Created**: [Current timestamp]
- **Status**: Ready for multi-task implementation
- **Next Action**: Human review and approval, then execute with `/execute-tasks`
```

### 2. Enhanced Task Quality Guidelines

#### EARS Requirement Traceability

- **Explicit Mapping**: Every task must reference specific EARS requirements
- **WHEN/THEN Coverage**: Tasks address both trigger conditions and expected outcomes
- **IF/THEN Integration**: Error handling tasks for exception scenarios
- **Validation Alignment**: Task acceptance criteria match EARS acceptance criteria

#### Multi-Task Structure

- **Hierarchical Organization**: Major phases → Task groups → Sub-tasks
- **Clear Dependencies**: Explicit ordering based on technical and logical dependencies
- **Parallel Execution Support**: Identify tasks that can run simultaneously
- **Validation Checkpoints**: Built-in validation after task groups

#### Task Granularity Standards

- **2-4 Hour Limit**: Each sub-task completable in single focused session
- **Single Responsibility**: Each task has one clear, testable outcome
- **Acceptance Criteria**: Specific, measurable completion criteria
- **Technical Scope**: Focus on coding, testing, and technical documentation

### 3. Task Categories and Exclusions

#### INCLUDED Task Types

- **Code Development**: Writing, modifying, testing application code
- **Technical Configuration**: Setting up development and deployment environments
- **Database Work**: Schema design, migrations, data layer implementation
- **API Development**: Endpoint creation, integration, documentation
- **UI Implementation**: Component development, styling, user experience
- **Testing**: Unit, integration, end-to-end, and performance testing
- **Technical Documentation**: Code documentation, API docs, setup guides

#### EXCLUDED Task Types (Transform as shown)

- **"Deploy to production"** → **"Create deployment configuration files"**
- **"User acceptance testing"** → **"Create automated test suite covering user scenarios"**
- **"Performance monitoring setup"** → **"Add performance logging and metrics to code"**
- **"Business planning"** → **"Create technical requirements documentation"**
- **"Marketing content"** → **"Create technical user guides and documentation"**

### 4. EARS Integration Validation

#### Requirement Coverage Verification

!`grep -c "EARS Mapping" .kiro/specs/$ARGUMENTS/tasks.md || echo "⚠️  Add EARS requirement mapping to all tasks"`
!`grep -c "REQ-" .kiro/specs/$ARGUMENTS/tasks.md || echo "⚠️  Reference specific requirements in task mapping"`

#### Task Structure Validation

!`grep -c "Acceptance Criteria" .kiro/specs/$ARGUMENTS/tasks.md || echo "⚠️  Add acceptance criteria to all tasks"`
!`grep -c "Estimated Time" .kiro/specs/$ARGUMENTS/tasks.md || echo "⚠️  Add time estimates to all tasks"`

### 5. Update Metadata

Update spec.json with enhanced tracking:

```json
{
  "phase": "tasks-generated",
  "methodology": "EARS-driven",
  "progress": {
    "requirements": 100,
    "design": 100, 
    "tasks": 100
  },
  "approvals": {
    "requirements": {
      "generated": true,
      "approved": true,
      "methodology": "EARS"
    },
    "design": {
      "generated": true,
      "approved": true,
      "research_integrated": true
    },
    "tasks": {
      "generated": true,
      "approved": false,
      "multi_task_ready": true,
      "ears_traceable": true
    }
  },
  "task_summary": {
    "total_tasks": "[count]",
    "estimated_hours": "[total estimate]",
    "ears_requirements_covered": "[REQ count]",
    "parallel_tasks_identified": true
  },
  "updated_at": "current_timestamp"
}
```

---

## REVIEW AND APPROVAL PROCESS (Not included in document)

### Human Review Required

After generating tasks.md, inform the user:

**NEXT STEP**: Human review required before starting multi-task implementation.

### Enhanced Review Checklist

- [ ] Tasks are properly sized (2-4 hours each) for focused execution
- [ ] All EARS requirements are covered by specific tasks with clear mapping
- [ ] Task dependencies are correctly identified and ordered
- [ ] Technology choices match the research-informed design
- [ ] Testing tasks comprehensively cover EARS requirements
- [ ] Acceptance criteria are specific and measurable
- [ ] Multi-task execution structure is clear and logical
- [ ] Task exclusions are properly transformed to technical tasks

### To Approve

After reviewing, update `.kiro/specs/$ARGUMENTS/spec.json`:

```json
{
  "approvals": {
    "requirements": {
      "generated": true,
      "approved": true,
      "methodology": "EARS"
    },
    "design": {
      "generated": true,
      "approved": true,
      "research_integrated": true
    },
    "tasks": {
      "generated": true,
      "approved": true,
      "multi_task_ready": true,
      "ears_traceable": true
    }
  },
  "phase": "ready-for-implementation",
  "ready_for_implementation": true,
  "multi_task_execution": true
}
```

**After approval, you can start implementation with `/execute-tasks $ARGUMENTS` for multi-task execution**

## Instructions

1. **Verify dual approval** - Ensure both EARS requirements and research-informed design are approved
2. **Map all EARS requirements** - Create explicit traceability from requirements to tasks
3. **Structure for multi-task execution** - Organize tasks with clear dependencies and parallelization opportunities
4. **Focus on technical implementation** - Exclude non-coding tasks, transform as needed
5. **Define validation criteria** - Set up tasks for automated validation with Task tool
6. **Estimate realistically** - Provide accurate time estimates for planning
7. **Enable parallel execution** - Identify tasks that can run simultaneously
8. **Prepare for automation** - Structure tasks for automated execution with `/execute-tasks`

Generate multi-task implementation plan with comprehensive EARS requirement traceability and validation framework.
