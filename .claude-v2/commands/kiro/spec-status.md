---
description: Enhanced progress tracking with validation status and visual indicators
allowed-tools: Bash, Read, Write, Edit, Update, Task
---

# Enhanced Specification Status

Display comprehensive status and progress for feature: **$ARGUMENTS**

## Specification Validation

### Spec Directory Check

!`ls -la .kiro/specs/$ARGUMENTS/ 2>/dev/null || echo "❌ Specification directory not found"`

### Core File Existence

!`ls .kiro/specs/$ARGUMENTS/spec.json 2>/dev/null && echo "✅ Metadata file found" || echo "❌ Missing spec.json"`
!`ls .kiro/specs/$ARGUMENTS/requirements.md 2>/dev/null && echo "✅ Requirements file found" || echo "❌ Missing requirements.md"`
!`ls .kiro/specs/$ARGUMENTS/design.md 2>/dev/null && echo "✅ Design file found" || echo "❌ Missing design.md"`
!`ls .kiro/specs/$ARGUMENTS/tasks.md 2>/dev/null && echo "✅ Tasks file found" || echo "❌ Missing tasks.md"`

## Enhanced Progress Overview

### Specification Metadata

- Spec metadata: @.kiro/specs/$ARGUMENTS/spec.json

### Phase Progress Analysis

!`if [ -f ".kiro/specs/$ARGUMENTS/spec.json" ]; then echo "📊 Progress Analysis:"; cat .kiro/specs/$ARGUMENTS/spec.json | jq -r '.progress // {"requirements": 0, "design": 0, "tasks": 0} | "Requirements: \(.requirements)% | Design: \(.design)% | Tasks: \(.tasks)%"' 2>/dev/null || echo "⚠️  Progress tracking unavailable"; else echo "❌ No metadata file found"; fi`

### Visual Progress Indicators

!`if [ -f ".kiro/specs/$ARGUMENTS/spec.json" ]; then TOTAL=$(cat .kiro/specs/$ARGUMENTS/spec.json | jq -r '(.progress.requirements // 0) + (.progress.design // 0) + (.progress.tasks // 0)' 2>/dev/null || echo "0"); OVERALL=$((TOTAL / 3)); echo "🎯 Overall Progress: $OVERALL%"; if [ $OVERALL -ge 75 ]; then echo "🟢 Near completion"; elif [ $OVERALL -ge 50 ]; then echo "🟡 Good progress"; elif [ $OVERALL -ge 25 ]; then echo "🟠 Getting started"; else echo "🔴 Just beginning"; fi; else echo "❌ Cannot calculate progress"; fi`

## EARS Methodology Compliance

### EARS Format Validation

!`if [ -f ".kiro/specs/$ARGUMENTS/requirements.md" ]; then EARS_COUNT=$(grep -c "WHEN.*THEN\|GIVEN.*WHEN.*THEN\|IF.*THEN" .kiro/specs/$ARGUMENTS/requirements.md 2>/dev/null || echo "0"); echo "📝 EARS Requirements Found: $EARS_COUNT"; if [ $EARS_COUNT -gt 0 ]; then echo "✅ EARS format detected"; else echo "⚠️  Consider converting to EARS format"; fi; else echo "❌ Requirements file not found"; fi`

### EARS Quality Check

!`if [ -f ".kiro/specs/$ARGUMENTS/requirements.md" ]; then echo "🔍 EARS Quality Analysis:"; WHEN_THEN=$(grep -c "WHEN.*THEN" .kiro/specs/$ARGUMENTS/requirements.md 2>/dev/null || echo "0"); GIVEN_WHEN_THEN=$(grep -c "GIVEN.*WHEN.*THEN" .kiro/specs/$ARGUMENTS/requirements.md 2>/dev/null || echo "0"); IF_THEN=$(grep -c "IF.*THEN" .kiro/specs/$ARGUMENTS/requirements.md 2>/dev/null || echo "0"); echo "- Basic WHEN/THEN: $WHEN_THEN"; echo "- Context GIVEN/WHEN/THEN: $GIVEN_WHEN_THEN"; echo "- Exception IF/THEN: $IF_THEN"; TOTAL_EARS=$((WHEN_THEN + GIVEN_WHEN_THEN + IF_THEN)); if [ $TOTAL_EARS -gt 5 ]; then echo "✅ Strong EARS compliance"; elif [ $TOTAL_EARS -gt 2 ]; then echo "🟡 Moderate EARS usage"; else echo "🔴 Limited EARS format"; fi; fi`

