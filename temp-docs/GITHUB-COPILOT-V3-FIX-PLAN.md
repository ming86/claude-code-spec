# GitHub Copilot v3 Implementation Fix Plan

## 🚨 CRITICAL ISSUE IDENTIFIED

The current `.github-v3/` implementation **violates the core Kiro workflow principle** by mixing Phase 3 (Implementation Planning) with Phase 4 (Task Execution) in a single chat mode.

## Current Problems

### ❌ Incorrect Implementation in `.github-v3/`

**File**: `/Users/ming/GitRepos/github-ming86/claude-code-spec/.github-v3/chatmodes/spec-implementation.chatmode.md`

**Problem**: This file incorrectly combines:
- **Phase 3 activities**: "Parse tasks.md", "Analyze task requirements" 
- **Phase 4 activities**: "Use editFiles tool to make changes", "Implement functionality"

**This breaks the Kiro approval workflow!**

### ❌ Missing Critical Files

1. **Missing**: `spec-4-tasks.chatmode.md` (Phase 3: Implementation Planning)
2. **Missing**: `spec-execution.chatmode.md` (Phase 4: Task Execution) 
3. **Missing**: `spec-execute-task.prompt.md` (Individual task execution)

## Correct Kiro Workflow Reference

### **Original Kiro 4-Phase Structure**

Based on analysis in `/Users/ming/GitRepos/github-ming86/claude-code-spec/kiro-improvement-analysis.md`:

1. **Phase 1: Requirements Clarification** → generates `requirements.md`
2. **Phase 2: Design Document** → generates `design.md` 
3. **Phase 3: Implementation Plan** → generates `tasks.md` (task list creation)
4. **Phase 4: Task Execution** → executes individual tasks from the list

**Key Principle**: Each phase has **manual approval gates** before proceeding to next phase.

### **Original Kiro Files Reference**

Located at: `/Users/ming/GitRepos/github-ming86/amazon-kiro.kiro-agent-source-code-analysis/prompts/`

- `spec-requirements-clarification.md` (Phase 1)
- `spec-design-document.md` (Phase 2) 
- `spec-implementation-plan.md` (Phase 3) ← Creates task list only
- `spec-task-execution.md` (Phase 4) ← Executes individual tasks

## Required Fixes

### 1. Delete Incorrect File

**File to Delete**: `/Users/ming/GitRepos/github-ming86/claude-code-spec/.github-v3/chatmodes/spec-implementation.chatmode.md`

**Reason**: Violates phase separation by mixing planning and execution.

### 2. Create Missing Chat Modes

#### **A. Create `spec-4-tasks.chatmode.md` (Phase 3)**

**Purpose**: Implementation Planning - Create task list from approved design
**Focus**: Planning tasks ONLY, no execution
**Tools**: `['codebase', 'search']` (no editFiles - this is planning only)

**Key Instructions**:
- Focus on breaking design into numbered task list
- Each task 2-4 hours of coding work
- Use max 2-level hierarchy (1.1, 1.2, 2.1)
- Reference specific requirements for each task
- EXCLUDE non-coding tasks (deployment, user testing, monitoring)
- Transform excluded tasks to coding equivalents
- DON'T execute tasks - just plan them

#### **B. Create `spec-execution.chatmode.md` (Phase 4)**

**Purpose**: Task Execution - Execute individual coding tasks
**Focus**: Executing ONE task at a time, then STOP
**Tools**: `['codebase', 'editFiles', 'search', 'problems']`

**Key Instructions**:
- Execute ONLY the specified task number
- Write code, test, then STOP
- DON'T proceed to next task automatically
- Mark task complete in tasks.md
- Validate against requirements
- Self-correct issues automatically

### 3. Create Missing Prompt File

#### **Create `spec-execute-task.prompt.md`**

**Purpose**: Execute individual task with parameters
**Parameters**: `${input:feature:Enter feature name}`, `${input:taskNumber:Enter task number}`
**Mode**: `agent`
**Tools**: `['codebase', 'editFiles', 'search', 'problems']`

## Implementation Details

### Chat Mode Structure Template

Based on existing correct implementations in `.github-v3/chatmodes/`:

```markdown
---
description: [Clear description of phase purpose]
tools: [Appropriate tools for phase]
---

# [Phase Name] Mode

[Clear instructions focused on single phase]

## Prerequisites Validation
- Check previous phase approval in spec.yaml
- Verify required files exist

## Phase-Specific Guidelines
[Instructions that maintain phase focus]

## Quality Validation
[Ensure outputs meet phase requirements]

## Boundaries
- DON'T [activities from other phases]
- FOCUS ONLY on [current phase activities]
```

