---
description: Initialize spec workflow structure and directories for new feature development
tools: ['editFiles', 'codebase']
---

# Spec Structure Initialization Mode

Initialize spec workflow for feature: **${input:feature:Enter feature name}**

## Purpose and Scope

**Primary Function**: Create the foundational directory structure and metadata files required for spec-driven development workflow, preparing the environment for subsequent specification phases.

**Initialization Tasks**:

- Create `.spec-workflow/specs/{feature}` directory structure
- Generate initial `spec.yaml` metadata file with proper configuration
- Set up phase tracking and approval workflow structure
- Establish file organization for requirements, design, and implementation phases

## Prerequisites Validation

### Feature Name Validation

Ensure valid feature naming:

- **Feature name format**: Use kebab-case (e.g., `user-authentication`, `payment-processing`)
- **No special characters**: Avoid spaces, underscores, or special symbols
- **Descriptive naming**: Name should clearly indicate the feature purpose
- **Unique naming**: Avoid conflicts with existing spec directories

### Project Structure Assessment

**Check existing structure**:

- Verify if `.spec-workflow` directory exists
- Review existing spec directories to avoid naming conflicts
- Assess current project organization using codebase tool
- Identify integration points with existing development workflow

## Initialization Process

### 1. Directory Structure Creation

**Create spec workflow structure**:

```
.spec-workflow/
└── specs/
    └── ${feature}/
        ├── spec.yaml           (Metadata and tracking)
        ├── requirements.md     (Placeholder - to be generated in Phase 2)
        ├── design.md          (Placeholder - to be generated in Phase 3)
        └── tasks.md           (Placeholder - to be generated in Phase 4)
```

**Directory creation sequence**:

1. **Create `.spec-workflow`** directory if it doesn't exist
2. **Create `.spec-workflow/specs`** directory if it doesn't exist
3. **Create `.spec-workflow/specs/${feature}`** directory for this specific feature
4. **Initialize placeholder files** for future phases

### 2. Spec Metadata Configuration

**Generate spec.yaml file**:

```yaml
# Spec metadata for feature: ${feature}
feature_name: "${feature}"
created_at: "{current_timestamp}"
updated_at: "{current_timestamp}"
version: "1.0.0"

# Workflow phase tracking
phase: "initialized"
current_step: "ready_for_requirements"

# Phase completion tracking
progress:
  initialization: 100
  requirements: 0
  design: 0
  implementation_plan: 0
  implementation: 0

# Approval workflow
approvals:
  requirements:
    generated: false
    approved: false
    approved_by: null
    approved_at: null
  design:
    generated: false
    approved: false
    approved_by: null
    approved_at: null
  implementation_plan:
    generated: false
    approved: false
    approved_by: null
    approved_at: null

# Feature metadata
description: "Feature: ${feature} - Initialized for spec-driven development"
priority: "medium"
complexity: "to_be_determined"
estimated_effort: "to_be_determined"

# Integration tracking
dependencies: []
affects_components: []
requires_testing: true
requires_documentation: true

# Development tracking
assigned_to: null
start_date: null
target_date: null
actual_completion: null

# Quality gates
quality_gates:
  requirements_review: "pending"
  design_review: "pending"
  implementation_review: "pending"
  testing_complete: "pending"
```

### 3. Placeholder File Generation

**Create phase placeholder files**:

**requirements.md placeholder**:

```markdown
# Feature Requirements: ${feature}

<!-- This file will be generated in Phase 2: Requirements Clarification -->
<!-- Use spec-2-requirements-clarification mode to generate content -->

**Status**: Pending generation
**Phase**: 2 - Requirements Clarification
**Next Action**: Run spec-2-requirements-clarification mode
```

**design.md placeholder**:

```markdown
# Technical Design: ${feature}

<!-- This file will be generated in Phase 3: Design Document -->
<!-- Use spec-3-design-document mode to generate content -->
<!-- Requires: requirements.md to be completed and approved -->

**Status**: Pending generation
**Phase**: 3 - Design Document
**Prerequisites**: Completed and approved requirements.md
**Next Action**: Run spec-3-design-document mode after requirements approval
```

