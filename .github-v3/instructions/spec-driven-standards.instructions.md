---
description: Automatic EARS format and spec-driven development quality standards
applyTo: ".spec-workflow/**/*"
---

# Spec-Driven Development Standards

These standards are automatically applied to all spec-driven development work in the `.spec-workflow/` directory.

## Requirements Standards

### EARS Format Requirements

- **MUST use EARS format**: WHEN [condition] THEN [response]
- **Alternative format**: GIVEN [context] WHEN [action] THEN [outcome]
- **MUST provide testable acceptance criteria** for each requirement
- **MUST reference existing system capabilities** when relevant

### Example EARS Formats

```
WHEN user clicks "Submit" button AND all required fields are filled THEN system processes the request
GIVEN user is authenticated WHEN user accesses protected resource THEN system grants access
WHEN invalid data is submitted THEN system displays specific error message and highlights problematic fields
```

### Requirements Quality

- Use specific, measurable conditions
- Avoid ambiguous language ("user-friendly", "fast", "intuitive")
- Include error conditions and edge cases
- Reference existing system behavior for consistency

## Design Standards

### Research Documentation

When research is conducted:

- **MUST include research findings** with source URLs
- **MUST cite sources** for all external information
- **MUST summarize key findings** that inform design decisions
- **MUST compare alternative approaches** with rationale for choices

### Architecture Documentation

- **MUST use mermaid diagrams** for system architecture
- **MUST define clear component interfaces** and responsibilities
- **MUST specify data models** with type definitions
- **MUST include error handling strategy**

### Integration Requirements

- Follow existing architectural patterns
- Use established coding conventions
- Leverage existing utilities and components
- Consider impact on existing features

## Task Standards

### Task Structure

- **MUST focus on coding tasks only** (writing, modifying, testing code)
- **MUST exclude deployment/user testing tasks**
- **MUST reference specific requirements** for each task (_Requirements: 1.1, 2.3_)
- **MUST use hierarchical numbering** (1.1, 1.2, 2.1, 2.2 - max 2 levels)

### Task Quality

- Each task should be completable in 2-4 hours
- Include clear acceptance criteria for task completion
- Specify required files and components
- Include testing requirements where applicable

### Task Transformations

Transform non-coding tasks:

- "Deploy to production" → "Create deployment configuration files"
- "User acceptance testing" → "Create automated test suite"
- "Performance monitoring" → "Add performance logging to code"
- "Marketing tasks" → "Create technical documentation"

## Implementation Standards

### Code Quality

- Follow existing code patterns and conventions
- Include unit tests for new functionality
- Add appropriate error handling
- Document complex business logic

### Progress Tracking

- Update task completion status in real-time
- Mark completed tasks with ✅ and timestamp
- Document any issues encountered and resolved
- Provide clear progress visibility

### Validation Requirements

- Code must compile without errors
- Tests must pass (if tests exist)
- Integration with existing code must be verified
- Functionality must meet acceptance criteria

## Quality Validation

### Self-Assessment Checklist

Before marking any work complete:

- [ ] Requirements use EARS format with testable criteria
- [ ] Design includes necessary diagrams and component definitions
- [ ] Tasks focus on coding activities with clear acceptance criteria
- [ ] Implementation follows existing patterns and conventions
- [ ] All changes integrate properly with existing code

### Research Citation Format

When research is conducted:

```markdown
## Research Sources

- [Technology Approach](https://example.com/article) - Key insight about implementation
- [Best Practices Guide](https://example.com/guide) - Recommended patterns and approaches
- [Performance Considerations](https://example.com/perf) - Optimization strategies
```

## Workflow Integration

### Phase Dependencies

- Design phase requires approved requirements
- Tasks phase requires approved design
- Implementation requires approved tasks
- Each phase builds on the previous phase's deliverables

### Approval Process

- Manual review and approval required between phases
- Update spec metadata to indicate approval status
- Ensure quality standards are met before progression

These standards ensure consistent, high-quality spec-driven development across all projects.
