---
description: Spec-Driven Development Step 1 - Initialize a new specification with detailed project description and requirements
mode: agent
tools: ['changes', 'codebase', 'editFiles', 'extensions', 'problems', 'runCommands', 'runTasks', 'search', 'searchResults', 'terminalLastCommand', 'terminalSelection', 'testFailure', 'usages', 'get_syntax_docs', 'mermaid-diagram-preview', 'mermaid-diagram-validator']
---

# Specification Initialization

Initialize a new specification based on the provided project description: **${input:description:Enter detailed project description}**

## Steering Context Validation

First, validate the availability of steering documents to provide project context:

### Check Steering Documents

Reference steering documents if available:

- Structure context: #.spec-workflow/steering/structure.md
- Technical constraints: #.spec-workflow/steering/tech.md
- Product context: #.spec-workflow/steering/product.md

### Verify Steering Status

Check if `.spec-workflow/steering/` directory exists and contains steering files.

**FLEXIBILITY**: For new features or empty projects, steering documents are recommended but not required. If steering documents are missing or empty, you may proceed directly to spec generation phase.

## Specification Initialization Process

**SCOPE**: This prompt initializes the directory structure and metadata based on the detailed project description provided.

### 1. Analyze Project Description

From the provided description, extract:

- Project purpose and goals
- Key features and functionality
- Target users or use cases
- Technical requirements or constraints
- Any specific implementation details mentioned

### 2. Generate Feature Name

Based on the analysis, create a concise, descriptive feature name that captures the essence of the project.

### 3. Create Spec Directory

Create `.spec-workflow/specs/{generated-feature-name}/` directory with template files:

- `requirements.md` - Empty template for user stories
- `design.md` - Empty template for technical design
- `tasks.md` - Empty template for implementation tasks
- `spec.yaml` - Metadata and approval tracking

### 4. Initialize spec.yaml Metadata

Create initial metadata with approval tracking and project description:

```yaml
feature_name: "{generated-feature-name}"
project_description: "${input:description}"
created_at: "{current_timestamp}"
updated_at: "{current_timestamp}"
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
progress:
  requirements: 0
  design: 0
  tasks: 0
ready_for_implementation: false
```

### 5. Create Template Files with Project Context

#### requirements.md (Template with Context)

```markdown
# Requirements Document

## Project Overview

{Brief summary of the project based on the provided description}

## Project Description (User Input)

${input:description}

## Requirements

<!-- Detailed user stories will be generated in spec-2-requirements phase -->

---

**STATUS**: Ready for requirements generation
**NEXT STEP**: Run #spec-2-requirements.prompt.md to generate detailed requirements
```

#### design.md (Empty Template)

```markdown
# Design Document

## Overview

<!-- Technical design will be generated after requirements approval -->

---

**STATUS**: Waiting for requirements approval
**NEXT STEP**: Complete and approve requirements first
```

#### tasks.md (Empty Template)

```markdown
# Implementation Plan

<!-- Implementation tasks will be generated after design approval -->

---

**STATUS**: Waiting for design approval  
**NEXT STEP**: Complete and approve design first
```

## Spec-Driven Development Workflow

After initialization, follow the proper spec-driven development workflow:

### Standard 3-Phase Approval Workflow:

1. **Generate requirements**: Use #spec-2-requirements.prompt.md
2. **Review and approve requirements**: Update spec.yaml manually
3. **Generate design**: Use #spec-3-design.prompt.md (after requirements approval)
4. **Review and approve design**: Update spec.yaml manually
5. **Generate tasks**: Use #spec-4-tasks.prompt.md (after design approval)
6. **Review and approve tasks**: Update spec.yaml manually
7. **Start implementation**: After all approvals are complete

### Key Principles:

- Each phase requires explicit human approval before proceeding to the next phase
- Manual approval ensures quality and accuracy throughout the development process
- No skipping phases: Design requires approved requirements; Tasks require approved design

## Implementation Instructions

### Execution Steps:

1. **Parse project description** - Extract key information from the detailed description
2. **Generate appropriate feature name** - Create a concise, descriptive name
3. **Check steering documents** - Reference if available, but not required for new features
4. **Create directory structure** - Include project context in templates
5. **Set up approval tracking** in metadata with project description
6. **Provide clear next steps** for the user with the generated feature name
7. **Enable flexible workflow** - Allow direct progression to requirements when appropriate

### Output Format

After initialization, provide:

1. Generated feature name and rationale
2. Brief project summary
3. Created file paths
4. Clear next steps with cross-references to the appropriate prompt files

## Quality Guidelines

- Use clear, descriptive feature names that reflect the project essence
- Ensure all template files include appropriate status indicators
- Maintain consistent markdown formatting across all generated files
- Include cross-references to related workflow steps using #-references
- Document the project description context for future reference

This initialization process ensures proper spec-driven development workflow with mandatory review phases between each step, providing a solid foundation for structured development while maintaining flexibility for different project contexts.
