---
description: Create specialized steering documents for specific technical contexts and standards
tools: ['codebase', 'search', 'editFiles']
---

# Custom Steering Creation Mode

Create specialized steering document for: **${input:steeringType:Enter steering type (e.g., api-standards, testing-approach, security-policies)}**

**Inclusion Mode**: ${input:inclusionMode:always|conditional|manual} - How this steering should be applied

## Purpose and Scope

**Primary Function**: Create specialized steering documents that provide domain-specific guidelines, standards, and conventions beyond the core project steering (product.md, tech.md, structure.md).

**Custom Steering Types**:

- **API Standards**: REST/GraphQL design guidelines, endpoint patterns
- **Testing Approach**: Testing strategies, framework usage, coverage standards
- **Security Policies**: Security guidelines, authentication patterns, data protection
- **Database Conventions**: Schema design, query patterns, migration strategies
- **Performance Standards**: Optimization guidelines, monitoring approaches
- **Code Style Guidelines**: Language-specific conventions, formatting rules
- **Deployment Workflows**: CI/CD patterns, environment configurations

## Prerequisites Validation

### Context Analysis Required

Before creating custom steering:

- **Analyze relevant codebase areas** using codebase tool
- **Identify existing patterns** in the specific domain
- **Review current implementations** of the target area
- **Understand project constraints** that affect the domain

### Existing Steering Integration

Check integration requirements:

- **Review core steering documents** (product.md, tech.md, structure.md)
- **Assess existing custom steering** files for overlap prevention
- **Determine inclusion strategy** based on usage patterns
- **Plan integration** with CLAUDE.md configuration

## Custom Steering Generation Process

### 1. Domain-Specific Analysis

**Codebase Domain Analysis**:

- Use codebase tool to examine relevant code areas
- Identify existing patterns and conventions in the domain
- Analyze current implementation approaches
- Review configuration files relevant to the domain

**Pattern Recognition**:

- Document existing good practices found in codebase
- Identify areas for standardization or improvement
- Note inconsistencies that guidelines should address
- Reference established frameworks or libraries in use

### 2. Steering Document Structure

**Custom Steering Template**:

```markdown
# ${steeringType} Steering

## Overview

[Brief description of this domain and its importance to the project]

## Current State Analysis

[What was found in the codebase regarding this domain]

## Standards and Guidelines

### [Domain-Specific Section 1]

- [Specific guideline based on project context]
- [Reference to existing patterns where applicable]
- [Rationale for the standard]

### [Domain-Specific Section 2]

- [Additional guidelines as needed]
- [Code examples from existing codebase where helpful]
- [Integration requirements with other systems]

## Implementation Guidelines

[How to apply these standards in practice]

## Quality Checks

[How to validate compliance with these standards]

## Integration Notes

[How this integrates with existing project patterns]
```

### 3. Domain-Specific Templates

**API Standards Steering**:

```markdown
# API Standards Steering

## Overview

API design standards and conventions for [project name] based on existing implementation patterns.

## Current API Analysis

[Analysis of existing API endpoints, patterns, authentication, etc.]

## Endpoint Design Standards

- **Naming Convention**: [Based on existing patterns]
- **HTTP Methods**: [Usage patterns found in codebase]
- **Response Format**: [Existing response structures]
- **Error Handling**: [Current error handling approaches]

## Authentication and Authorization

[Existing auth patterns and standards]

## Documentation Requirements

[API documentation standards based on current practices]
```

**Testing Approach Steering**:

```markdown
# Testing Approach Steering

## Overview

Testing strategies and conventions for [project name] based on existing test infrastructure.

## Current Testing Infrastructure

[Analysis of existing test setup, frameworks, patterns]

## Testing Standards

- **Unit Testing**: [Existing unit test patterns and requirements]
- **Integration Testing**: [Current integration test approaches]
- **Coverage Requirements**: [Existing coverage standards]
- **Test Organization**: [Current test file organization patterns]

## Framework Usage

[How to use existing testing frameworks and utilities]

## Quality Gates

[Existing quality requirements and enforcement]
```

**Security Policies Steering**:

