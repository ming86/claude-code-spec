---
description: Create comprehensive technical design with optional research and architecture analysis
mode: agent
tools: ['codebase', 'usages', 'problems', 'fetch', 'findTestFiles', 'editFiles', 'search', 'get_syntax_docs', 'mermaid-diagram-validator']
---

# Technical Design Generation

Generate an appropriate technical design for feature: **${input:feature:Enter feature name}** that bridges approved requirements with implementable architecture solutions.

# Execution Steps

## Step 1: Prerequisites & Context Analysis

### ⚠️ CRITICAL: Requirements Approval Check

**MUST verify requirements approval before proceeding:**

Check `.spec-workflow/specs/${input:feature}/spec.yaml`:

```yaml
approvals:
  requirements:
    approved: true # Must be true to proceed
```

**If requirements not approved**: Stop immediately with message: "Requirements must be approved in spec.yaml before design generation can proceed. Please complete requirements review and approval first."

### Requirements Analysis

Read and analyze `.spec-workflow/specs/${input:feature}/requirements.md`:

- **Functional Requirements**: Document all user-facing functionality and business logic
- **Non-functional Requirements**: Identify performance, security, scalability, and usability constraints
- **Integration Requirements**: Note dependencies on existing systems and external services
- **Acceptance Criteria**: Review for design implications and validation requirements

### Codebase Architecture Analysis

**MUST USE SEARCH AND CODEBASE TOOLS** systematically:

- Use `search` tool to locate relevant files and project structure
- Use `codebase` semantic search tool with specific queries to find:
  - **Current architecture patterns** and structures
  - **Existing components** that can be reused or extended
  - **Data models** and database schemas
  - **API patterns** and conventions
  - **Testing approaches** and frameworks
  - **Error handling** patterns
  - **Authentication and authorization mechanisms**
  - **Performance optimization techniques currently used**

### Steering Context

Reference steering documents if available:

- **Architecture constraints**: `.spec-workflow/steering/structure.md`
- **Technology stack**: `.spec-workflow/steering/tech.md`
- **Product context**: `.spec-workflow/steering/product.md`
- **Custom domain-specific guidelines**: Check for additional steering files in `.spec-workflow/steering/`

## Step 2: Research Integration (When Required)

**MUST conduct research when designing complex or unfamiliar features**:

### When to Research (Mandatory for these scenarios)

- **New technology integration**: Unfamiliar frameworks, libraries, or architectural patterns
- **Complex business logic requirements**: Domain-specific algorithms or workflows
- **Performance-critical features**: High-throughput, low-latency, or resource-intensive operations
- **Security-sensitive components**: Authentication, authorization, data protection, or compliance features
- **Industry-specific functionality**: Domain expertise requiring external validation

### Research Process (Systematic Approach)

1. **Use fetch tool** to research technical approaches and industry standards
2. **Search internal codebase** for similar implementations and patterns
3. **Investigate existing solutions** and frameworks in the ecosystem
4. **Analyze pros/cons** of different approaches with clear rationale
5. **Document decision criteria** used for technology and approach selection

### Research Documentation

When research is conducted, include:

```markdown
## Research Findings

### Technical Approaches

- [Framework/Library](URL) - Key capabilities and integration considerations
- [Design Pattern](URL) - Implementation approach and benefits

### Best Practices

- [Industry Standard](URL) - Relevant guidelines and recommendations
- [Performance Study](URL) - Optimization techniques and benchmarks
```

## Step 3: Technical Design Generation

**⚠️ CRITICAL: STRICT SCOPE CONTROL ⚠️**

- **MUST address ONLY approved requirements** - feature expansion creates maintenance burden
- **MUST trace every design element** back to approved requirement
- **MUST NOT add new functionality** beyond what was approved
- **Research enhances implementation** of existing requirements only

Generate comprehensive technical design following this structure:

### 1. Design Overview

#### System Architecture

- High-level component architecture
- Integration with existing system
- Data flow and component interactions
- Technology choices and rationale

#### Component Breakdown

- Core components and their responsibilities
- Reusable components from existing codebase
- New components requiring development
- Component interaction patterns

### 2. Detailed Component Design

#### Data Models

```markdown
### Data Models

#### {ModelName}

**Purpose**: Brief description of the model's role

**Structure** (adapt to project language):
```

{ModelName} Data Structure:

- field1: [type] - Description
- field2: [type] - Description

```

**Relationships**: Connections to other models
**Validation**: Data validation requirements
```

#### API Specifications

```markdown
### API Endpoints

#### {Endpoint Group}

**Base URL**: `/api/{resource}`

##### GET /{resource}

- **Purpose**: Retrieve resource collection
- **Parameters**: Query parameters and filters
- **Response**: Success and error response formats
- **Security**: Authentication and authorization requirements

##### POST /{resource}

- **Purpose**: Create new resource
- **Request Body**: Required data structure
- **Validation**: Input validation rules
- **Response**: Creation success/error responses
```

#### Database Design

- Schema modifications or additions
- Index requirements for performance
- Migration strategy for existing data
- Backup and recovery considerations

### 3. Integration Design

#### External System Integration

- Third-party APIs and services
- Authentication and authorization flow
- Error handling for external dependencies
- Retry logic and circuit breaker patterns

#### Internal System Integration

- Integration points with existing features
- Shared component modifications
- Data synchronization requirements
- Event handling and notifications

### 4. Testing Strategy

#### Testing Approach

```markdown
### Testing Strategy

#### Unit Testing

- **Scope**: Individual component testing
- **Framework**: {Detected testing framework from project analysis}
- **Coverage**: Minimum coverage requirements
- **Mock Strategy**: External dependency mocking

#### Integration Testing

- **Scope**: Component interaction testing
- **Database**: Test database setup and cleanup
- **External Services**: Mock service configuration
- **API Testing**: Endpoint validation and error handling

#### End-to-End Testing

- **User Scenarios**: Critical user journey testing
- **Browser Testing**: Cross-browser compatibility
- **Performance Testing**: Load and stress testing
```

