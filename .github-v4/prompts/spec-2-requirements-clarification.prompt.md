---
description: Generate comprehensive EARS-format requirements with optional research
mode: agent
tools: ['codebase', 'search', 'fetch', 'editFiles']
---

# Requirements Generation

Generate comprehensive requirements for feature: **${input:feature:Enter feature name}**

## Standards and Guidelines

**Requirements Standards**: [EARS Format & Quality Guidelines](../instructions/spec-requirements.instructions.md)  
**Workflow Principles**: [Core Workflow Standards](../instructions/spec-workflow-general.instructions.md)

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
- Scope boundaries and limitations

### 2. Functional Requirements

Each requirement MUST include:

#### EARS Format Statement

- Use WHEN/THEN or GIVEN/WHEN/THEN structure
- Be specific and unambiguous
- Focus on system behavior

#### Acceptance Criteria

- Specific, testable conditions
- Clear pass/fail criteria
- Measurable outcomes

#### Priority Level

- **Must-have**: Core functionality, system won't work without it
- **Should-have**: Important functionality, significant impact if missing
- **Could-have**: Nice-to-have functionality, minimal impact if missing

#### Dependencies

- Other features this requirement depends on
- External system dependencies
- Data or infrastructure requirements

### 3. Non-Functional Requirements

#### Performance Requirements

- Response time expectations
- Throughput requirements
- Resource usage constraints
- Scalability considerations

#### Security Requirements

- Authentication and authorization needs
- Data protection requirements
- Security compliance standards
- Audit and logging needs

#### Usability Requirements

- User experience standards
- Accessibility requirements
- Browser and device compatibility
- User interface guidelines

#### System Requirements

- Integration constraints
- Data format requirements
- API compatibility needs
- Infrastructure dependencies

### 4. Quality Validation

Ensure each requirement is:

- **Specific**: Clearly defined with no ambiguity
- **Testable**: Can be verified through testing
- **Complete**: Covers all necessary functionality
- **Consistent**: Aligns with existing system capabilities
- **Feasible**: Can be implemented within project constraints

## Implementation Process

### 1. Requirements File Update

Update `.spec-workflow/specs/${input:feature}/requirements.md` with:

- Complete requirements document following the structure above
- All functional requirements in EARS format
- Comprehensive non-functional requirements
- Clear acceptance criteria for each requirement

### 2. Spec Metadata Update

Update `.spec-workflow/specs/${input:feature}/spec.yaml`:

```yaml
updated_at: "{current_timestamp}"
phase: "requirements-generated"
approvals:
  requirements:
    generated: true
    approved: false # Requires human approval
```

### 3. Quality Review Checklist

Before completion, verify:

- [ ] All functional requirements use EARS format
- [ ] Each requirement has specific acceptance criteria
- [ ] Priority levels assigned to all requirements
- [ ] Non-functional requirements comprehensively covered
- [ ] Integration with existing system considered
- [ ] Research findings incorporated where applicable

## Next Steps Guidance

After requirements generation:

1. **Human Review Required**: Review generated requirements for accuracy and completeness
2. **Edit as Needed**: Refine requirements based on business and technical review
3. **Manual Approval**: Update `spec.yaml` to mark requirements as approved
4. **Proceed to Design**: Use spec-design chat mode after requirements approval

## Output Guidelines

- Use clear, professional language
- Focus on user and system behavior
- Avoid implementation details (save for design phase)
- Reference existing codebase patterns when relevant
- Include source citations if research was conducted
- Ensure all requirements are actionable and testable

Generate requirements that provide a solid foundation for the technical design phase while maintaining alignment with existing system capabilities and industry best practices.
