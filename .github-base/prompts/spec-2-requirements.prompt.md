---
description: Spec-Driven Development Step 2 - Generate comprehensive requirements for a specification using structured user stories
mode: agent
tools: ['changes', 'codebase', 'editFiles', 'extensions', 'problems', 'runCommands', 'runTasks', 'search', 'searchResults', 'terminalLastCommand', 'terminalSelection', 'testFailure', 'usages', 'get_syntax_docs', 'mermaid-diagram-preview', 'mermaid-diagram-validator']
---

# Requirements Generation

Generate comprehensive requirements for feature: **${input:feature:Enter feature name}**

## Context Validation

### Steering Context

Reference steering documents if available:

- Architecture context: #.spec-workflow/steering/structure.md
- Technical constraints: #.spec-workflow/steering/tech.md
- Product context: #.spec-workflow/steering/product.md

### Existing Spec Context

Verify the specification exists and is ready for requirements generation:

- Current spec directory: Check `.spec-workflow/specs/${input:feature}/`
- Current requirements: Reference `.spec-workflow/specs/${input:feature}/requirements.md`
- Spec metadata: Reference `.spec-workflow/specs/${input:feature}/spec.yaml`

## Requirements Generation Process

Create comprehensive requirements document following this structured user story template:

---
## 📋 USER STORY TEMPLATE REFERENCE
*Use this template structure when generating requirements - this is template content, not prompt instructions*

### User Story Template for Requirements

Use this structured template when generating requirements for specifications to ensure consistency and completeness.

### User Story Structure

Each requirement should follow this format:

#### Requirement N

**User Story:** As a [user type], I want to [do something], so that I can [achieve some goal]

##### Acceptance Criteria

1. WHEN [specific condition] THEN [specific expected outcome]
2. WHEN [specific condition] THEN [specific expected outcome]
3. IF [exception condition] THEN [expected error handling]

### Quality Guidelines for User Stories

#### User Story Components

- **User Type**: Be specific about who the user is (end user, admin, developer, etc.)
- **Action**: Clearly describe what the user wants to do
- **Goal**: Explain the benefit or value the user will receive

#### Acceptance Criteria Standards

- **Testable**: Each criterion should be verifiable through testing
- **Specific**: Use concrete conditions and expected outcomes
- **Complete**: Cover normal flow, edge cases, and error scenarios
- **Measurable**: Include quantifiable success metrics where applicable

#### Requirements Coverage

Ensure requirements address:

- **Functional Requirements**: Core features and capabilities
- **Non-Functional Requirements**: Performance, security, usability
- **Integration Requirements**: How the feature fits with existing systems
- **Data Requirements**: Data structures, validation, persistence
- **Error Handling**: Exception scenarios and recovery

### Template Example

```markdown
#### Requirement 1: User Authentication

**User Story:** As a new user, I want to create an account with email and password, so that I can access personalized features of the application.

##### Acceptance Criteria

1. WHEN a user provides valid email and password THEN account is created successfully
2. WHEN a user provides duplicate email THEN system shows "Email already exists" error
3. WHEN a user provides invalid email format THEN system shows validation error
4. IF password is less than 8 characters THEN system shows "Password too short" error
5. WHEN account creation succeeds THEN user receives confirmation email

#### Requirement 2: User Login

**User Story:** As a registered user, I want to log in with my credentials, so that I can access my account and data.

##### Acceptance Criteria

1. WHEN user provides correct email and password THEN login succeeds and user is redirected to dashboard
2. WHEN user provides incorrect credentials THEN system shows "Invalid credentials" error
3. WHEN user exceeds 5 failed attempts THEN account is temporarily locked for 15 minutes
4. IF user forgot password THEN system provides password reset option
```

### Best Practices

- Write from the user's perspective, not the system's
- Keep user stories focused on a single piece of functionality
- Include both positive and negative test scenarios
- Map requirements to business value and user needs
- Ensure requirements are implementation-agnostic

---
*End of template reference section*

### 1. Requirements Structure

Generate requirements.md with structured user stories:

```markdown
# Requirements Specification

## Overview

[Clear overview of the feature and its purpose]

## Requirements

### Requirement 1

**User Story:** As a [user type], I want to [do something], so that I can [achieve some goal]

#### Acceptance Criteria

1. WHEN [specific condition] THEN [specific expected outcome]
2. WHEN [specific condition] THEN [specific expected outcome]
3. IF [exception condition] THEN [expected error handling]

### Requirement 2

**User Story:** As a [user type], I want to [do something], so that I can [achieve some goal]

#### Acceptance Criteria

1. WHEN [specific condition] THEN [specific expected outcome]
2. WHEN [specific condition] THEN [specific expected outcome]
3. IF [exception condition] THEN [expected error handling]

### Requirement 3

[Additional requirements following same pattern]
```

### 2. Requirements Quality Guidelines

Ensure all requirements meet these quality standards:

- **User-Centric**: Write from user perspective
- **Testable**: Each acceptance criterion should be verifiable
- **Specific**: Use concrete conditions and outcomes
- **Complete**: Cover all major user scenarios
- **Contextual**: Consider existing system integration

### 3. Integration Considerations

Based on steering context, consider:

- How this feature fits with existing architecture
- Technical constraints that affect requirements
- Existing user workflows that need integration
- Performance and scalability requirements

### 4. Update Metadata

After generating requirements, update spec.yaml with:

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

### 5. Document Generation Focus

Generate the requirements document content ONLY. Do not include review or approval instructions in the actual document file.

## Quality Validation

Ensure the generated requirements:

- Follow the user story template structure
- Include specific, testable acceptance criteria
- Cover all aspects of the feature described in the original project description
- Consider integration with existing system components
- Provide clear foundation for the design phase

## Cross-References

This prompt works within the spec-driven development workflow:

- **Previous step**: #spec-1-init.prompt.md (specification initialization)
- **Next step**: #spec-3-design.prompt.md (technical design - requires requirements approval)
- **Status check**: #spec-5-status.prompt.md (view current progress)

## Implementation Instructions

### Execution Steps:

1. **Verify feature exists** - Check that the specification directory and files exist
2. **Analyze project context** from existing requirements.md and spec.yaml
3. **Apply steering context** to understand architectural and technical constraints
4. **Generate user-focused requirements** with clear acceptance criteria
5. **Follow inline template structure** provided above in this prompt
6. **Update tracking metadata** upon completion
7. **Provide next steps** for human review and approval process

### Output Guidelines:

- Generate requirements that provide clear foundation for design phase
- Use specific, concrete language in acceptance criteria
- Include error handling and edge cases
- Consider system integration points
- Maintain consistency with established project patterns

## Human Review Process

After generation, the requirements must be reviewed and approved before proceeding to design:

1. **Human reviews** the generated requirements.md
2. **Manual edits** can be made directly to the file if needed
3. **Approval** is granted by manually updating spec.yaml:
   ```yaml
   approvals:
     requirements:
       generated: true
       approved: true
   phase: "requirements-approved"
   ```
4. **Only after approval** can #spec-3-design.prompt.md be used

This ensures quality requirements that serve as a solid foundation for technical design and implementation planning.