## Approval Status Dashboard

### Requirements Approval Status

!`if [ -f ".kiro/specs/$ARGUMENTS/spec.json" ]; then echo "📋 Requirements Status:"; REQ_GEN=$(cat .kiro/specs/$ARGUMENTS/spec.json | jq -r '.approvals.requirements.generated // false' 2>/dev/null || echo "false"); REQ_APP=$(cat .kiro/specs/$ARGUMENTS/spec.json | jq -r '.approvals.requirements.approved // false' 2>/dev/null || echo "false"); METHODOLOGY=$(cat .kiro/specs/$ARGUMENTS/spec.json | jq -r '.approvals.requirements.methodology // "unknown"' 2>/dev/null || echo "unknown"); echo "- Generated: $REQ_GEN"; echo "- Approved: $REQ_APP"; echo "- Methodology: $METHODOLOGY"; if [ "$REQ_APP" = "true" ]; then echo "✅ Requirements approved for design phase"; else echo "⏳ Awaiting requirements approval"; fi; fi`

### Design Approval Status

!`if [ -f ".kiro/specs/$ARGUMENTS/spec.json" ]; then echo "🏗️ Design Status:"; DESIGN_GEN=$(cat .kiro/specs/$ARGUMENTS/spec.json | jq -r '.approvals.design.generated // false' 2>/dev/null || echo "false"); DESIGN_APP=$(cat .kiro/specs/$ARGUMENTS/spec.json | jq -r '.approvals.design.approved // false' 2>/dev/null || echo "false"); RESEARCH_INT=$(cat .kiro/specs/$ARGUMENTS/spec.json | jq -r '.approvals.design.research_integrated // false' 2>/dev/null || echo "false"); echo "- Generated: $DESIGN_GEN"; echo "- Approved: $DESIGN_APP"; echo "- Research Integrated: $RESEARCH_INT"; if [ "$DESIGN_APP" = "true" ]; then echo "✅ Design approved for task generation"; else echo "⏳ Awaiting design approval"; fi; fi`

### Tasks Approval Status

!`if [ -f ".kiro/specs/$ARGUMENTS/spec.json" ]; then echo "📝 Tasks Status:"; TASKS_GEN=$(cat .kiro/specs/$ARGUMENTS/spec.json | jq -r '.approvals.tasks.generated // false' 2>/dev/null || echo "false"); TASKS_APP=$(cat .kiro/specs/$ARGUMENTS/spec.json | jq -r '.approvals.tasks.approved // false' 2>/dev/null || echo "false"); MULTI_TASK=$(cat .kiro/specs/$ARGUMENTS/spec.json | jq -r '.approvals.tasks.multi_task_ready // false' 2>/dev/null || echo "false"); EARS_TRACE=$(cat .kiro/specs/$ARGUMENTS/spec.json | jq -r '.approvals.tasks.ears_traceable // false' 2>/dev/null || echo "false"); echo "- Generated: $TASKS_GEN"; echo "- Approved: $TASKS_APP"; echo "- Multi-task Ready: $MULTI_TASK"; echo "- EARS Traceable: $EARS_TRACE"; if [ "$TASKS_APP" = "true" ]; then echo "✅ Tasks approved for implementation"; else echo "⏳ Awaiting task approval"; fi; fi`

## Implementation Readiness Assessment

### Overall Readiness Check