```markdown
# Security Policies Steering

## Overview

Security guidelines and standards for [project name] based on current security implementations.

## Current Security Analysis

[Analysis of existing security measures, authentication, data protection]

## Security Standards

- **Authentication**: [Existing auth implementations and standards]
- **Data Protection**: [Current data handling and protection measures]
- **Input Validation**: [Existing validation patterns]
- **Access Control**: [Current authorization patterns]

## Implementation Guidelines

[How to implement security measures consistently]

## Compliance Requirements

[Security standards that must be maintained]
```

## Inclusion Mode Configuration

### Always Included Mode

**When to use**: Core standards that apply to all development work

**Configuration**:

```markdown
### Custom Steering Files

- `${steeringType}.md`: Always included - [Brief description of purpose]
```

**Benefits**: Automatic context for all interactions, consistent application

### Conditional Mode

**When to use**: Standards that apply to specific file types or contexts

**Configuration**:

```markdown
### Custom Steering Files

- `${steeringType}.md`: Conditional - `"${input:filePattern:Enter file pattern (e.g., src/api/**/*,**/*api*)}"` - [Brief description]
```

**Examples**:

- `"src/api/**/*", "**/*api*"` - API-related files
- `"**/*.test.*", "**/spec/**/*"` - Test files
- `"**/*.security.*", "**/auth/**/*"` - Security-related files

### Manual Mode

**When to use**: Specialized guidance used on-demand

**Configuration**:

```markdown
### Custom Steering Files

- `${steeringType}.md`: Manual - [Description] (reference with @${steeringType}.md)
```

**Benefits**: Available when needed, doesn't add context overhead for unrelated work

## Integration and Validation

### CLAUDE.md Integration

**Update steering configuration**:

1. **Add to Custom Steering Files section** in CLAUDE.md
2. **Specify inclusion mode** and file patterns if conditional
3. **Provide usage guidance** for manual inclusion files
4. **Update steering file list** to reflect new additions

### Quality Validation

**Custom steering document must**:

- **Build on existing patterns** found in the codebase
- **Provide actionable guidance** for specific domain
- **Integrate well** with core steering documents
- **Include specific examples** from project context
- **Define clear standards** that can be consistently applied

### Consistency Checks

**Ensure custom steering**:

- **Aligns with core steering** (product.md, tech.md, structure.md)
- **Doesn't conflict** with existing custom steering
- **References actual codebase** patterns and implementations
- **Supports project goals** defined in product steering
- **Uses established technologies** documented in tech steering

## File Management

### Custom Steering Location

**File structure**:

```
.kiro/
└── steering/
    ├── product.md                    (Core - Always included)
    ├── tech.md                       (Core - Always included)
    ├── structure.md                  (Core - Always included)
    ├── ${steeringType}.md           (Custom - Your inclusion mode)
    └── [other custom files]         (Previously created)
```

### Naming Conventions

**Recommended naming patterns**:

- `api-standards.md` - API design guidelines
- `testing-approach.md` - Testing strategies and conventions
- `security-policies.md` - Security standards and requirements
- `database-conventions.md` - Database design and usage patterns
- `performance-standards.md` - Performance guidelines and requirements
- `code-style-[language].md` - Language-specific style guidelines

## Boundaries and Constraints

### What This Phase DOES

- ✅ Create specialized steering documents for specific domains
- ✅ Analyze existing codebase patterns in the target domain
- ✅ Configure appropriate inclusion modes for the steering type
- ✅ Integrate with existing steering structure and CLAUDE.md
- ✅ Provide domain-specific guidelines based on project context

### What This Phase DOES NOT DO

- ❌ Create or modify core steering documents (use spec-0-steering)
- ❌ Generate feature specifications or requirements
- ❌ Create implementation plans or tasks
- ❌ Modify application code or configuration
- ❌ Create spec workflow directories (use spec-1-init)

## Completion Process

After creating custom steering document:

1. **Validate domain accuracy** against codebase analysis
2. **Test inclusion mode** configuration works as expected
3. **Update CLAUDE.md** custom steering section
4. **Verify integration** with existing steering documents
5. **Provide usage guidance** for the new steering document

Create specialized steering that enhances project context while integrating seamlessly with existing steering infrastructure.
