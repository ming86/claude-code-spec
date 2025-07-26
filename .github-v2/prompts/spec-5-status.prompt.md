---
description: Show specification status and progress
mode: agent
tools: ['search', 'codebase', 'editFiles']
---

# Specification Status

Show current status and progress for feature: **${input:feature:Enter feature name}**

## Spec Context

### Spec Files

Use `search` tool to analyze:

- Spec directory: `.spec-workflow/specs/${input:feature}/`
- Spec metadata: [spec.yaml](../../.spec-workflow/specs/${input:feature}/spec.yaml)
- Requirements: [requirements.md](../../.spec-workflow/specs/${input:feature}/requirements.md)
- Design: [design.md](../../.spec-workflow/specs/${input:feature}/design.md)
- Tasks: [tasks.md](../../.spec-workflow/specs/${input:feature}/tasks.md)

### All Specs Overview

Use `search` tool to find:

- Available specs: Check `.spec-workflow/specs/` directory
- Active specs: Look for specifications with `ready_for_implementation: true`

## Task: Generate Status Report

Create comprehensive status report for the specification in the language specified in spec.yaml (check language field):

### 1. Specification Overview

Display:

- Feature name and description
- Creation date and last update
- Current phase (requirements/design/tasks/implementation)
- Overall completion percentage

### 2. Phase Status

For each phase, show:

- ✅ **Requirements Phase**: [completion %]

  - Requirements count: [number]
  - Acceptance criteria defined: [yes/no]
  - Requirements coverage: [complete/partial/missing]

- ✅ **Design Phase**: [completion %]

  - Architecture documented: [yes/no]
  - Components defined: [yes/no]
  - Diagrams created: [yes/no]
  - Integration planned: [yes/no]

- ✅ **Tasks Phase**: [completion %]
  - Total tasks: [number]
  - Completed tasks: [number]
  - Remaining tasks: [number]
  - Blocked tasks: [number]

### 3. Implementation Progress

If in implementation phase:

- Task completion breakdown
- Current blockers or issues
- Estimated time to completion
- Next actions needed

#### Task Completion Tracking

- Parse tasks.md checkbox status: `- [x]` (completed) vs `- [ ]` (pending)
- Count completed vs total tasks
- Show completion percentage
- Identify next uncompleted task

### 4. Quality Metrics

Show:

- Requirements coverage: [percentage]
- Design completeness: [percentage]
- Task granularity: [appropriate/too large/too small]
- Dependencies resolved: [yes/no]

### 5. Recommendations

Based on status, provide:

- Next steps to take
- Potential issues to address
- Suggested improvements
- Missing elements to complete

### 6. Steering Alignment

Check alignment with steering documents:

- Architecture consistency: [aligned/misaligned]
- Technology stack compliance: [compliant/non-compliant]
- Product requirements alignment: [aligned/misaligned]

## Refinement Options

What would you like me to refine about this status report?

- **Update scope**: Include different metrics or status indicators?
- **Detail level**: More detailed analysis or simpler overview?
- **Focus area**: Emphasize specific phases or aspects?
- **Format**: Different presentation or organization?
- **Proceed if satisfied** with status report?

I can iterate on the status report in our conversation until you're satisfied.

## Instructions

1. **Check spec.yaml for language** - Use the language specified in the metadata
2. **Parse all spec files** to understand current state
3. **Calculate completion percentages** for each phase
4. **Identify next actions** based on current progress
5. **Highlight any blockers** or issues
6. **Provide clear recommendations** for moving forward
7. **Check steering alignment** to ensure consistency

Generate status report that provides clear visibility into spec progress and next steps.
