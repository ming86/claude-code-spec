---
description: 'Initialize specification structure and directories for new feature development'
argument-hint: '[feature-description]'
---

# Role and Objective

Initialize comprehensive foundational directory structure and metadata files for spec-driven development workflow, ensuring proper phase tracking, approval gates, and integration with existing project architecture.

# Instructions

## Initialization Strategy

- **Feature Naming**: Generate meaningful, specific names using kebab-case format
- **Structure Validation**: Ensure no conflicts with existing spec directories
- **Metadata Accuracy**: Create properly formatted spec.yaml with correct phase tracking
- **Integration Focus**: Align spec structure with existing project patterns and conventions
- **Template Quality**: Create informative template files with clear next-step guidance

## Anti-Shortcut Quality Patterns

- Analyze existing project structure and patterns rather than using generic templates
- Generate feature names based on systematic analysis of provided descriptions, not assumptions
- Create project-specific template content based on actual codebase context
- Validate against existing specifications to prevent naming conflicts

# Execution Steps

## 1. Comprehensive Project Context Analysis

**Objective**: Build complete understanding of project architecture, constraints, and development patterns

**Process**:

- Examine code patterns, architectural approaches, and implementation examples
- Identify existing steering documents for project context and constraints
- Check for existing specifications to understand naming conventions and avoid conflicts
- Analyze integration points where new features typically connect to existing systems
- Understand current development workflow, testing patterns, and deployment considerations
- Identify technology constraints, architectural boundaries, and established conventions

## 2. Feature Scope Analysis and Name Generation

**Objective**: Create meaningful, specific feature name that accurately represents scope and follows project conventions

**Process**:

- Parse provided description to identify core functionality, target users, and primary use cases
- Extract key concepts and functional boundaries from the description
- Generate descriptive feature name using kebab-case format following project conventions
- Ensure name is specific, meaningful, and avoids generic terms like "system" or "module"
- Validate against existing spec directories to prevent naming conflicts
- Confirm name accurately represents intended feature scope and boundaries

## 3. Spec Structure Creation and Configuration

**Objective**: Create complete specification workflow structure with proper metadata and phase tracking

**Process**:

- Create .spec-workflow/specs/{feature-name}/ directory structure ensuring parent directories exist
- Generate spec.yaml metadata file with accurate timestamps, phase tracking, and approval workflow configuration
- Create requirements.md template with project context, user description, and clear next-step guidance
- Create design.md template with proper approval dependencies and workflow sequencing
- Create tasks.md template with implementation planning structure and approval requirements
- Configure approval workflow with proper phase gates and sequential development requirements

## 4. Integration Verification and Guidance Generation

**Objective**: Ensure proper integration and provide comprehensive workflow guidance

**Process**:

- Verify directory structure integrates properly with existing project organization and version control
- Confirm spec.yaml metadata follows proper YAML formatting and contains all required fields
- Validate template files contain appropriate project-specific guidance and clear status indicators
- Generate comprehensive next steps guidance aligned with spec-driven development workflow
- Document project-specific considerations, integration points, and architectural notes
- Provide complexity assessment and development timeline estimates based on project analysis

# Output Requirements

## Directory Structure Target

```
.spec-workflow/
└── specs/
    └── ${feature-name}/
        ├── spec.yaml           (Metadata and phase tracking)
        ├── requirements.md     (Template - Ready for Phase 2)
        ├── design.md          (Template - Awaiting requirements approval)
        └── tasks.md           (Template - Awaiting design approval)
```

## Metadata Configuration (spec.yaml)

