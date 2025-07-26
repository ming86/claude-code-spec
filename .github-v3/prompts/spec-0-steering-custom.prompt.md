---
description: Create specialized steering documents for specific domains and practices
mode: agent
tools: ['codebase', 'search', 'editFiles']
---

# Custom Steering Document Creation

Create specialized steering documents for: **${input:domain:Enter domain/area (e.g., API standards, testing, security)}**

## Custom Steering Overview

Beyond the core steering documents (product.md, tech.md, structure.md), create specialized documentation for specific development domains, practices, or standards.

## Common Custom Steering Domains

### API Standards and Guidelines

**File**: `api-standards.instructions.md`

- REST API design principles
- Endpoint naming conventions
- Request/response format standards
- Authentication and authorization patterns
- Error handling and status codes
- Documentation requirements

### Testing Methodologies

**File**: `testing-approach.instructions.md`

- Unit testing standards and frameworks
- Integration testing strategies
- End-to-end testing approaches
- Test data management
- Coverage requirements
- Testing automation and CI/CD integration

### Security Policies and Standards

**File**: `security-policies.instructions.md`

- Authentication and authorization standards
- Data protection and privacy requirements
- Security vulnerability assessment
- Code security review guidelines
- Deployment security practices
- Incident response procedures

### Database Conventions

**File**: `database-standards.instructions.md`

- Schema design principles
- Naming conventions for tables, columns, indexes
- Migration and versioning strategies
- Performance optimization guidelines
- Data backup and recovery procedures
- Database access patterns

### Performance Standards

**File**: `performance-requirements.instructions.md`

- Performance benchmarks and targets
- Optimization strategies and techniques
- Monitoring and alerting requirements
- Load testing procedures
- Caching strategies
- Resource usage guidelines

### Deployment and DevOps

**File**: `deployment-workflows.instructions.md`

- Deployment pipeline standards
- Environment configuration management
- Infrastructure as code practices
- Monitoring and logging requirements
- Rollback and recovery procedures
- Release management processes

## Custom Document Structure

### Document Template

```markdown
---
applyTo: "{glob-pattern}"
description: "{Domain-specific standards description}"
---

# {Domain} Standards and Guidelines

## Overview

Brief description of the domain and why standards are important.

## Core Principles

- Key principle 1
- Key principle 2
- Key principle 3

## Standards and Requirements

### {Standard Category 1}

Detailed requirements and guidelines for this category.

### {Standard Category 2}

Detailed requirements and guidelines for this category.

## Implementation Guidelines

- How to apply these standards
- Tools and frameworks to use
- Integration with existing workflow

## Quality Checklist

- [ ] Requirement 1 met
- [ ] Requirement 2 met
- [ ] Requirement 3 met

## Examples

Concrete examples of applying these standards.

## References

- [External Standard](URL) - Industry standard or best practice
- [Tool Documentation](URL) - Relevant tool or framework docs
```

### Inclusion Mode Configuration

#### Always Included (for universal standards)

```markdown
---
applyTo: "**"
description: "Universal standards applied to all code"
---
```

#### Conditional Inclusion (for specific file types)

```markdown
---
applyTo: "**/*.test.*,**/spec/**/*"
description: "Testing standards for test files"
---
```

#### Manual Reference (for specialized contexts)

```markdown
---
description: "Security standards - reference with @security-policies.md when needed"
---
```

## Domain Analysis Process

### 1. Codebase Analysis

Use codebase tool to understand:

- Current practices and patterns in the specified domain
- Existing standards or conventions already in use
- Tools and frameworks currently employed
- Areas where standards would add value

### 2. Gap Analysis

Identify:

- Inconsistencies in current practices
- Missing standards or guidelines
- Areas of confusion or ambiguity
- Opportunities for improvement

### 3. Standard Development

Create standards that:

- Address identified gaps and inconsistencies
- Build on existing good practices
- Are practical and achievable
- Align with industry best practices

### 4. Integration Planning

Consider:

- How standards integrate with existing workflow
- Tools needed to support the standards
- Training or communication requirements
- Rollout and adoption strategy

## Implementation Examples

### API Standards Example

```markdown
---
applyTo: "**/api/**/*,**/*api*,**/controllers/**/*"
description: "REST API design and implementation standards"
---

# API Standards and Guidelines

## REST API Design Principles

- Use noun-based resource URLs
- Implement standard HTTP methods (GET, POST, PUT, DELETE)
- Return appropriate HTTP status codes
- Use consistent error response format

## Endpoint Naming Conventions

- Use plural nouns for collections: `/api/users`
- Use specific resource IDs: `/api/users/{id}`
- Use nested resources for relationships: `/api/users/{id}/orders`

## Request/Response Standards

- All requests and responses use JSON format
- Include proper Content-Type headers
- Implement request validation and sanitization
- Use consistent timestamp formats (ISO 8601)
```

### Testing Standards Example

```markdown
---
applyTo: "**/*.test.*,**/spec/**/*,**/tests/**/*"
description: "Testing standards and best practices"
---

# Testing Standards and Guidelines

## Unit Testing Requirements

- Every public function must have unit tests
- Test coverage minimum 80% for new code
- Use descriptive test names that explain behavior
- Follow Arrange-Act-Assert pattern

## Integration Testing Standards

- Test API endpoints with realistic data
- Validate database interactions
- Test error handling and edge cases
- Use test databases, not production data
```

## Quality Validation

### Standard Quality Checklist

- [ ] Standards are specific and actionable
- [ ] Examples provided for complex requirements
- [ ] Integration with existing workflow considered
- [ ] Tools and implementation guidance included
- [ ] Quality metrics or validation criteria defined

### Applicability Assessment

- [ ] Glob patterns correctly target relevant files
- [ ] Inclusion mode appropriate for standard scope
- [ ] Standards don't conflict with existing practices
- [ ] Implementation burden is reasonable

## Maintenance and Evolution

### Regular Review Process

- Review standards quarterly for relevance
- Update based on new tools or practices
- Gather feedback from development team
- Evolve standards based on project experience

### Version Control

- Track changes to standards over time
- Document rationale for major changes
- Communicate updates to development team
- Archive obsolete standards

Create specialized steering documents that provide clear, actionable guidance for specific development domains while integrating seamlessly with existing workflow and practices.