!`if [ -f ".kiro/specs/$ARGUMENTS/spec.json" ]; then READY=$(cat .kiro/specs/$ARGUMENTS/spec.json | jq -r '.ready_for_implementation // false' 2>/dev/null || echo "false"); MULTI_EXEC=$(cat .kiro/specs/$ARGUMENTS/spec.json | jq -r '.multi_task_execution // false' 2>/dev/null || echo "false"); echo "🚀 Implementation Readiness:"; echo "- Ready for Implementation: $READY"; echo "- Multi-task Execution: $MULTI_EXEC"; if [ "$READY" = "true" ]; then echo "✅ Ready to execute with /execute-tasks"; else echo "⏳ Complete approvals before implementation"; fi; fi`

### Phase Gate Validation

!`if [ -f ".kiro/specs/$ARGUMENTS/spec.json" ]; then echo "🚪 Phase Gate Status:"; PHASE=$(cat .kiro/specs/$ARGUMENTS/spec.json | jq -r '.phase // "unknown"' 2>/dev/null || echo "unknown"); echo "- Current Phase: $PHASE"; case $PHASE in "requirements-generated") echo "📋 Next: Review and approve requirements";; "requirements-approved") echo "🏗️ Next: Generate design";; "design-generated") echo "🏗️ Next: Review and approve design";; "design-approved") echo "📝 Next: Generate tasks";; "tasks-generated") echo "📝 Next: Review and approve tasks";; "ready-for-implementation") echo "🚀 Next: Execute implementation";; *) echo "❓ Unknown phase status";; esac; fi`

## Research Integration Status

### Research Tracking

!`if [ -f ".kiro/specs/$ARGUMENTS/spec.json" ]; then echo "🔬 Research Integration:"; RESEARCH_CONDUCTED=$(cat .kiro/specs/$ARGUMENTS/spec.json | jq -r '.research.conducted // false' 2>/dev/null || echo "false"); if [ "$RESEARCH_CONDUCTED" = "true" ]; then SOURCES_COUNT=$(cat .kiro/specs/$ARGUMENTS/spec.json | jq -r '.research.sources_count // "unknown"' 2>/dev/null || echo "unknown"); RESEARCH_AREAS=$(cat .kiro/specs/$ARGUMENTS/spec.json | jq -r '.research.research_areas[]? // "none"' 2>/dev/null | tr '\n' ', ' | sed 's/,$//'); echo "- Research Conducted: Yes"; echo "- Sources Count: $SOURCES_COUNT"; echo "- Research Areas: $RESEARCH_AREAS"; else echo "- Research Conducted: No"; echo "- Research may enhance design quality for complex features"; fi; fi`

### Research Quality Validation

!`if [ -f ".kiro/specs/$ARGUMENTS/design.md" ]; then RESEARCH_SECTIONS=$(grep -c "Research-Driven Design\|Research Findings\|Source URL\|Documentation URL" .kiro/specs/$ARGUMENTS/design.md 2>/dev/null || echo "0"); if [ $RESEARCH_SECTIONS -gt 0 ]; then echo "✅ Research documentation found in design"; else echo "ℹ️  No research documentation detected"; fi; fi`

## Task Execution Status

### Task Completion Analysis

!`if [ -f ".kiro/specs/$ARGUMENTS/tasks.md" ]; then echo "📊 Task Execution Progress:"; TOTAL_TASKS=$(grep -c "^- \[ \]" .kiro/specs/$ARGUMENTS/tasks.md 2>/dev/null || echo "0"); COMPLETED_TASKS=$(grep -c "^- \[x\]" .kiro/specs/$ARGUMENTS/tasks.md 2>/dev/null || echo "0"); if [ $TOTAL_TASKS -gt 0 ]; then COMPLETION_PERCENT=$((COMPLETED_TASKS * 100 / TOTAL_TASKS)); echo "- Total Tasks: $TOTAL_TASKS"; echo "- Completed Tasks: $COMPLETED_TASKS"; echo "- Completion: $COMPLETION_PERCENT%"; if [ $COMPLETION_PERCENT -eq 100 ]; then echo "🎉 All tasks completed!"; elif [ $COMPLETION_PERCENT -ge 75 ]; then echo "🟢 Nearly complete"; elif [ $COMPLETION_PERCENT -ge 50 ]; then echo "🟡 Good progress"; elif [ $COMPLETION_PERCENT -ge 25 ]; then echo "🟠 Getting there"; else echo "🔴 Just started"; fi; else echo "⚠️  No tasks found for progress tracking"; fi; fi`

