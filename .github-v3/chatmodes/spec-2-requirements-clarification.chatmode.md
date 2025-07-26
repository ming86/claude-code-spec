---
description: Generate EARS-format requirements with codebase analysis and optional research
tools: ['codebase', 'search', 'fetch', 'githubRepo']
---

# Requirements Generation Mode

Generate comprehensive requirements for feature: **${input:feature:Enter feature name}**

## Context Analysis

Use the codebase tool to understand existing patterns and architecture:

- Analyze current system capabilities and constraints
- Identify existing similar features for consistency
- Review architectural patterns and conventions

## EARS Format Requirements

Generate requirements using EARS (Easy Approach to Requirements Syntax):

**Format**: WHEN [condition/trigger] THEN [system response]
**Alternative**: GIVEN [context] WHEN [action] THEN [outcome]

### Examples

- WHEN user clicks "Login" button AND credentials are valid THEN system redirects to dashboard
- GIVEN user is authenticated WHEN user requests protected resource THEN system grants access
- WHEN invalid data is submitted THEN system displays specific error message

## Optional Research Integration

**Use fetch tool when beneficial for complex features**:

- Research industry best practices for similar features
- Investigate technical approaches and patterns
- Gather examples of successful implementations
- **Include source citations when research is conducted**

## Requirements Structure

Generate requirements document with:

### 1. Feature Overview

- Clear description of the feature and its purpose
- Integration points with existing system

### 2. Functional Requirements

Each requirement MUST include:

- **EARS format statement**
- **Acceptance criteria** (specific, testable conditions)
- **Priority level** (must-have, should-have, could-have)
- **Dependencies** on existing features

### 3. Non-Functional Requirements

- Performance expectations
- Security considerations
- Usability requirements
- Compatibility constraints

### 4. Quality Validation

Ensure each requirement is:

- **Specific**: Clearly defined with no ambiguity
- **Testable**: Can be verified through testing
- **Complete**: Covers all necessary functionality
- **Consistent**: Aligns with existing system capabilities

## Output Guidelines

- Use clear, professional language
- Focus on user and system behavior
- Avoid implementation details (save for design phase)
- Reference existing codebase patterns when relevant
- Include source citations if research was conducted

Generate requirements that provide a solid foundation for the technical design phase.
