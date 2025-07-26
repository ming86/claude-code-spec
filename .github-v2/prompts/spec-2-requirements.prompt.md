---
description: Generate comprehensive requirements for a specification
mode: agent
tools: ['search', 'codebase', 'editFiles']
---

# Requirements Generation

Generate comprehensive requirements for feature: **${input:feature:Enter feature name}**

## Context Validation

### Steering Context

Reference steering documents if available:

- Architecture context: [structure.md](../../.spec-workflow/steering/structure.md)
- Technical constraints: [tech.md](../../.spec-workflow/steering/tech.md)
- Product context: [product.md](../../.spec-workflow/steering/product.md)

### Existing Spec Context

Verify the specification exists and is ready for requirements generation:

- Current spec directory: Use `search` tool to check `.spec-workflow/specs/${input:feature}/`
- Current requirements: [requirements.md](../../.spec-workflow/specs/${input:feature}/requirements.md)
- Spec metadata: [spec.yaml](../../.spec-workflow/specs/${input:feature}/spec.yaml)

## Task: Generate Detailed Requirements

Create comprehensive requirements document in the language specified in spec.yaml:

### 1. Requirements Structure

Generate requirements.md in the language specified in spec.yaml (check language field):

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

Update spec.yaml with:

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

### 5. Document Generation Only

Generate the requirements document content ONLY. Do not include any review or approval instructions in the actual document file.

## Refinement Options

What would you like me to refine about these requirements?

- **Adjust scope**: Add or remove requirement areas?
- **Modify detail level**: More detailed acceptance criteria or simpler stories?
- **Change user focus**: Different user types or personas?
- **Refine acceptance criteria**: More specific conditions or edge cases?
- **Update integration points**: Better alignment with existing systems?
- **Proceed if satisfied** with requirements?

I can iterate on the requirements in our conversation until you're satisfied.

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
4. **Only after approval** can /spec-3-design: feature={feature-name} be used

## Instructions

1. **Check spec.yaml for language** - Use the language specified in the metadata
2. **Analyze existing product context** to understand user needs
3. **Create user-focused requirements** with clear acceptance criteria
4. **Consider technical constraints** from steering documents
5. **Ensure requirements are testable** and specific
6. **Update tracking metadata** upon completion

Generate requirements that provide clear foundation for design phase.