### Task Validation Status

!`if [ -f ".kiro/specs/$ARGUMENTS/tasks.md" ]; then echo "🔍 Task Validation:"; EARS_MAPPING=$(grep -c "EARS Mapping\|REQ-" .kiro/specs/$ARGUMENTS/tasks.md 2>/dev/null || echo "0"); ACCEPTANCE_CRITERIA=$(grep -c "Acceptance Criteria" .kiro/specs/$ARGUMENTS/tasks.md 2>/dev/null || echo "0"); TIME_ESTIMATES=$(grep -c "Estimated Time" .kiro/specs/$ARGUMENTS/tasks.md 2>/dev/null || echo "0"); echo "- EARS Mappings: $EARS_MAPPING"; echo "- Acceptance Criteria: $ACCEPTANCE_CRITERIA"; echo "- Time Estimates: $TIME_ESTIMATES"; if [ $EARS_MAPPING -gt 0 ] && [ $ACCEPTANCE_CRITERIA -gt 0 ] && [ $TIME_ESTIMATES -gt 0 ]; then echo "✅ Task structure validated"; else echo "⚠️  Task structure needs enhancement"; fi; fi`

## Multi-Task Execution Readiness

### Execution Environment Check

!`if [ -f ".kiro/specs/$ARGUMENTS/spec.json" ]; then MULTI_READY=$(cat .kiro/specs/$ARGUMENTS/spec.json | jq -r '.approvals.tasks.multi_task_ready // false' 2>/dev/null || echo "false"); echo "⚡ Multi-Task Execution:"; echo "- Multi-task Ready: $MULTI_READY"; if [ "$MULTI_READY" = "true" ]; then echo "✅ Ready for /execute-tasks command"; echo "ℹ️  Run: /execute-tasks $ARGUMENTS"; else echo "⏳ Complete task approval for multi-task execution"; fi; fi`

### Dependency Analysis

!`if [ -f ".kiro/specs/$ARGUMENTS/tasks.md" ]; then echo "🔗 Task Dependencies:"; SEQUENTIAL_TASKS=$(grep -c "Sequential\|must complete before" .kiro/specs/$ARGUMENTS/tasks.md 2>/dev/null || echo "0"); PARALLEL_TASKS=$(grep -c "Parallel\|can be executed simultaneously" .kiro/specs/$ARGUMENTS/tasks.md 2>/dev/null || echo "0"); echo "- Sequential Dependencies: $SEQUENTIAL_TASKS"; echo "- Parallel Opportunities: $PARALLEL_TASKS"; if [ $PARALLEL_TASKS -gt 0 ]; then echo "✅ Parallel execution opportunities identified"; else echo "ℹ️  Sequential execution planned"; fi; fi`

## Quality Metrics and Recommendations

### Specification Quality Score

!`if [ -f ".kiro/specs/$ARGUMENTS/spec.json" ]; then echo "📊 Quality Assessment:"; SCORE=0; REQ_APP=$(cat .kiro/specs/$ARGUMENTS/spec.json | jq -r '.approvals.requirements.approved // false' 2>/dev/null); DESIGN_APP=$(cat .kiro/specs/$ARGUMENTS/spec.json | jq -r '.approvals.design.approved // false' 2>/dev/null); TASKS_APP=$(cat .kiro/specs/$ARGUMENTS/spec.json | jq -r '.approvals.tasks.approved // false' 2>/dev/null); METHODOLOGY=$(cat .kiro/specs/$ARGUMENTS/spec.json | jq -r '.approvals.requirements.methodology // "unknown"' 2>/dev/null); [ "$REQ_APP" = "true" ] && SCORE=$((SCORE + 25)); [ "$DESIGN_APP" = "true" ] && SCORE=$((SCORE + 25)); [ "$TASKS_APP" = "true" ] && SCORE=$((SCORE + 25)); [ "$METHODOLOGY" = "EARS" ] && SCORE=$((SCORE + 25)); echo "- Specification Quality Score: $SCORE/100"; if [ $SCORE -ge 75 ]; then echo "🟢 High quality specification"; elif [ $SCORE -ge 50 ]; then echo "🟡 Good specification, room for improvement"; else echo "🔴 Specification needs enhancement"; fi; fi`

