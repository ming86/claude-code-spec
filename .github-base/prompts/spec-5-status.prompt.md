---
description: Spec-Driven Development Step 5 - Show specification status and progress for a feature
mode: agent
tools: ['changes', 'codebase', 'findTestFiles', 'problems', 'runCommands', 'runTasks', 'search', 'searchResults', 'terminalLastCommand', 'terminalSelection', 'testFailure', 'usages']
---

# Specification Status Report

Show current status and progress for feature: **${input:feature:Enter feature name}**

## Specification Context

### Spec Files Analysis

First, verify the specification exists and analyze its current state:

- Spec directory: Check `.spec-workflow/specs/${input:feature}/`
- Spec metadata: Reference `.spec-workflow/specs/${input:feature}/spec.yaml`
- Requirements: Reference `.spec-workflow/specs/${input:feature}/requirements.md`
- Design: Reference `.spec-workflow/specs/${input:feature}/design.md`
- Tasks: Reference `.spec-workflow/specs/${input:feature}/tasks.md`

### All Specs Overview

- Available specs: Check `.spec-workflow/specs/` directory
- Active specs: Look for specifications with `ready_for_implementation: true`

## Status Report Generation

Create comprehensive status report for the specification:

### 1. Specification Overview

Display:

- Feature name and description
- Creation date and last update
- Current phase in the workflow
- Overall progress percentage

### 2. Phase Progress Analysis

For each phase, show:

#### Requirements Phase

- **Status**: Generated? Approved?
- **Progress**: Percentage complete
- **Files**: requirements.md status
- **Next Action**: What needs to be done

#### Design Phase

- **Status**: Generated? Approved?
- **Progress**: Percentage complete
- **Files**: design.md status
- **Dependencies**: Requirements approval required
- **Next Action**: What needs to be done

#### Tasks Phase

- **Status**: Generated? Approved?
- **Progress**: Percentage complete
- **Files**: tasks.md status
- **Dependencies**: Design approval required
- **Next Action**: What needs to be done

### 3. Task Completion Tracking

If tasks are generated, analyze task completion:

- Count total tasks vs completed tasks
- Show completion percentage
- Identify next pending tasks
- Display task dependencies

### 4. Workflow Status Summary

Show current workflow state:

- Current phase and what's needed to advance
- Approval gates status
- Implementation readiness
- Recommended next steps

### 5. Cross-Reference Navigation

Provide navigation to relevant workflow steps:

- **If needs requirements**: Point to #spec-2-requirements.prompt.md
- **If needs design**: Point to #spec-3-design.prompt.md
- **If needs tasks**: Point to #spec-4-tasks.prompt.md
- **If ready for implementation**: Indicate implementation can begin

## Quality Metrics

Include quality assessment:

- Specification completeness
- Approval gate compliance
- Documentation quality indicators
- Workflow adherence

## Output Format

Present status in clear, structured format:

```markdown
# Specification Status: {feature-name}

## Overview

- **Created**: {creation-date}
- **Last Updated**: {update-date}
- **Current Phase**: {current-phase}
- **Overall Progress**: {progress-percentage}%

## Phase Status

### Requirements

- Status: Generated [DONE] | Approved [DONE]
- Progress: 100%
- Next: Proceed to design

### Design

- Status: Generated [DONE] | Approved [PENDING]
- Progress: 80%
- Next: Human review and approval required

### Tasks

- Status: Not started
- Progress: 0%
- Next: Awaiting design approval

## Implementation Readiness

- Ready for Implementation: [NO]
- Blocking Issue: Design approval required
- Recommended Action: Review and approve design.md

## Next Steps

1. Review `.spec-workflow/specs/{feature}/design.md`
2. Update spec.yaml to approve design
3. Generate tasks using #spec-4-tasks.prompt.md
```

## Implementation Instructions

### Execution Steps:

1. **Verify specification exists** - Check that the feature directory and files exist
2. **Parse metadata** from spec.yaml to understand current state
3. **Analyze each phase** for generation and approval status
4. **Calculate progress** based on completed phases and tasks
5. **Identify blockers** and next required actions
6. **Provide navigation** to appropriate next steps
7. **Present clear summary** of current status and recommendations

### Analysis Guidelines:

- Show clear visual indicators ([DONE] [PENDING] [WAITING] [NOT_STARTED]) for status
- Calculate accurate progress percentages
- Identify specific blocking issues
- Provide actionable next steps
- Include cross-references to relevant prompts

## Cross-References

This prompt works within the spec-driven development workflow:

- **All workflow steps**: Can reference any phase for status checking
- **Related prompts**: #spec-1-init.prompt.md, #spec-2-requirements.prompt.md, #spec-3-design.prompt.md, #spec-4-tasks.prompt.md

## Error Handling

Handle common scenarios:

- **Specification not found**: Provide guidance to create with #spec-1-init.prompt.md
- **Incomplete metadata**: Show what information is missing
- **Corrupted files**: Identify issues and suggest corrections
- **Multiple specs**: Provide overview of all specifications if no specific feature requested

This status report provides comprehensive visibility into the spec-driven development process, helping users understand current progress and next steps.
