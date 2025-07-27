# GitHub Copilot Transformation Implementation Handoff

## Project Overview

Transform the existing Claude Code Kiro-style spec-driven development workflow into GitHub Copilot native prompt files. This maintains the structured 3-phase approval workflow while making it project-agnostic and compatible with GitHub Copilot's capabilities.

## Source Material

Transform the existing command implementations located in:

- `C:\viewGithub\claude-code-spec\.claude\commands\kiro\spec-init.md`
- `C:\viewGithub\claude-code-spec\.claude\commands\kiro\spec-requirements.md`
- `C:\viewGithub\claude-code-spec\.claude\commands\kiro\spec-design.md`
- `C:\viewGithub\claude-code-spec\.claude\commands\kiro\spec-tasks.md`
- `C:\viewGithub\claude-code-spec\.claude\commands\kiro\spec-status.md`
- `C:\viewGithub\claude-code-spec\.claude\commands\kiro\steering.md`
- `C:\viewGithub\claude-code-spec\.claude\commands\kiro\steering-custom.md`

## Target Structure

Create the following directory structure:

```
project/
├── .spec-workflow/
│   ├── steering/
│   │   ├── product.md
│   │   ├── tech.md
│   │   └── structure.md
│   └── specs/
│       └── [feature-name]/
│           ├── spec.yaml
│           ├── requirements.md
│           ├── design.md
│           └── tasks.md
├── .github/
│   ├── prompts/
│   │   ├── spec-0-steering.prompt.md
│   │   ├── spec-0-steering-custom.prompt.md
│   │   ├── spec-1-init.prompt.md
│   │   ├── spec-2-requirements.prompt.md
│   │   ├── spec-3-design.prompt.md
│   │   ├── spec-4-tasks.prompt.md
│   │   └── spec-5-status.prompt.md
│   └── instructions/
│       ├── spec-user-story-template.instructions.md
│       ├── spec-design-template.instructions.md
│       └── spec-task-template.instructions.md
```

## Key Transformations Required

### 1. Directory Path Changes

Replace all path references in the original commands:

- `.kiro/steering/` → `.spec-workflow/steering/`
- `.kiro/specs/` → `.spec-workflow/specs/`
- All file path references must be updated accordingly

### 2. Metadata Format Change

Convert from `spec.json` to `spec.yaml`:

```yaml
# spec.yaml structure
feature_name: feature-name
project_description: |
  Multi-line project description
created_at: timestamp
updated_at: timestamp
phase: current-phase
approvals:
  requirements:
    generated: boolean
    approved: boolean
  design:
    generated: boolean
    approved: boolean
  tasks:
    generated: boolean
    approved: boolean
progress:
  requirements: percentage
  design: percentage
  tasks: percentage
ready_for_implementation: boolean
```

### 3. Prompt File Structure

Each `.prompt.md` file should have this frontmatter:

```markdown
---
description: Brief description from original command
mode: 'agent'
tools: ['codebase', 'workspace', 'terminal']
---
```

### 4. Variable System

Replace `$ARGUMENTS` with `${input:feature:Description}` or `${input:description:Description}` as appropriate.

### 5. Cross-Reference Implementation

Add markdown link references between related files:

- Reference previous workflow steps
- Reference steering documents
- Reference instruction templates
- Reference current spec files

## Implementation Tasks

### Task 1: Create Numbered Prompt Files

#### spec-0-steering.prompt.md

- Transform `steering.md`
- Update paths to `.spec-workflow/steering/`
- Add frontmatter with agent mode and tools
- Remove language-specific instructions (keep English only)

#### spec-0-steering-custom.prompt.md  

- Transform `steering-custom.md`
- Update paths to `.spec-workflow/steering/`
- Add frontmatter with agent mode and tools

#### spec-1-init.prompt.md

- Transform `spec-init.md`
- Replace `$ARGUMENTS` with `${input:description:Detailed project description}`
- Update all `.kiro/` paths to `.spec-workflow/`
- Change `spec.json` references to `spec.yaml`
- Add cross-references to steering files
- Update template generation to use YAML format

#### spec-2-requirements.prompt.md

- Transform `spec-requirements.md`
- Replace `$ARGUMENTS` with `${input:feature:Feature name}`
- Update all path references
- Change metadata updates to YAML format
- Add cross-references to spec-1 and steering files
- Remove language detection logic (English only)

#### spec-3-design.prompt.md

- Transform `spec-design.md` (you will need to read this file)
- Follow same transformation pattern as requirements
- Add cross-references to requirements and steering
- Update metadata tracking to YAML

#### spec-4-tasks.prompt.md

- Transform `spec-tasks.md` (you will need to read this file)
- Follow same transformation pattern
- Add cross-references to design and requirements
- Update metadata tracking to YAML

#### spec-5-status.prompt.md

- Transform `spec-status.md`
- Replace `$ARGUMENTS` with `${input:feature:Feature name}`
- Update path references and YAML parsing
- Add cross-references to all other prompts
- Update progress calculation for YAML format

### Task 2: Create Instruction Templates

Extract reusable templates from the original commands and create:

#### spec-user-story-template.instructions.md

- Extract user story format from `spec-requirements.md`
- Include acceptance criteria structure
- No frontmatter needed for instruction files

#### spec-design-template.instructions.md

- Extract design document structure from `spec-design.md`
- Include architecture patterns and component guidelines

#### spec-task-template.instructions.md

- Extract task breakdown format from `spec-tasks.md`
- Include progress tracking checkbox format

### Task 3: Implementation Constraints

1. **Preserve Original Logic**: Only transform existing functionality, do not add new features
2. **No Emojis**: Remove all emoji usage from original commands
3. **English Only**: Remove Japanese language support and multi-language logic
4. **Project Agnostic**: Remove Kiro-specific references, make generic
5. **Cross-References**: Add markdown link references between related files using syntax: `[Description](#path/to/file.md)`
6. **Variable Interpolation**: Use `${input:variable:description}` for user inputs
7. **Workspace Variables**: Use `${workspaceFolder}` where appropriate
8. **YAML Format**: All metadata operations use YAML instead of JSON

### Task 4: Quality Assurance

1. Verify all path references point to `.spec-workflow/` structure
2. Ensure all `spec.json` references are changed to `spec.yaml`
3. Confirm frontmatter is consistent across all prompt files
4. Validate cross-reference syntax is correct
5. Check that variable interpolation syntax is proper
6. Remove any emoji characters from all files
7. Ensure approval workflow logic is preserved

## File Reading Requirements

You must read these files to complete the transformation:

- `C:\viewGithub\claude-code-spec\.claude\commands\kiro\spec-design.md`
- `C:\viewGithub\claude-code-spec\.claude\commands\kiro\spec-tasks.md`

These contain the specific logic for design and task generation that must be preserved in the transformation.

## Expected Deliverables

1. Seven `.prompt.md` files in `.github/prompts/`
2. Three `.instructions.md` files in `.github/instructions/`
3. All files should be ready for immediate use with GitHub Copilot
4. Preserve all approval workflow logic and quality gates
5. Maintain project-agnostic approach with intelligent context discovery

## Success Criteria

The implementation is complete when:

1. All original command functionality is preserved
2. Prompts can be invoked via `/spec-1-init: description` syntax
3. Cross-references work correctly
4. YAML metadata format is properly implemented
5. Approval workflow gates function as designed
6. No emojis or language-specific code remains
7. Directory structure outputs to `.spec-workflow/` correctly
