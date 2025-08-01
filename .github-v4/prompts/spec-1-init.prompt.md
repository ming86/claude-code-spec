---
description: Initialize a new specification with project analysis and structure setup
mode: agent
tools: ['codebase', 'search', 'editFiles']
---

# Specification Initialization

Initialize a new specification for: **${input:description:Enter detailed project description}**

## Standards and Guidelines

**Workflow Principles**: [Core Workflow Standards](../instructions/spec-workflow-general.instructions.md)

## Project Context Analysis

### Steering Documents Validation

Check for existing steering context:

- **Structure context**: `.spec-workflow/steering/structure.md`
- **Technical constraints**: `.spec-workflow/steering/tech.md`
- **Product context**: `.spec-workflow/steering/product.md`

**Note**: Steering documents are recommended but not required. For new features or projects without steering, proceed with specification generation.

### Codebase Analysis

Use codebase tool to understand:

- Existing architectural patterns
- Current technology stack
- Code organization conventions
- Integration points for new features

## Feature Name Generation

Based on the provided description, generate a concise, descriptive feature name that:

- Captures the essence of the project/feature
- Uses kebab-case format (e.g., "user-authentication")
- Is specific and meaningful
- Avoids generic terms

## Specification Structure Creation

### 1. Directory Setup

Create `.spec-workflow/specs/{generated-feature-name}/` with:

### 2. Specification Metadata (`spec.yaml`)

```yaml
feature_name: "{generated-feature-name}"
project_description: "${input:description}"
created_at: "{current_timestamp}"
updated_at: "{current_timestamp}"
language: "english"
phase: "initialized"
approvals:
  requirements:
    generated: false
    approved: false
  design:
    generated: false
    approved: false
  tasks:
    generated: false
    approved: false
```

### 3. Template Files Creation

#### Requirements Template (`requirements.md`)

```markdown
# Requirements Document

## Project Overview

{Brief summary based on provided description}

## Project Description (User Input)

${input:description}

## Requirements

<!-- Detailed user stories will be generated in requirements phase -->

---

**STATUS**: Ready for requirements generation
**NEXT STEP**: Use spec-requirements chat mode or prompt to generate detailed requirements
```

#### Design Template (`design.md`)

```markdown
# Design Document

## Overview

<!-- Technical design will be generated after requirements approval -->

---

**STATUS**: Waiting for requirements approval
**NEXT STEP**: Complete and approve requirements first
```

#### Tasks Template (`tasks.md`)

```markdown
# Implementation Plan

<!-- Implementation tasks will be generated after design approval -->

---

**STATUS**: Waiting for design approval
**NEXT STEP**: Complete and approve design first
```

## Project Analysis Summary

Provide analysis of:

### Feature Context

- How this feature fits with existing system
- Integration points identified
- Potential architectural considerations
- Technology constraints or opportunities

### Complexity Assessment

- Estimated complexity level (simple/moderate/complex)
- Key technical challenges identified
- Required skills or expertise
- Estimated development timeline

### Dependencies

- External system dependencies
- Internal feature dependencies
- Technology or library requirements
- Infrastructure considerations

## Next Steps Guidance

After initialization, follow the spec-driven development workflow:

### Standard Workflow

1. **Generate requirements**: Use spec-requirements chat mode
2. **Review and approve requirements**: Update spec.yaml approval status
3. **Generate design**: Use spec-design chat mode (after requirements approval)
4. **Review and approve design**: Update spec.yaml approval status
5. **Generate tasks**: Use spec-tasks chat mode (after design approval)
6. **Review and approve tasks**: Update spec.yaml approval status
7. **Start implementation**: Use spec-implementation chat mode

### Quality Gates

- Human review required between each phase
- Manual approval updates in spec.yaml
- No phase skipping allowed
- Each phase builds on the previous phase

## Implementation Notes

### Best Practices

- Provide detailed project descriptions for better analysis
- Review generated content and edit as needed
- Ensure steering documents exist for complex projects
- Follow the sequential approval workflow

### Flexibility

- Steering documents enhance but don't block initialization
- Templates can be customized based on project needs
- Workflow can be adapted for different project types

Create a solid foundation for spec-driven development with proper structure, metadata, and clear next steps.