### 5. Security Considerations

#### Authentication and Authorization

- User authentication flow
- Permission and role-based access
- Token management and refresh
- Session security measures

#### Data Protection

- Sensitive data handling
- Encryption requirements
- Input validation and sanitization
- SQL injection and XSS prevention

#### Security Testing

- Security vulnerability assessment
- Penetration testing requirements
- Code security review guidelines
- Compliance requirements

### 6. Performance Considerations

#### Performance Requirements

- Response time expectations
- Throughput requirements
- Resource usage constraints
- Scalability considerations

#### Optimization Strategy

- Database query optimization
- Caching strategy and implementation
- Code optimization techniques
- Monitoring and alerting setup

### 7. Error Handling and Logging

#### Error Handling Strategy

````markdown
### Error Handling

#### Error Categories

- **Validation Errors**: User input validation failures
- **Business Logic Errors**: Domain rule violations
- **System Errors**: Infrastructure and dependency failures
- **Integration Errors**: External service communication failures

#### Error Response Format

```json
{
  "error": {
    "code": "ERROR_CODE",
    "message": "User-friendly message",
    "details": "Technical details for debugging"
  }
}
```
````

````

#### Logging Strategy

- Log levels and categorization
- Structured logging format
- Performance monitoring
- Security event logging

### 8. Deployment and Infrastructure

#### Deployment Strategy

- Environment configuration
- Database migration process
- Feature flag implementation
- Rollback procedures

#### Infrastructure Requirements

- Server resource requirements
- Database performance needs
- Third-party service dependencies
- Monitoring and alerting setup

## Visual Design Documentation

### Architecture Diagrams

Use mermaid diagrams to visualize:

#### System Architecture

```mermaid
graph TB
    subgraph "Frontend"
        UI[User Interface]
        API_CLIENT[API Client]
    end

    subgraph "Backend"
        API[API Layer]
        BL[Business Logic]
        DATA[Data Layer]
    end

    subgraph "External"
        DB[(Database)]
        EXT[External Services]
    end

    UI --> API_CLIENT
    API_CLIENT --> API
    API --> BL
    BL --> DATA
    DATA --> DB
    BL --> EXT
````

#### Data Flow Diagram

```mermaid
sequenceDiagram
    participant U as User
    participant F as Frontend
    participant A as API
    participant D as Database

    U->>F: User Action
    F->>A: API Request
    A->>D: Data Query
    D-->>A: Data Response
    A-->>F: API Response
    F-->>U: UI Update
```

## Step 4: Implementation Guidelines & Quality Validation

### Development Approach

- Implementation phases and milestones
- Code organization and structure
- Coding standards and conventions
- Code review requirements

### Quality Assurance

- Definition of done criteria
- Acceptance testing procedures
- Performance benchmarks
- Security validation checklist

## Step 5: Document Generation & Metadata Updates

### 1. Design File Creation

Update `.spec-workflow/specs/${input:feature}/design.md` with:

- Complete technical design following the structure above
- All component specifications and API designs
- Comprehensive testing strategy
- Security and performance considerations

### 2. Spec Metadata Update

Update `.spec-workflow/specs/${input:feature}/spec.yaml`:

```yaml
updated_at: "{current_timestamp}"
phase: "design-generated"
approvals:
  design:
    generated: true
    approved: false # Requires human approval
```

### 3. Quality Review Checklist

Before completion, verify:

- [ ] All approved requirements addressed in design with clear traceability
- [ ] **SCOPE CONTROL**: Design addresses only approved requirements - no additional functional requirements added
- [ ] Architecture aligns with existing system
- [ ] API specifications are complete
- [ ] Testing strategy is appropriate for all design components
- [ ] Security considerations addressed
- [ ] Performance requirements included
- [ ] Visual diagrams provided

## Defensive Patterns

### Error Handling

- **If requirements not approved**: Stop immediately with clear message: "Requirements must be approved in spec.yaml before design generation can proceed. Please complete requirements review and approval first."
- **If codebase analysis reveals architectural conflicts**: Document the conflicts clearly and provide recommended resolution approaches with pros/cons
- **If research yields multiple conflicting approaches**: Present alternatives in a structured comparison with recommendation based on project constraints
- **If design becomes overly complex**: Break into implementation phases and document the decomposition rationale
- **If required tools are not accessible**: Clearly explain what information is needed and suggest alternative approaches
- **If scope expansion is tempting during research**: Focus research on implementation approaches for approved requirements only - document additional feature ideas for future consideration but do not include in current design

### Quality Validation

- **If any design section is incomplete**: Return to that section and complete it before proceeding
- **If architectural decisions lack justification**: Add clear rationale based on requirements and constraints
- **If integration points are unclear**: Clarify dependencies and communication patterns

## Success Criteria

Design generation is complete when:

- [ ] All approved requirements are addressed in design with clear traceability
- [ ] **SCOPE CONTROL**: Design addresses only approved requirements - no additional functional requirements added
- [ ] Architecture aligns with existing system patterns
- [ ] API specifications are complete and consistent
- [ ] Testing strategy covers all components
- [ ] Security considerations are thoroughly addressed
- [ ] Performance requirements are included with optimization strategies
- [ ] Visual diagrams clearly represent the architecture
- [ ] Implementation guidelines provide clear direction
- [ ] All files are updated with generated content

Generate a comprehensive technical design that provides clear implementation guidance while maintaining strict scope control and alignment with existing system architecture and industry best practices.
