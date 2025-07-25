---
description: Implementation task template for structured task breakdown in spec-driven development
applyTo: ".spec-workflow/**/*"
---

# Implementation Task Template

Use this structured template when generating implementation tasks for specifications to ensure comprehensive coverage and clear execution paths.

## Task Document Structure

Follow this hierarchical structure for all implementation plans:

### Task Hierarchy Format

```markdown
- [ ] 1. Major Phase Name

  - Brief phase description
  - Key deliverables
  - _Requirements: X.X, Y.Y_

- [ ] 1.1 Specific Task Group

  - Concrete actionable item 1
  - Concrete actionable item 2
  - Concrete actionable item 3
  - _Requirements: X.X_

- [ ] 1.2 Another Task Group
  - Concrete actionable item 1
  - Concrete actionable item 2
  - _Requirements: Y.Y_
```

## Standard Phase Structure

### Phase 1: Project Setup and Core Structure

- Development environment setup
- Core directory structure
- Basic configuration files
- Development tooling

### Phase 2: Database and Model Layer

- Schema design and implementation
- Data validation
- Business logic implementation
- Database utilities

### Phase 3: API and Backend Services

- Authentication system
- Core API endpoints
- Business services
- API documentation

### Phase 4: Frontend Component Implementation

- UI component library setup
- Basic components
- Feature-specific components
- State management

### Phase 5: Integration and Testing

- Test suite implementation
- End-to-end testing
- Deployment configuration
- Monitoring setup

## Task Quality Guidelines

### Task Characteristics

- **Discrete**: Each task should be completable in 2-4 hours
- **Actionable**: Clear, concrete steps that can be executed
- **Testable**: Verifiable completion criteria
- **Independent**: Minimal dependencies on other incomplete tasks

### Task Content Requirements

- **Technology Specification**: Include specific technologies in [brackets]
- **Deliverables**: Clear output expectations
- **Requirements Mapping**: Link to specific requirements with _Requirements: X.X_
- **Acceptance Criteria**: What "done" looks like

### Dependencies and Ordering

- **Sequential Flow**: Tasks ordered by logical dependencies
- **Parallel Opportunities**: Identify tasks that can run concurrently
- **Milestone Markers**: Major completion points
- **Testing Integration**: Testing tasks for each major component

## Template Example