### Enhancement Recommendations

!`if [ -f ".kiro/specs/$ARGUMENTS/spec.json" ]; then echo "💡 Recommendations:"; METHODOLOGY=$(cat .kiro/specs/$ARGUMENTS/spec.json | jq -r '.approvals.requirements.methodology // "unknown"' 2>/dev/null); RESEARCH_INT=$(cat .kiro/specs/$ARGUMENTS/spec.json | jq -r '.approvals.design.research_integrated // false' 2>/dev/null); MULTI_TASK=$(cat .kiro/specs/$ARGUMENTS/spec.json | jq -r '.approvals.tasks.multi_task_ready // false' 2>/dev/null); if [ "$METHODOLOGY" != "EARS" ]; then echo "- 📝 Consider converting requirements to EARS format for better testability"; fi; if [ "$RESEARCH_INT" != "true" ]; then echo "- 🔬 Consider adding research to inform design decisions"; fi; if [ "$MULTI_TASK" != "true" ]; then echo "- ⚡ Enable multi-task execution for efficient implementation"; fi; fi`

## Next Steps Guidance

### Immediate Actions

!`if [ -f ".kiro/specs/$ARGUMENTS/spec.json" ]; then PHASE=$(cat .kiro/specs/$ARGUMENTS/spec.json | jq -r '.phase // "unknown"' 2>/dev/null); READY=$(cat .kiro/specs/$ARGUMENTS/spec.json | jq -r '.ready_for_implementation // false' 2>/dev/null); echo "🎯 Next Steps:"; if [ "$READY" = "true" ]; then echo "✅ All phases complete - Ready for implementation"; echo "🚀 Run: /execute-tasks $ARGUMENTS"; elif [ "$PHASE" = "tasks-generated" ]; then echo "📝 Review tasks.md and approve in spec.json"; echo "✏️  Update: 'tasks.approved: true' in spec.json"; elif [ "$PHASE" = "design-generated" ]; then echo "🏗️ Review design.md and approve in spec.json"; echo "✏️  Update: 'design.approved: true' in spec.json"; elif [ "$PHASE" = "requirements-generated" ]; then echo "📋 Review requirements.md and approve in spec.json"; echo "✏️  Update: 'requirements.approved: true' in spec.json"; else echo "🔄 Continue with specification workflow"; fi; fi`

### Workflow Commands

!`echo "🛠️ Available Commands:"; echo "- /spec-requirements $ARGUMENTS  # Generate/update requirements"; echo "- /spec-design $ARGUMENTS        # Generate/update design"; echo "- /spec-tasks $ARGUMENTS         # Generate/update tasks"; echo "- /spec-status $ARGUMENTS        # View this status (refresh)"; echo "- /execute-tasks $ARGUMENTS      # Multi-task implementation (when ready)"`

## Status Summary

!`echo ""; echo "========================================"; echo "📋 SPECIFICATION STATUS SUMMARY"; echo "========================================"; if [ -f ".kiro/specs/$ARGUMENTS/spec.json" ]; then PHASE=$(cat .kiro/specs/$ARGUMENTS/spec.json | jq -r '.phase // "unknown"' 2>/dev/null); READY=$(cat .kiro/specs/$ARGUMENTS/spec.json | jq -r '.ready_for_implementation // false' 2>/dev/null); echo "Feature: $ARGUMENTS"; echo "Phase: $PHASE"; echo "Implementation Ready: $READY"; echo "========================================"; else echo "❌ Specification not initialized"; echo "Run: /spec-init $ARGUMENTS"; echo "========================================"; fi`
