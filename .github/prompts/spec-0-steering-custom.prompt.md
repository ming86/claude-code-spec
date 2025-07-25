---
description: Spec-Driven Development Step 0 - Create custom project steering documents for specialized contexts beyond core steering files
mode: agent
tools: ['changes', 'codebase', 'editFiles', 'extensions', 'problems', 'runCommands', 'runTasks', 'search', 'searchResults', 'terminalLastCommand', 'terminalSelection', 'testFailure', 'usages', 'get_syntax_docs', 'mermaid-diagram-preview', 'mermaid-diagram-validator']
---

# Custom Project Steering Creation

Create custom steering documents in `.spec-workflow/steering/` for specialized contexts beyond the three foundational files (product.md, tech.md, structure.md).

## Steering Context Analysis

First, analyze the current project state to identify areas that would benefit from custom steering:

### Existing Steering Documents

Check for:

- Core steering files in `.spec-workflow/steering/`
- Count of existing custom steering files
- Current coverage areas

### Project Specialization Analysis

Look for specialized areas that indicate need for custom steering:

- Specialized directories (test, spec, api, auth, security)
- Configuration patterns (_.config._, _rc._)
- Domain-specific code patterns
- Unique architectural components

## Common Custom Steering Types

Consider these common custom steering document types:

### 1. API Standards (`api-standards.md`)

- REST/GraphQL conventions
- Error handling patterns
- Authentication/authorization approaches
- Rate limiting and pagination
- API versioning strategy

### 2. Testing Approach (`testing.md`)

- Test file organization
- Naming conventions for tests
- Mocking strategies
- Coverage requirements
- E2E vs unit vs integration testing

### 3. Code Style Guidelines (`code-style.md`)

- Language-specific conventions
- Formatting rules beyond linters
- Comment standards
- Function/variable naming patterns
- Code organization principles

### 4. Security Policies (`security.md`)

- Input validation requirements
- Authentication patterns
- Secrets management
- OWASP compliance guidelines
- Security review checklist

### 5. Database Conventions (`database.md`)

- Schema design patterns
- Migration strategies
- Query optimization guidelines
- Connection pooling settings
- Backup and recovery procedures

### 6. Performance Standards (`performance.md`)

- Load time requirements
- Memory usage limits
- Optimization techniques
- Caching strategies
- Monitoring and profiling

### 7. Deployment Workflow (`deployment.md`)

- CI/CD pipeline stages
- Environment configurations
- Release procedures
- Rollback strategies
- Health check requirements

## Inclusion Mode Selection

Choose the appropriate inclusion mode based on usage context:

### 1. Always Included (Use sparingly for custom files)

- **When to use**: Universal standards that apply to ALL code (security policies, core conventions)
- **Impact**: Increases context size for every interaction
- **Example**: `security-standards.md` for critical security requirements
- **Recommendation**: Only use for truly universal guidelines

### 2. Conditional Inclusion (Recommended for most custom files)

- **When to use**: Domain-specific guidelines for particular file types or directories
- **File patterns**: `"*.test.js"`, `"src/api/**/*"`, `"**/auth/*"`, `"*.config.*"`
- **Example**: `testing-approach.md` only loads when editing test files
- **Benefits**: Relevant context without overwhelming general interactions

### 3. Manual Inclusion (Best for specialized contexts)

- **When to use**: Specialized knowledge needed occasionally
- **Usage**: Reference with `#filename.md` during specific conversations
- **Example**: `deployment-runbook.md` for deployment-specific tasks
- **Benefits**: Available when needed, doesn't clutter routine interactions

## Document Structure Guidelines

Create custom steering documents with:

### 1. Clear Title and Purpose

- What aspect of the project this document covers
- When this guidance should be applied

### 2. Specific Guidelines

- Concrete rules and patterns to follow
- Rationale for important decisions

### 3. Code Examples

- Show correct implementation patterns
- Include counter-examples if helpful

### 4. Integration Points

- How this relates to other steering documents
- Dependencies or prerequisites

## Quality and Security Guidelines

### Security Requirements

- **Never include sensitive data**: No API keys, passwords, database URLs, secrets
- **Review sensitive context**: Avoid internal server names, private API endpoints
- **Team access awareness**: All steering content is shared with team members

### Content Quality Standards

- **Single responsibility**: One steering file = one domain (don't mix API + database guidelines)
- **Concrete examples**: Include code snippets and real project examples
- **Clear rationale**: Explain WHY certain approaches are preferred
- **Maintainable size**: Target 2-3 minute read time per file

## Implementation Instructions

### Step 1: Requirements Gathering

Ask the user for:

- Document name (descriptive filename ending in .md)
- Topic/purpose of the custom steering
- Inclusion mode preference
- Specific patterns for conditional inclusion (if applicable)

### Step 2: Document Creation

Create the document in `.spec-workflow/steering/` with:

- Clear, focused content (2-3 minute read)
- Practical examples
- Consistent formatting with other steering files

### Step 3: Inclusion Mode Documentation

Add a comment at the top of the document:

```markdown
<!-- Inclusion Mode: Always | Conditional: "pattern" | Manual -->
```

### Step 4: Validation

Ensure the document:

- Doesn't duplicate existing steering content
- Provides unique value for the specified context
- Follows markdown best practices

## Integration with Existing Workflow

Custom steering documents should:

- Supplement, not replace, the foundational three files
- Provide specialized context for specific aspects of the project
- Integrate seamlessly with the spec-driven development workflow
- Reference related steering documents using #-references

Remember: Custom steering documents enhance the development process by providing targeted guidance for specialized areas while maintaining the clean separation of concerns established by the core steering files.
