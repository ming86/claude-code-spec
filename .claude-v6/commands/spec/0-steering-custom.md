---
description: 'Create specialized steering documents for specific technical domains and standards'
argument-hint: '[steeringType] [inclusionMode: always|conditional|manual]'
---

# Role and Objective

Analyze specific technical domains and create targeted guidance documents in `.spec-workflow/steering/` that complement core project steering while maintaining consistency with existing patterns.

# Instructions

## Domain Analysis Strategy

- **Context-Driven**: All steering content must be based on actual codebase analysis, not assumptions
- **Integration-Focused**: New steering must integrate seamlessly with existing steering documents
- **Non-Conflicting**: Avoid duplicating or contradicting existing project guidelines
- **Practical**: Provide actionable guidance that can be consistently applied

## Anti-Shortcut Quality Patterns

- Analyze existing codebase using systematic domain-specific investigation rather than making generic assumptions
- Create domain-specific content based on actual patterns found in the project, not industry boilerplate
- Use comprehensive analysis to understand domain-specific implementations and conventions
- Generate content grounded in actual project context and existing patterns

# Execution Steps

## 1. Domain Investigation

**Objective**: Understand current state of the requested technical domain

**Process**:

- Detect domain-relevant files and configurations systematically
- Examine implementation patterns and examples in the specific domain
- Analyze discovered patterns for steering content creation
- Document technology-specific approaches found in the project

## 2. Gap Analysis and Standards Planning

**Objective**: Identify what guidance is needed and how it should be structured

**Process**:

- Compare current practices against industry standards and best practices
- Identify inconsistencies, missing guidelines, and areas needing clarification
- Plan standard categories and organization based on actual project needs
- Design inclusion mode strategy based on domain scope and usage patterns

## 3. Steering Document Creation

**Objective**: Create comprehensive, actionable steering document

**Process**:

- Build content based on identified patterns and gaps from analysis
- Structure according to domain template while adapting to project needs
- Include concrete examples from the actual codebase where applicable
- Ensure alignment with existing core steering documents (product.md, tech.md, structure.md)

## 4. Workflow Integration

**Objective**: Configure steering document for proper usage

**Process**:

- Determine appropriate inclusion mode based on domain scope and usage patterns
- Configure file patterns for conditional inclusion if applicable
- Update `CLAUDE.md` with new steering configuration
- Verify integration doesn't conflict with existing steering setup

# Specialized Domain Areas

## Available Domain Types

### API Standards and Guidelines

**Target**: `.spec-workflow/steering/api-standards.md`
**Focus Areas**:

- REST/GraphQL design principles and endpoint patterns
- Request/response format standards and validation
- Authentication and authorization implementation patterns
- Error handling strategies and HTTP status code usage
- API documentation requirements and tooling
- Version management and backward compatibility

### Testing Methodologies and Standards

**Target**: `.spec-workflow/steering/testing-approach.md`
**Focus Areas**:

- Unit testing frameworks and patterns used in project
- Integration testing strategies and tools
- End-to-end testing approaches and automation
- Test data management and mocking strategies
- Coverage requirements and quality gates
- CI/CD testing integration and reporting

### Security Policies and Implementation

**Target**: `.spec-workflow/steering/security-policies.md`
**Focus Areas**:

- Authentication and authorization patterns in use
- Data protection and privacy implementation requirements
- Security vulnerability assessment and remediation
- Code security review guidelines and tools
- Deployment security practices and configurations
- Incident response procedures and escalation

### Database Design and Usage Conventions

**Target**: `.spec-workflow/steering/database-conventions.md`
**Focus Areas**:

- Schema design principles and naming conventions
- Query optimization patterns and performance guidelines
- Migration strategies and versioning approaches
- Data backup, recovery, and archival procedures
- Database access patterns and connection management
- Indexing strategies and monitoring practices

### Performance Standards and Optimization

**Target**: `.spec-workflow/steering/performance-standards.md`
**Focus Areas**:

- Performance benchmarks and measurement targets
- Optimization strategies for identified bottlenecks
- Monitoring, alerting, and observability requirements
- Load testing procedures and performance validation
- Caching strategies and implementation patterns
- Resource usage guidelines and constraints

### Deployment and DevOps Practices

**Target**: `.spec-workflow/steering/deployment-workflows.md`
**Focus Areas**:

- Deployment pipeline standards and automation
- Environment configuration management and secrets handling
- Infrastructure as code practices and tooling
- Monitoring, logging, and observability setup
- Rollback procedures and incident response
- Release management and change control processes

# Inclusion Mode Configuration

## Mode Types

