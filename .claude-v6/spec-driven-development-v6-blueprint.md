# Spec-Driven Development v6: Technical Blueprint

## Technical Problem Statement

Software development frequently encounters three critical failures:

1. **Scope Expansion**: Features grow beyond original requirements during implementation, creating maintenance debt
2. **Context Loss**: Complex development workflows lose coherence across phase transitions
3. **Quality Inconsistency**: Ad-hoc development approaches produce inconsistent outcomes and technical debt

## Architectural Solution: Surgical Consolidation

### Core Innovation

**Surgical Consolidation** eliminates context loading dependencies while maintaining complete functionality through precise knowledge distribution. Each phase receives exactly the domain expertise required for its role, preventing cross-phase contamination and scope expansion.

### Consolidation Levels

#### ZERO Consolidation (Standalone Utilities)

- **Purpose**: Independent project analysis tools
- **Knowledge Scope**: Project structure, technology detection, file organization
- **Boundary**: No methodology knowledge, no workflow dependencies
- **Examples**: Project steering generation, custom domain analysis

#### MINIMAL Consolidation (Basic Integration)

- **Purpose**: Simple setup and reporting utilities
- **Knowledge Scope**: Basic project understanding, file structure, progress calculation
- **Boundary**: No methodology details, no implementation knowledge
- **Examples**: Specification initialization, status reporting

#### SURGICAL Consolidation (Methodology Precision)

- **Purpose**: Single methodology application without contamination
- **Knowledge Scope**: USDD → EARS transformation only
- **Boundary**: No design knowledge, no implementation planning
- **Examples**: Requirements clarification

#### COMPREHENSIVE Consolidation (Complete Domain Expertise)

- **Purpose**: Complex phases requiring full technical knowledge
- **Knowledge Scope**: Complete domain expertise + critical scope control warnings
- **Boundary**: All relevant knowledge for phase + strict scope enforcement
- **Examples**: Technical design, implementation planning, task execution

## Methodology Pipeline: USDD → EARS → SDD

### User Story Driven Development (USDD)

**Purpose**: Transform vague feature descriptions into clear user value understanding

**Process**:

1. Systematic analysis regardless of apparent clarity
2. Generate "As a [persona], I want [intent], so that [value]" format
3. Explore personas, use cases, contexts, underlying problems
4. Focus on who benefits and what problem is solved

### Easy Approach to Requirements Syntax (EARS)

**Purpose**: Convert user stories into precise, testable requirements

**Format Standards**:

- Primary: `WHEN [condition] THEN [response]`
- Extended: `GIVEN [context] WHEN [action] THEN [outcome]`
- Quality Requirements: Specific, measurable conditions and outcomes
- Validation: Clear pass/fail conditions for each requirement

### Specification-Driven Development (SDD)

**Purpose**: Disciplined implementation following approved specifications

**Workflow**:

1. Requirements → Design → Implementation Plan → Execution
2. Sequential approval gates prevent scope expansion
3. Each phase builds only on approved previous phases
4. Strict traceability from requirements to implementation

## Command Architecture

### Command Structure Pattern

```yaml
---
description: 'Phase-specific technical description'
argument-hint: '[parameters]'
---

# Role and Objective
[Clear purpose aligned with consolidation level]

# Instructions
[Phase-specific methodology with anti-shortcut patterns]

# Execution Steps
[Systematic workflow for phase completion]

# Quality Standards
[Validation requirements and success criteria]
```

### Phase Isolation Implementation

Each command maintains strict boundaries:

**Information Flow**: One-directional from previous phases
**Knowledge Scope**: Limited to consolidation level requirements
**Scope Control**: Explicit warnings against feature expansion
**Quality Gates**: Validation requirements before phase progression

## Technical Implementation Details

### File Structure Pattern

```
.spec-workflow/
└── specs/
    └── {feature-name}/
        ├── spec.yaml           # Metadata and approval tracking
        ├── requirements.md     # EARS-format requirements
        ├── design.md          # Technical architecture
        └── tasks.md           # Implementation plan
```

### Metadata Schema (spec.yaml)

```yaml
feature_name: "{kebab-case-name}"
project_description: "{user-input}"
created_at: "{iso-timestamp}"
updated_at: "{iso-timestamp}"
language: "english"
phase: "{current-phase}"
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
task_summary:
  total_tasks: integer
  estimated_hours: integer
  phases: integer
```

### Approval Workflow Implementation

```
Phase 1: Init → generates templates
Phase 2: Requirements → requires approval before design
Phase 3: Design → requires requirements approval before generation
Phase 4: Implementation → requires design approval before generation  
Phase 5: Execution → requires implementation approval before execution
Phase 6: Status → independent analysis capability
```

