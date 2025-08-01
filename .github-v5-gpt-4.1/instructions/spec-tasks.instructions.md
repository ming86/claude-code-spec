---
description: Task structure and implementation planning standards
applyTo: ".spec-workflow/**/tasks.md"
---

# Task Planning Standards

Standards for task structure and implementation planning in the spec-driven development workflow.

## Task Structure Requirements

### Mandatory Task Focus

- **MUST focus on coding tasks only** (writing, modifying, testing code)
- **MUST exclude deployment/user testing tasks**
- **MUST reference specific requirements** for each task (_Requirements: 1.1, 2.3_)
- **MUST use hierarchical numbering** (1.1, 1.2, 2.1, 2.2 - max 2 levels)

### Task Quality Standards

- **Each task should be completable in 2-4 hours**
- **Include clear acceptance criteria for task completion**
- **Specify required files and components**
- **Include testing requirements where applicable**

## Task Transformations

Transform non-coding tasks to coding equivalents:

- **"Deploy to production"** → "Create deployment configuration files"
- **"User acceptance testing"** → "Create automated test suite"
- **"Performance monitoring"** → "Add performance logging to code"
- **"Marketing tasks"** → "Create technical documentation"

These standards ensure tasks focus on actionable coding work with clear structure and requirement traceability.
