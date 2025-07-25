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

Create comprehensive requirements document following the user story template from #spec-user-story-template.instructions.md.

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
5. **Follow template structure** from #spec-user-story-template.instructions.md
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