### File Locations and Structure

```
.github-v3/
├── chatmodes/
│   ├── spec-2-requirements.chatmode.md     ✅ (already correct)
│   ├── spec-3-design.chatmode.md           ✅ (already correct)
│   ├── spec-4-tasks.chatmode.md            ❌ (needs creation)
│   ├── spec-execution.chatmode.md          ❌ (needs creation)
│   ├── spec-implementation.chatmode.md     ❌ (DELETE - incorrect)
│   └── spec-status.chatmode.md             ✅ (keep as-is)
├── prompts/
│   ├── spec-2-requirements.prompt.md       ✅ (already correct)
│   ├── spec-3-design.prompt.md             ✅ (already correct)
│   ├── spec-4-tasks.prompt.md              ✅ (already correct)
│   ├── spec-execute-task.prompt.md         ❌ (needs creation)
│   └── [other existing prompts]            ✅ (keep as-is)
```

### Key Implementation References

**EARS Format Requirements** (from improvement analysis):
- Use "WHEN [condition] THEN [response]" format
- Include in Phase 1 (requirements) only

**Research Integration** (from improvement analysis):
- Mandatory research during Phase 2 (design)
- Use fetch tool for external research
- Include source citations

**Task Planning Principles** (from original Kiro):
- Focus ONLY on coding tasks
- Exclude deployment, user testing, monitoring
- Max 2-level hierarchy (1.1, 1.2, 2.1)
- Each task 2-4 hours
- Reference specific requirements

**Task Execution Discipline** (from original Kiro):
- ONE task at a time, then STOP
- Don't proceed automatically
- Validate against requirements
- Mark completion in tasks.md

## Content Sources for Implementation

### Templates to Reference

**For Phase 3 Chat Mode** (`spec-4-tasks.chatmode.md`):
- Use structure from: `/Users/ming/GitRepos/github-ming86/claude-code-spec/.github-v3/chatmodes/spec-3-design.chatmode.md`
- Content guidance from: `kiro-improvement-analysis.md` (GitHub Copilot Enhanced Task Structure section)
- Original Kiro: `/Users/ming/GitRepos/github-ming86/amazon-kiro.kiro-agent-source-code-analysis/prompts/spec-implementation-plan.md`

**For Phase 4 Chat Mode** (`spec-execution.chatmode.md`):
- Execution discipline from: Original Kiro `spec-task-execution.md`
- Tool usage from: Existing correct implementation patterns
- Self-correction guidance from: `kiro-improvement-analysis.md`

**For Task Execution Prompt** (`spec-execute-task.prompt.md`):
- Parameter structure from: Existing prompt files in `.github-v3/prompts/`
- Execution logic from: Original Kiro task execution principles
- Single-task focus from: Kiro discipline requirements

## Validation Checklist

After implementation, verify:

### ✅ Phase Separation Maintained
- [ ] Phase 3 mode focuses ONLY on planning (no editFiles tool)
- [ ] Phase 4 mode focuses ONLY on execution (no planning content)
- [ ] Clear boundaries between phases maintained

### ✅ Approval Workflow Preserved  
- [ ] Each phase checks previous phase approval in spec.yaml
- [ ] No automatic progression between phases
- [ ] Manual approval required between phases

### ✅ Original Kiro Principles Maintained
- [ ] EARS format in requirements (Phase 1)
- [ ] Research integration in design (Phase 2)  
- [ ] Coding-only task focus (Phase 3)
- [ ] Single-task execution discipline (Phase 4)

### ✅ Platform Optimization
- [ ] Appropriate tools for each phase
- [ ] Interactive input variables where needed
- [ ] Agent mode optimization for complex tasks

## Execution Priority

1. **HIGH**: Delete incorrect `spec-implementation.chatmode.md`
2. **HIGH**: Create `spec-4-tasks.chatmode.md` (Phase 3)
3. **HIGH**: Create `spec-execution.chatmode.md` (Phase 4)  
4. **MEDIUM**: Create `spec-execute-task.prompt.md`
5. **LOW**: Update documentation to reflect correct workflow

## Critical Success Factor

**The fix MUST maintain the core Kiro principle**: Each phase is separate with approval gates between them. No phase should combine planning and execution activities.

**This separation enables**:
- Clear mental model for users
- Proper approval workflow
- Focused LLM conversations  
- Error isolation between phases
- Maintainable development process

## Next Actions

1. Review this plan for completeness
2. Execute fixes in priority order
3. Test each phase separately to ensure proper separation
4. Validate complete workflow end-to-end
5. Update documentation with corrected workflow

**The GitHub Copilot v3 implementation will be correct and aligned with proven Kiro methodology after these fixes.**