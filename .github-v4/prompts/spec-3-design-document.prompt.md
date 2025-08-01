---
description: Create comprehensive technical design with optional research and architecture analysis
mode: agent
tools: ['codebase', 'search', 'fetch', 'editFiles']
---

# Technical Design Generation

Create comprehensive technical design for feature: **${input:feature:Enter feature name}**

## Standards and Guidelines

**Design Standards**: [Architecture & Documentation Guidelines](../instructions/spec-design.instructions.md)  
**Workflow Principles**: [Core Workflow Standards](../instructions/spec-workflow-general.instructions.md)

## Prerequisites Validation

**CRITICAL**: Design can only be generated after requirements are approved.

### Approval Status Check

Verify in `.spec-workflow/specs/${input:feature}/spec.yaml`:

```yaml
approvals:
  requirements:
    approved: true # Must be true to proceed
```

**If requirements not approved**: Complete requirements review and approval first.

## Context Analysis

### Requirements Analysis

Read and analyze `.spec-workflow/specs/${input:feature}/requirements.md`:

- Understand all functional requirements
- Identify non-functional requirements
- Note integration requirements
- Review acceptance criteria for design implications

### Codebase Architecture Analysis

Use codebase tool to understand:

- **Current architecture patterns** and structures
- **Existing components** that can be reused or extended
- **Data models** and database schemas
- **API patterns** and conventions
- **Testing approaches** and frameworks
- **Error handling** patterns

### Steering Context

Reference steering documents if available:

- **Architecture constraints**: `.spec-workflow/steering/structure.md`
- **Technology stack**: `.spec-workflow/steering/tech.md`
- **Product context**: `.spec-workflow/steering/product.md`

## Optional Research Integration

**Conduct research when designing complex or unfamiliar features**:

### When to Research

- New technology integration
- Complex business logic requirements
- Performance-critical features
- Security-sensitive components
- Industry-specific functionality

### Research Process

1. Use fetch tool to research technical approaches
2. Search for best practices and design patterns
3. Investigate existing solutions and frameworks
4. Analyze pros/cons of different approaches

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

## Technical Design Structure

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

````markdown
### Data Models

#### {ModelName}

**Purpose**: Brief description of the model's role

**Structure**:

```typescript
interface {ModelName} {
  field1: type; // Description
  field2: type; // Description
}
```
````

**Relationships**: Connections to other models
**Validation**: Data validation requirements

````

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
````

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
- **Framework**: {Existing testing framework}
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

## Implementation Guidelines

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

## Design Document Update Process

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

- [ ] All requirements addressed in design
- [ ] Architecture aligns with existing system
- [ ] API specifications are complete
- [ ] Testing strategy is comprehensive
- [ ] Security considerations addressed
- [ ] Performance requirements included
- [ ] Visual diagrams provided

## Next Steps Guidance

After design generation:

1. **Human Review Required**: Review technical design for completeness and feasibility
2. **Architecture Validation**: Confirm design aligns with system architecture
3. **Technical Review**: Validate technical approaches and technology choices
4. **Manual Approval**: Update `spec.yaml` to mark design as approved
5. **Proceed to Tasks**: Use spec-tasks chat mode after design approval

Generate a comprehensive technical design that provides clear implementation guidance while maintaining alignment with existing system architecture and industry best practices.