```yaml
feature_name: "{generated-feature-name}"
project_description: "{user-provided-description}"
created_at: "{current-timestamp}"
updated_at: "{current-timestamp}"
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

# Feature Naming System

## Systematic Naming Approach

### Analysis-Based Generation

1. **Extract Core Concepts**: Identify primary functionality from description
2. **Identify Scope Boundaries**: Determine what's included vs. excluded
3. **Consider Integration Context**: How feature relates to existing system
4. **Apply Naming Conventions**: Use kebab-case with descriptive, specific terms

### Validation Process

1. **Specificity Check**: Ensure name captures actual functionality, not generic terms
2. **Conflict Detection**: Verify no existing directories with same name
3. **Scope Alignment**: Confirm name matches intended feature boundaries
4. **Team Clarity**: Ensure name is meaningful to developers and users

## Examples of Systematic Naming

- **Input**: "Create a way for users to upload and process documents"
- **Analysis**: Core functionality is document upload + processing workflow
- **Generated**: "document-upload-processor" (aligned with project conventions)

- **Input**: "Add social login options to the authentication system"
- **Analysis**: Extending existing auth with social provider integration
- **Generated**: "social-auth-integration" (specific to social providers, clear scope)

# Quality Validation

## Completion Criteria Checklist

- [ ] Comprehensive project analysis completed
- [ ] Feature name generated using systematic approach and validated for conflicts
- [ ] Complete directory structure created with proper parent directory handling
- [ ] spec.yaml metadata file created with accurate timestamps and project context
- [ ] All template files created with project-specific guidance and clear status indicators
- [ ] Approval workflow configured with proper phase gates and sequential requirements
- [ ] Integration verified with existing project structure and conventions
- [ ] Next steps guidance provided with clear workflow instructions

## Template Content Validation

- [ ] All templates contain project-specific analysis findings (not generic placeholders)
- [ ] YAML metadata follows proper formatting with no syntax errors
- [ ] Feature name follows detected project conventions (kebab-case validated)
- [ ] Integration notes reflect actual codebase patterns discovered

# Template Examples

## Requirements.md Template

```markdown
# Requirements Document: {Feature Name}

## Project Overview

{Brief summary based on analysis and provided description}

## Project Description (User Input)

{user-provided-description}

## User Stories

<!-- Will contain: User stories that clarify who benefits and what problem is being solved -->

## EARS Requirements

<!-- Will contain: Formal requirements in WHEN [condition] THEN [response] format -->

## Project Context Analysis

### Integration Points

{identified-integration-points-from-codebase-analysis}

### Architectural Considerations

{relevant-architectural-constraints-and-opportunities}

### Technology Constraints

{identified-technology-stack-implications}

## Complexity Assessment

- **Estimated Complexity**: {simple|moderate|complex}
- **Key Technical Challenges**: {identified-challenges}
- **Required Skills**: {identified-expertise-requirements}
- **Estimated Timeline**: {timeline-estimate}

---

**STATUS**: Ready for user story clarification and EARS requirements generation
**NEXT STEP**: Use /spec:2-requirements to begin requirements generation workflow
**APPROVAL REQUIRED**: Human review and approval needed before proceeding to design phase
```

## Design.md Template

```markdown
# Design Document: {Feature Name}

## Overview

<!-- Will contain: Technical design and architecture specifications -->

## Architecture Integration

{notes-about-integration-with-existing-architecture}

## Technology Stack Alignment

{notes-about-compatibility-with-current-tech-stack}

---

**STATUS**: Waiting for requirements approval
**NEXT STEP**: Complete and approve requirements first using spec.yaml approval tracking
**REQUIREMENTS**: Requirements must be generated and approved before design phase can begin
```

## Tasks.md Template

```markdown
# Implementation Plan: {Feature Name}

## Implementation Overview

<!-- Will contain: Detailed implementation tasks with requirement traceability -->

## Development Workflow Integration

{notes-about-integration-with-existing-development-workflow}

---

**STATUS**: Waiting for design approval
**NEXT STEP**: Complete and approve design first using spec.yaml approval tracking
**REQUIREMENTS**: Design must be generated and approved before implementation planning can begin
```

# Examples

## Argument Handling

```bash
/spec:1-init "Create user authentication system with social login"
/spec:1-init "Add real-time notifications for user activities"
/spec:1-init "Implement payment processing with multiple providers"
```

## Feature Name Generation Process

1. **Input**: "Create a system for users to log in and manage their profiles"
2. **Analysis**: Core functionality is authentication and profile management
3. **Generated Name**: "user-profile-management"
4. **Validation**: Check against existing specs, ensure no conflicts
5. **Final Name**: "user-profile-management" (validated and ready)

## Project Integration Example

1. **Project Analysis**: "Analyzing detected project structure and architectural patterns..."
2. **Integration Notes**: "New feature should integrate with existing authentication patterns and component architecture..."
3. **Template Adaptation**: Include project-specific considerations based on detected technology stack
4. **Next Steps**: "Requirements phase should consider existing architectural patterns discovered during analysis..."

## Workflow Setup Example

```yaml
phase: "initialized"
approvals:
  requirements:
    generated: false # Ready for /spec:2-requirements
    approved: false # Requires human review after generation
  design:
    generated: false # Blocked until requirements approved
    approved: false # Sequential approval required
```

Create a comprehensive foundation for spec-driven development that integrates seamlessly with existing project architecture while providing clear workflow guidance for collaborative development.