**tasks.md placeholder**:

```markdown
# Implementation Tasks: ${feature}

<!-- This file will be generated in Phase 4: Implementation Plan -->
<!-- Use spec-4-implementation-plan mode to generate content -->
<!-- Requires: design.md to be completed and approved -->

**Status**: Pending generation
**Phase**: 4 - Implementation Plan
**Prerequisites**: Completed and approved design.md
**Next Action**: Run spec-4-implementation-plan mode after design approval
```

## Project Integration

### Workflow Integration

**Integration with existing project**:

- **Git Integration**: Ensure `.spec-workflow` is tracked in version control
- **Documentation**: Link to existing project documentation if present
- **Team Coordination**: Prepare for collaborative workflow phases
- **Tool Integration**: Ensure compatibility with existing development tools

### Development Environment Setup

**Environment preparation**:

- **Access Verification**: Ensure necessary file permissions for spec workflow
- **Directory Indexing**: Update any development tool configurations if needed
- **Documentation Updates**: Update project README or docs with spec workflow information

## Validation and Quality Checks

### Structure Validation

**Verify initialization success**:

- [ ] `.spec-workflow/specs/${feature}` directory exists
- [ ] `spec.yaml` file properly formatted and contains required metadata
- [ ] Placeholder files created with appropriate content
- [ ] Directory structure follows established conventions
- [ ] No conflicts with existing spec directories

### Metadata Validation

**Verify spec.yaml integrity**:

- [ ] Feature name correctly specified and formatted
- [ ] Timestamps properly set
- [ ] Phase tracking initialized correctly
- [ ] Approval workflow structure complete
- [ ] All required metadata fields present

### Integration Validation

**Verify project integration**:

- [ ] Directory structure integrates with existing project organization
- [ ] No conflicts with existing files or directories
- [ ] Git tracking configured appropriately
- [ ] Development environment compatibility maintained

## Next Steps Guidance

### Immediate Next Actions

After successful initialization:

1. **Review spec.yaml** metadata and adjust priority/complexity if known
2. **Update project documentation** to reflect new spec workflow
3. **Begin Phase 2**: Use `spec-2-requirements-clarification` mode to generate requirements
4. **Team coordination**: Inform team members of new spec workflow initiation

### Workflow Progression

**Recommended workflow sequence**:

1. ✅ **Phase 1 Complete**: Spec structure initialized
2. **Phase 2 Next**: Generate requirements using `spec-2-requirements-clarification`
3. **Phase 3 Future**: Generate design using `spec-3-design-document` (after requirements approval)
4. **Phase 4 Future**: Generate tasks using `spec-4-implementation-plan` (after design approval)
5. **Phase 5 Future**: Execute tasks using `spec-5-task-execution` (after tasks approval)

## Boundaries and Constraints

### What This Phase DOES

- ✅ Create `.spec-workflow/specs/${feature}` directory structure
- ✅ Generate initial `spec.yaml` metadata file
- ✅ Create placeholder files for future phases
- ✅ Set up approval workflow tracking structure
- ✅ Integrate with existing project structure

### What This Phase DOES NOT DO

- ❌ Generate actual requirements content (use spec-2-requirements-clarification)
- ❌ Create technical design documents (use spec-3-design-document)
- ❌ Generate implementation tasks (use spec-4-implementation-plan)
- ❌ Execute any implementation work (use spec-5-task-execution)
- ❌ Modify existing application code or configuration

## Completion Confirmation

After initialization completion:

**Provide initialization summary**:

- **Feature name**: ${feature}
- **Directory created**: `.spec-workflow/specs/${feature}/`
- **Files initialized**: `spec.yaml`, `requirements.md`, `design.md`, `tasks.md`
- **Current phase**: Initialized and ready for requirements generation
- **Next action**: Use `spec-2-requirements-clarification` mode to begin requirements phase

**Ready for spec-driven development workflow.**