### Always Included (Universal Standards)

- Core standards applying to all development work
- Configuration: `applyTo: "**"`
- Use for: Fundamental practices that affect all code

### Conditional Inclusion (File-Pattern Specific)

- Domain-specific standards for particular file patterns
- Configuration: `applyTo: "**/*.{extensions},**/path/pattern/**/*"`
- Use for: Standards specific to certain file types or directories

### Manual Reference (Specialized Context)

- Specialized guidance used on-demand via @filename.md syntax
- Configuration: No applyTo pattern, referenced manually
- Use for: Complex domain expertise needed only in specific contexts

# Output Requirements

## Directory Structure

```
.spec-workflow/
└── steering/
    ├── product.md                    (Core - Always included)
    ├── tech.md                       (Core - Always included)
    ├── structure.md                  (Core - Always included)
    ├── ${steeringType}.md           (Custom - Your inclusion mode)
    └── [other custom files]         (Previously created)
```

## Document Template Structure

```markdown
---
applyTo: "{glob-pattern-based-on-analysis}"
description: "{Domain-specific standards based on codebase analysis}"
---

# {Domain} Standards and Guidelines

## Overview

Brief description of the domain based on codebase analysis and why these specific standards matter for this project.

## Current State Analysis

Summary of existing patterns and practices found in the codebase.

## Core Principles

- Principle 1 based on successful patterns in codebase
- Principle 2 addressing identified gaps or inconsistencies
- Principle 3 aligned with project architecture and constraints

## Standards and Requirements

### {Category 1 - Based on Analysis}

Detailed requirements derived from codebase patterns and identified needs.

### {Category 2 - Based on Analysis}

Detailed requirements derived from codebase patterns and identified needs.

## Implementation Guidelines

- How to apply standards within existing project structure
- Tools and frameworks already in use or recommended additions
- Integration points with existing development workflow

## Quality Checklist

- [ ] Requirement 1 based on project needs
- [ ] Requirement 2 based on project needs
- [ ] Requirement 3 based on project needs

## Examples from Codebase

Concrete examples showing how to apply standards using actual project patterns.

## Integration Notes

How these standards work with existing core steering (product.md, tech.md, structure.md).
```

# Quality Validation

## Completion Criteria

- [ ] Domain thoroughly analyzed using systematic investigation
- [ ] Steering document created with project-specific content
- [ ] Appropriate inclusion mode configured with correct file patterns
- [ ] `CLAUDE.md` updated with new steering configuration
- [ ] Integration verified to work with existing workflow
- [ ] No conflicts with existing core steering documents

## Content Accuracy Validation

- [ ] All documented patterns exist in the actual codebase
- [ ] File patterns for conditional inclusion match actual project structure
- [ ] No generic best practices without project-specific context
- [ ] Steering integrates with existing core documents without conflicts

# Examples

## Argument Handling

```bash
/spec:0-steering-custom api-standards conditional    # API standards for specific file patterns
/spec:0-steering-custom testing-approach always     # Universal testing standards
/spec:0-steering-custom security-policies manual    # On-demand security guidance
/spec:0-steering-custom performance-standards        # Default to conditional mode
```

## Domain Detection Examples

- **API Standards**: "Analyzing API implementations... Found REST endpoints with authentication patterns..."
- **Testing Approach**: "Examining test files... Detected testing frameworks across multiple languages..."
- **Security Patterns**: "Investigating authentication implementations across different tech stacks..."

## Integration Configuration Examples

### Always Inclusion

```markdown
## Custom Steering Files
- `testing-approach.md`: Always - Universal testing standards for all development work
```

### Conditional Inclusion

```markdown
## Custom Steering Files
- `api-standards.md`: Conditional - **/api/**/*.{js,ts} - API design and implementation standards
```

### Manual Reference

```markdown
## Custom Steering Files
- `security-policies.md`: Manual - @security-policies.md - Security guidance for sensitive contexts
```

# Domain-Specific Templates

## API Standards Template

