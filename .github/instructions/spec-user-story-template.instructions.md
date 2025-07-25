---
description: User story template for structured requirements generation in spec-driven development
applyTo: ".spec-workflow/**/*"
---

# User Story Template for Requirements

Use this structured template when generating requirements for specifications to ensure consistency and completeness.

## User Story Structure

Each requirement should follow this format:

### Requirement N

**User Story:** As a [user type], I want to [do something], so that I can [achieve some goal]

#### Acceptance Criteria

1. WHEN [specific condition] THEN [specific expected outcome]
2. WHEN [specific condition] THEN [specific expected outcome]
3. IF [exception condition] THEN [expected error handling]

## Quality Guidelines for User Stories

### User Story Components

- **User Type**: Be specific about who the user is (end user, admin, developer, etc.)
- **Action**: Clearly describe what the user wants to do
- **Goal**: Explain the benefit or value the user will receive

### Acceptance Criteria Standards

- **Testable**: Each criterion should be verifiable through testing
- **Specific**: Use concrete conditions and expected outcomes
- **Complete**: Cover normal flow, edge cases, and error scenarios
- **Measurable**: Include quantifiable success metrics where applicable

### Requirements Coverage

Ensure requirements address:

- **Functional Requirements**: Core features and capabilities
- **Non-Functional Requirements**: Performance, security, usability
- **Integration Requirements**: How the feature fits with existing systems
- **Data Requirements**: Data structures, validation, persistence
- **Error Handling**: Exception scenarios and recovery

## Template Example

```markdown
### Requirement 1: User Authentication

**User Story:** As a new user, I want to create an account with email and password, so that I can access personalized features of the application.

#### Acceptance Criteria

1. WHEN a user provides valid email and password THEN account is created successfully
2. WHEN a user provides duplicate email THEN system shows "Email already exists" error
3. WHEN a user provides invalid email format THEN system shows validation error
4. IF password is less than 8 characters THEN system shows "Password too short" error
5. WHEN account creation succeeds THEN user receives confirmation email

### Requirement 2: User Login

**User Story:** As a registered user, I want to log in with my credentials, so that I can access my account and data.

#### Acceptance Criteria

1. WHEN user provides correct email and password THEN login succeeds and user is redirected to dashboard
2. WHEN user provides incorrect credentials THEN system shows "Invalid credentials" error
3. WHEN user exceeds 5 failed attempts THEN account is temporarily locked for 15 minutes
4. IF user forgot password THEN system provides password reset option
```

## Integration with Spec Workflow

This template should be referenced in:

- Requirements generation phase (#spec-2-requirements.prompt.md)
- Status checking and validation
- Quality assurance reviews

## Best Practices

- Write from the user's perspective, not the system's
- Keep user stories focused on a single piece of functionality
- Include both positive and negative test scenarios
- Map requirements to business value and user needs
- Ensure requirements are implementation-agnostic
