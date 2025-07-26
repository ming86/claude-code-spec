---
description: Generate comprehensive EARS-format requirements with optional research
mode: agent
tools: ['codebase', 'search', 'fetch', 'editFiles']
---

# Requirements Generation

Generate comprehensive requirements for feature: **${input:feature:Enter feature name}**

## Context Validation

### Steering Context

Reference steering documents if available:

- **Architecture context**: `.spec-workflow/steering/structure.md`
- **Technical constraints**: `.spec-workflow/steering/tech.md`
- **Product context**: `.spec-workflow/steering/product.md`

### Existing Spec Context

Verify the specification exists and is ready for requirements generation:

- **Current spec directory**: `.spec-workflow/specs/${input:feature}/`
- **Current requirements**: `.spec-workflow/specs/${input:feature}/requirements.md`
- **Spec metadata**: `.spec-workflow/specs/${input:feature}/spec.yaml`

### Codebase Analysis

Use codebase tool to understand:

- Existing system capabilities and patterns
- Similar features for consistency
- Current architectural constraints
- Integration requirements

## Optional Research Integration

**Conduct research when beneficial for complex features**:

### When to Research

- Complex business requirements that need industry context
- Technical approaches requiring best practice validation
- Integration with external systems or standards
- Performance or security-critical features

### Research Process

1. **Use fetch tool** to research relevant topics
2. **Search for best practices** and industry standards
3. **Analyze existing solutions** and approaches
4. **Document key findings** that inform requirements

### Research Documentation

When research is conducted, include:

```markdown
## Research Findings

### Industry Best Practices

- [Source Name](URL) - Key insight or recommendation
- [Standard/Specification](URL) - Relevant requirements or constraints

### Key Insights

- Important findings that inform requirements
- Industry standards or conventions to follow
- Performance or security considerations
```

## EARS Format Requirements

Generate requirements using **EARS** (Easy Approach to Requirements Syntax):

### Primary Format

**WHEN** [specific condition/trigger] **THEN** [specific system response]

### Alternative Format

**GIVEN** [context/precondition] **WHEN** [action/event] **THEN** [expected outcome]

### EARS Examples

```markdown
WHEN user clicks "Login" button AND credentials are valid THEN system redirects to dashboard
GIVEN user is authenticated WHEN user accesses protected resource THEN system grants access with appropriate permissions
WHEN invalid data is submitted THEN system displays specific error message highlighting problematic fields
```

## Requirements Document Structure

### 1. Feature Overview

- Clear description of the feature and its purpose
- Integration points with existing system
- Business value and user benefits

### 2. Functional Requirements

#### Requirement Format

For each requirement:

```markdown
### Requirement [X.X]: [Descriptive Title]

**EARS Statement**: WHEN [condition] THEN [outcome]

**Acceptance Criteria**:

1. WHEN [specific condition] THEN [specific expected result]
2. WHEN [edge case condition] THEN [expected error handling]
3. IF [exception condition] THEN [specific behavior]

**Priority**: Must-have | Should-have | Could-have
**Dependencies**: [List any dependencies on other features/requirements]
```

### 3. Non-Functional Requirements

- **Performance**: Response time, throughput, scalability expectations
- **Security**: Authentication, authorization, data protection requirements
- **Usability**: User experience, accessibility, interface requirements
- **Compatibility**: Browser, device, system compatibility needs

### 4. Integration Requirements

- **API Requirements**: External service integrations
- **Data Requirements**: Database schema changes, data migration needs
- **System Requirements**: Infrastructure, deployment, monitoring needs

## Quality Validation

Ensure each requirement is:

- **Specific**: Clearly defined with no ambiguity
- **Testable**: Can be verified through testing or validation
- **Complete**: Covers all necessary functionality for the feature
- **Consistent**: Aligns with existing system capabilities and constraints
- **Traceable**: Can be mapped to design and implementation tasks

## Requirements Quality Checklist

Before finalizing requirements:

- [ ] All requirements use EARS format (WHEN/THEN or GIVEN/WHEN/THEN)
- [ ] Each requirement has specific, testable acceptance criteria
- [ ] Edge cases and error conditions are addressed
- [ ] Integration with existing features is considered
- [ ] Non-functional requirements are included
- [ ] Research findings are incorporated (if research was conducted)
- [ ] Requirements are prioritized appropriately
- [ ] Dependencies are clearly identified

## Metadata Updates

Update spec.yaml upon completion:

```yaml
phase: "requirements-generated"
progress:
  requirements: 100
  design: 0
  tasks: 0
approvals:
  requirements:
    generated: true
    approved: false
updated_at: "{current_timestamp}"
```

## Next Steps

After requirements generation:

1. **Human Review**: Thoroughly review generated requirements
2. **Edit as Needed**: Make any necessary adjustments or additions
3. **Approve Requirements**: Update spec.yaml to set `requirements.approved: true`
4. **Proceed to Design**: Only after requirements are approved

Generate comprehensive, well-structured requirements that provide a solid foundation for technical design and implementation.