```markdown
# Implementation Plan

- [ ] 1. Project Setup and Core Structure

  - Establish development environment and basic project structure
  - Set up build tools, linting, and development workflows
  - _Requirements: 1.1, 1.2_

- [ ] 1.1 Frontend Setup

  - Create React/Vue/Next.js project with [TypeScript]
  - Configure build tools ([Vite/Webpack]) and development server
  - Set up linting ([ESLint]) and formatting ([Prettier])
  - Install and configure component library ([Tailwind/Chakra/Material-UI])
  - _Requirements: 1.1_

- [ ] 1.2 Backend Setup

  - Create backend project with [FastAPI/Express/Django]
  - Set up database connection with [Prisma/SQLAlchemy/Mongoose]
  - Configure environment variables and configuration management
  - Set up API documentation with [OpenAPI/Swagger]
  - _Requirements: 1.2_

- [ ] 2. Database and Model Layer Implementation

  - Design and implement data models with proper validation
  - Create database migrations and seed data
  - _Requirements: 2.1, 2.2, 2.3_

- [ ] 2.1 Database Schema Design

  - Define entity relationships and database schema
  - Create migration files using [Database Migration Tool]
  - Implement database connection utilities and pooling
  - Set up database seeding for development
  - _Requirements: 2.1_

- [ ] 2.2 Data Models and Validation

  - Implement data model classes with [ORM/ODM]
  - Add field validation and business rule enforcement
  - Create model utility functions (CRUD operations)
  - Implement comprehensive error handling for data operations
  - _Requirements: 2.2, 2.3_

- [ ] 3. Authentication and Authorization System

  - Implement user authentication with secure session management
  - Create role-based access control system
  - _Requirements: 3.1, 3.2_

- [ ] 3.1 User Authentication

  - Implement user registration with [JWT/Session] authentication
  - Create secure login/logout endpoints with [bcrypt] password hashing
  - Add password reset functionality with email verification
  - Implement account verification and activation
  - _Requirements: 3.1_

- [ ] 3.2 Authorization Middleware

  - Create role-based access control middleware
  - Implement route protection for authenticated endpoints
  - Add user permission checking utilities
  - Create admin panel access controls
  - _Requirements: 3.2_

- [ ] 4. Core API Endpoints Implementation

  - Implement CRUD operations for main entities
  - Add comprehensive input validation and error handling
  - _Requirements: 4.1, 4.2, 4.3_

- [ ] 4.1 Main Entity CRUD Operations

  - Implement GET /api/[resource] (list with pagination)
  - Implement POST /api/[resource] (create with validation)
  - Implement GET /api/[resource]/:id (get single resource)
  - Implement PUT /api/[resource]/:id (update with validation)
  - Implement DELETE /api/[resource]/:id (soft delete)
  - _Requirements: 4.1, 4.2_

- [ ] 4.2 API Error Handling and Documentation

  - Standardize error response formats across all endpoints
  - Add comprehensive input validation with detailed error messages
  - Generate API documentation with [OpenAPI/Swagger]
  - Implement API versioning strategy
  - _Requirements: 4.3_

- [ ] 5. Frontend Component Implementation

  - Create reusable UI components and implement feature-specific interfaces
  - Add form handling and state management
  - _Requirements: 5.1, 5.2, 5.3_

- [ ] 5.1 UI Component Library

  - Set up component library with [Design System]
  - Implement common components (Button, Input, Modal, Table, Form)
  - Create responsive layout components and navigation
  - Set up theming and dark mode support
  - _Requirements: 5.1_

- [ ] 5.2 Feature Components

  - Implement main feature pages and components
  - Add form handling with [React Hook Form/Formik] and validation
  - Implement state management with [Redux/Zustand/Context API]
  - Create data fetching and caching with [React Query/SWR]
  - _Requirements: 5.2, 5.3_

- [ ] 6. Testing Implementation

  - Create comprehensive test suite for all components
  - Set up automated testing pipeline
  - _Requirements: All requirements coverage_

- [ ] 6.1 Backend Testing

  - Implement unit tests for all service functions with [Jest/pytest]
  - Create API integration tests for all endpoints
  - Add database testing with test database setup/teardown
  - Implement load testing for critical endpoints
  - _Requirements: Test coverage for all backend requirements_

- [ ] 6.2 Frontend Testing

  - Create component unit tests with [Testing Library]
  - Implement user interaction tests for all major workflows
  - Add visual regression testing with [Chromatic/Percy]
  - Set up accessibility testing with [axe-core]
  - _Requirements: Test coverage for all frontend requirements_

- [ ] 6.3 End-to-End Testing

  - Implement E2E tests with [Playwright/Cypress] for critical user journeys
  - Set up test data management and cleanup
  - Create performance testing and monitoring
  - Add cross-browser testing configuration
  - _Requirements: Complete workflow validation_

- [ ] 7. Deployment and Monitoring

  - Set up production deployment pipeline
  - Configure monitoring and logging
  - _Requirements: Production readiness_

- [ ] 7.1 Deployment Configuration

  - Create [Docker] containers for frontend and backend
  - Set up CI/CD pipeline with [GitHub Actions/GitLab CI]
  - Configure production environment variables and secrets
  - Implement database migration strategy for production
  - _Requirements: Deployment requirements_

- [ ] 7.2 Monitoring and Observability
  - Set up application logging with [Winston/structlog]
  - Implement health check endpoints for all services
  - Add performance monitoring with [APM tool]
  - Configure error tracking and alerting
  - _Requirements: Operational requirements_
```

## Task Formatting Rules

### Numbering System

- **Major phases**: 1, 2, 3, 4, 5...
- **Task groups**: 1.1, 1.2, 2.1, 2.2...
- **Checkbox format**: `- [ ]` for incomplete, `- [x]` for complete

### Content Standards

- **Technology brackets**: [React], [FastAPI], [PostgreSQL]
- **Concrete actions**: Start with action verbs (Create, Implement, Set up, Add)
- **Specific deliverables**: Clear output expectations
- **Time estimates**: 2-4 hours per task group
- **Requirement mapping**: _Requirements: X.X, Y.Y_ at end of each task

### Dependencies and Flow

- **Logical ordering**: Dependencies flow naturally
- **Parallel work**: Identify independent tasks
- **Testing integration**: Tests for each major component
- **Milestone clarity**: Major completion points marked

## Integration with Spec Workflow

This template should be referenced in:

- Task generation phase (#spec-4-tasks.prompt.md)
- Progress tracking and status updates
- Implementation planning and execution

## Best Practices

- Break large features into discrete, manageable tasks
- Include testing as an integral part of each phase
- Specify exact technologies and tools to be used
- Map every task back to specific requirements
- Consider deployment and operational concerns from the start
- Design tasks for 2-4 hour completion windows
- Enable parallel work where possible