```markdown
---
applyTo: "**/api/**/*.{js,ts,py,cs,java}"
description: "API design and implementation standards based on project patterns"
---

# API Standards and Guidelines

## Overview

API development standards based on analysis of existing endpoint implementations and architectural patterns found in the project.

## Current State Analysis

- **API Architecture**: [REST/GraphQL patterns observed]
- **Authentication**: [Auth mechanisms currently in use]
- **Error Handling**: [Existing error response patterns]
- **Documentation**: [API documentation tools and standards found]

## Core Principles

- Consistent endpoint design following project URL patterns
- Standardized error handling aligned with existing implementations
- Authentication integration using established project mechanisms

## Standards and Requirements

### Endpoint Design

- **URL Patterns**: Follow existing project conventions [specific patterns found]
- **HTTP Methods**: Use established method patterns for CRUD operations
- **Versioning**: Implement versioning strategy consistent with project approach

### Request/Response Standards

- **Request Format**: Follow established JSON schema patterns
- **Response Format**: Use consistent response structure found in existing APIs
- **Validation**: Implement input validation using project validation libraries

### Error Handling

- **Status Codes**: Use HTTP status codes consistent with existing endpoints
- **Error Format**: Follow established error response structure
- **Logging**: Integrate with existing logging infrastructure

## Implementation Guidelines

- Use existing API framework and middleware configurations
- Follow established authentication and authorization patterns
- Integrate with current API documentation tools

## Quality Checklist

- [ ] Endpoints follow established URL patterns
- [ ] Error handling uses consistent format and status codes
- [ ] Authentication integrates with existing mechanisms
- [ ] Documentation follows project standards

## Examples from Codebase

[Concrete examples based on actual API implementations found]
```

## Testing Approach Template

```markdown
---
applyTo: "**"
description: "Testing standards and practices based on project testing infrastructure"
---

# Testing Approach and Standards

## Overview

Testing methodology and standards based on analysis of existing test infrastructure and patterns found in the project.

## Current State Analysis

- **Testing Frameworks**: [Frameworks currently in use]
- **Test Organization**: [How tests are structured and organized]
- **Coverage Tools**: [Coverage measurement and reporting tools]
- **CI Integration**: [How tests integrate with build pipeline]

## Core Principles

- Comprehensive test coverage following project patterns
- Test organization consistent with existing structure
- Integration with established CI/CD pipeline

## Standards and Requirements

### Unit Testing

- **Framework**: Use established testing framework [specific framework found]
- **Structure**: Follow existing test file organization patterns
- **Coverage**: Meet or exceed current project coverage standards
- **Mocking**: Use established mocking patterns and libraries

### Integration Testing

- **Scope**: Test component interactions following project patterns
- **Database**: Use established test database setup and cleanup patterns
- **External Services**: Follow existing service mocking strategies

### End-to-End Testing

- **Framework**: Use established E2E testing tools if present
- **Scenarios**: Cover critical user journeys identified in project
- **Environment**: Integrate with existing test environment setup

## Implementation Guidelines

- Follow existing test naming and organization conventions
- Use established test data management patterns
- Integrate with current CI/CD testing pipeline

## Quality Checklist

- [ ] Tests follow established framework and patterns
- [ ] Coverage meets or exceeds project standards  
- [ ] Integration with existing CI/CD pipeline
- [ ] Test data management follows project conventions

## Examples from Codebase

[Concrete examples based on actual test implementations found]
```

## Security Policies Template

```markdown
---
description: "Security policies and implementation guidelines based on project security patterns"
---

# Security Policies and Implementation

## Overview

Security standards and practices based on analysis of existing security implementations and patterns found in the project.

## Current State Analysis

- **Authentication**: [Auth mechanisms currently implemented]
- **Authorization**: [Permission and role management patterns]
- **Data Protection**: [Encryption and data handling approaches]
- **Security Tools**: [Security scanning and monitoring tools in use]

## Core Principles

- Security-first development following established project patterns
- Integration with existing authentication and authorization systems
- Consistent application of security practices across all components

## Standards and Requirements

### Authentication and Authorization

- **Authentication**: Use established authentication mechanisms
- **Authorization**: Follow existing role-based access patterns
- **Session Management**: Implement session handling consistent with project approach

### Data Protection

- **Encryption**: Apply encryption standards consistent with project requirements
- **Input Validation**: Use established validation patterns and libraries
- **Data Handling**: Follow existing sensitive data management practices

### Security Testing

- **Vulnerability Assessment**: Integrate with existing security scanning tools
- **Code Review**: Follow established security review guidelines
- **Compliance**: Meet regulatory requirements identified in project

## Implementation Guidelines

- Integrate with existing security infrastructure and tools
- Follow established security review and approval processes
- Use current security libraries and frameworks

## Quality Checklist

- [ ] Authentication integrates with existing mechanisms
- [ ] Authorization follows established role patterns
- [ ] Data protection meets project encryption standards
- [ ] Security testing integrated with development workflow

## Examples from Codebase

[Concrete examples based on actual security implementations found]
```

Create specialized steering documents that provide clear, actionable, project-specific guidance for development domains while maintaining seamless integration with existing workflow and practices.
