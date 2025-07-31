---
description: Create specialized steering documents for specific domains and practices
mode: agent
tools: ['codebase', 'search', 'editFiles']
---

# Custom Steering Document Creation

Create specialized steering document for: **${input:steeringType:Enter steering type (e.g., api-standards, testing-approach, security-policies)}**

**Inclusion Mode**: ${input:inclusionMode:always|conditional|manual} - How this steering should be applied

## Custom Steering Types

### API Standards and Guidelines

**File**: `.kiro/steering/api-standards.md`

- REST API design principles
- Endpoint naming conventions
- Request/response format standards
- Authentication and authorization patterns
- Error handling and status codes
- Documentation requirements

### Testing Methodologies

**File**: `.kiro/steering/testing-approach.md`

- Unit testing standards and frameworks
- Integration testing strategies
- End-to-end testing approaches
- Test data management
- Coverage requirements
- Testing automation and CI/CD integration

### Security Policies and Standards

**File**: `.kiro/steering/security-policies.md`

- Authentication and authorization standards
- Data protection and privacy requirements
- Security vulnerability assessment
- Code security review guidelines
- Deployment security practices
- Incident response procedures

### Database Conventions

**File**: `.kiro/steering/database-conventions.md`

- Schema design principles
- Naming conventions for tables, columns, indexes
- Migration and versioning strategies
- Performance optimization guidelines
- Data backup and recovery procedures
- Database access patterns

### Performance Standards

**File**: `.kiro/steering/performance-standards.md`

- Performance benchmarks and targets
- Optimization strategies and techniques
- Monitoring and alerting requirements
- Load testing procedures
- Caching strategies
- Resource usage guidelines

### Deployment and DevOps

**File**: `.kiro/steering/deployment-workflows.md`

- Deployment pipeline standards
- Environment configuration management
- Infrastructure as code practices
- Monitoring and logging requirements
- Rollback and recovery procedures
- Release management processes

## Custom Document Structure Template

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

## Inclusion Mode Configuration

### Always Included (for universal standards)

```markdown
---
applyTo: "**"
description: "Universal standards applied to all code"
---
```

### Conditional Inclusion (for specific file types)

```markdown
---
applyTo: "**/*.test.*,**/spec/**/*"
description: "Testing standards for test files"
---
```

### Manual Reference (for specialized contexts)

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

## copilot-instructions.md Integration

**Update steering configuration**:

1. **Add to Custom Steering Files section** in `.github/copilot-instructions.md`
2. **Specify inclusion mode** and file patterns if conditional
3. **Provide usage guidance** for manual inclusion files
4. **Update steering file list** to reflect new additions

### Custom Steering Files Configuration Format

```markdown
### Custom Steering Files

<!-- Added by /kiro:steering-custom command -->

- `${steeringType}.md`: ${inclusionMode} - ${filePattern} - [Brief description]
```

## File Location

**Target Directory**: `.kiro/steering/${steeringType}.md`

Create specialized steering documents that provide clear, actionable guidance for specific development domains while integrating seamlessly with existing workflow and practices.