## Scope Control System

### Critical Control Points

#### Design Phase

```
⚠️ FEATURE EXPANSION IS STRICTLY FORBIDDEN
- MUST address ONLY approved requirements
- MUST trace every design element back to approved requirement
- RESEARCH enhances implementation of existing requirements only
```

#### Implementation Planning

```
⚠️ FEATURE EXPANSION CREATES SERIOUS MAINTENANCE BURDEN
- MUST generate tasks ONLY for approved requirements
- MUST trace every task back to approved requirement  
- MUST NOT add optimizations beyond approved scope
```

#### Task Execution

```
⚠️ TASK EXECUTION IS WHERE SCOPE CREEP MOST COMMONLY OCCURS
- EXECUTE ONLY the specific task requirements
- RESIST developer instincts to add features during coding
- FOLLOW acceptance criteria exactly
```

### Enforcement Mechanisms

**Requirement Traceability**: Every task maps to specific requirement (REQ-X.X format)
**Acceptance Criteria**: Specific, measurable completion conditions
**Progress Tracking**: Immediate checkbox updates in tasks.md
**Quality Validation**: Verification against approved specifications only

## Anti-Shortcut Quality Patterns

### Pattern Categories

#### Analysis-First Patterns

- "Analyze existing codebase rather than making assumptions"
- "Use project-specific information, not generic templates"
- "Follow systematic analysis regardless of apparent clarity"

#### Context-Safety Patterns  

- "Read existing files before editing"
- "Re-read tasks.md before each new task"
- "Validate against actual project patterns"

#### Scope-Discipline Patterns

- "Implement only task specifications"
- "Document additional ideas separately"
- "Trace every element back to approved requirements"

## Technical Benefits

### Reliability Improvements

- **Context Safety**: Re-reading tasks.md prevents context loss
- **Phase Isolation**: Prevents knowledge contamination between phases
- **Scope Control**: Multiple enforcement points prevent feature expansion

### Maintainability Improvements

- **Single Responsibility**: Each command has precisely defined role
- **Clean Dependencies**: Sequential workflow with clear approval gates
- **Traceability**: Complete mapping from requirements to implementation

### Quality Improvements

- **Systematic Methodology**: USDD → EARS → SDD pipeline prevents ad-hoc approaches
- **Anti-Shortcut Enforcement**: Quality patterns prevent common developer shortcuts
- **Measurable Outcomes**: EARS format provides testable acceptance criteria

## Implementation Specifications

### Command Naming Convention

```
0-steering.md                    # Project analysis
0-steering-custom.md             # Domain-specific steering  
1-init.md                        # Specification initialization
2-requirements-clarification.md  # USDD → EARS transformation
3-design-document.md             # Technical architecture
4-implementation-plan.md         # Task breakdown
5-task-execution.md              # Implementation execution
6-status.md                      # Progress analysis
```

### Task Sizing Standards

- **Optimal Range**: 2-4 hours focused development work
- **Breakdown Rules**: Large tasks split into manageable components
- **Validation**: Each task includes specific acceptance criteria

### Progress Tracking Protocol

```
1. Read tasks.md to understand current state
2. Execute task following specification exactly  
3. Mark task complete with [x] immediately
4. Continue to next task in sequence
5. Provide completion summary when all tasks done
```

## Quality Validation Framework

### Requirements Quality Metrics

- **EARS Compliance**: Percentage using WHEN/THEN format
- **Acceptance Coverage**: Requirements with testable criteria
- **Traceability**: All requirements mapped to implementation tasks

### Implementation Quality Metrics

- **Task Completion**: Percentage of implementation tasks completed
- **Scope Compliance**: Implementation limited to approved requirements
- **Pattern Consistency**: Code follows existing project conventions

### Workflow Quality Metrics

- **Phase Completion**: Sequential progression through approval gates
- **Context Safety**: Proper task state management and continuation
- **Documentation Accuracy**: Specifications reflect actual implementation

## Technical Architecture Summary

**v6 Framework Architecture**:

- **8 Self-Contained Commands**: Each with precise consolidation level
- **Sequential Workflow**: Approval gates prevent premature progression
- **Surgical Knowledge Distribution**: Each phase gets exactly required expertise
- **Multiple Scope Control Points**: Warnings and enforcement at critical phases
- **Systematic Methodology**: USDD → EARS → SDD pipeline prevents ad-hoc development
- **Quality Pattern Enforcement**: Anti-shortcut patterns maintain development standards

This architecture eliminates common development failures through systematic methodology application, precise knowledge boundaries, and multi-layered scope control while maintaining workflow flexibility and developer productivity.
