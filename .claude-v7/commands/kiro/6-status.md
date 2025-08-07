# Kiro Status Analysis and Progress Inspection

This command provides comprehensive analysis of your Kiro spec-driven development workflow progress, document quality assessment, and strategic recommendations for next steps.

**Usage**: `/kiro:6-status [feature-name]`

**Purpose**: Read-only analysis providing insights into current workflow state, quality metrics, and progression recommendations.

---

## Section 1: Context and Validation

I'll begin by analyzing your current Kiro workflow state to provide accurate progress insights.

**Primary Analysis:**

- Reading spec.yaml configuration: `@.kiro/specs/$ARGUMENTS/spec.yaml`
- Validating YAML structure and required fields
- Checking feature initialization completeness
- Verifying directory structure organization

**Validation Framework:**

- YAML structure integrity (required fields present)
- Feature metadata completeness (name, description, timestamps)
- Approval state consistency (generated/approved flags alignment)
- File system organization (proper .kiro structure)

**Error Handling:**
If spec.yaml is missing or malformed, I'll provide specific guidance on initialization requirements and recommend using `/kiro:1-init` to establish proper project structure.

---

## Section 2: Workflow Progress Analysis

**Comprehensive Progress Assessment:**

I'll analyze approval states across all four Kiro stages:

**Stage 1 - Requirements Analysis:**

- `approvals.requirements.generated`: Document creation status
- `approvals.requirements.approved`: User approval confirmation  
- File presence: requirements.md existence and accessibility
- Progress indicator: Visual representation of completion state

**Stage 2 - Design Analysis:**

- `approvals.design.generated`: Document creation status
- `approvals.design.approved`: User approval confirmation
- File presence: design.md existence and accessibility  
- Progress indicator: Visual representation of completion state

**Stage 3 - Implementation Planning Analysis:**

- `approvals.implementation_plan.generated`: Document creation status
- `approvals.implementation_plan.approved`: User approval confirmation
- File presence: tasks.md existence and accessibility
- Progress indicator: Visual representation of completion state

**Stage 4 - Task Execution Analysis:**

- Active task identification (if tasks.md exists)
- Completion tracking: Checked vs unchecked tasks
- Progress calculation: Percentage completion metrics
- Current task context: Next logical task identification

**Visual Progress Representation:**
I'll provide clear progress indicators showing:

- Overall workflow completion percentage
- Stage-specific completion status
- Approval gate status (pending/completed)
- Current workflow position and next steps

---

## Section 3: Document Quality Assessment

**Comprehensive Quality Analysis Framework:**

**Requirements Document Quality (requirements.md):**

- **EARS Format Compliance**: Verification of "The system shall [action]" and conditional formats
- **User Story Structure**: "As a [role], I want [feature], so that [benefit]" template compliance
- **Coverage Completeness**: Functional, non-functional, technical constraints, edge cases
- **Content Quality**: Clarity, testability, scope appropriateness, value articulation
- **Structure Validation**: Hierarchical organization, section completeness

**Design Document Quality (design.md):**

- **Section Completeness**: All 6 mandatory sections (Overview, Architecture, Components, Data Models, Error Handling, Testing Strategy)
- **Research Integration**: Evidence of research findings incorporated into design decisions
- **Requirement Coverage**: All requirements addressed in design specifications
- **Technical Quality**: Architectural coherence, interface specifications, data model completeness
- **Design Rationale**: Decision justification and alternative consideration

**Implementation Plan Quality (tasks.md):**

- **Format Compliance**: Numbered checkbox list with maximum two-level hierarchy
- **Coding Exclusivity**: All tasks involve writing, modifying, or testing code exclusively
- **Requirement Traceability**: Tasks map to specific requirements (granular level)
- **Incremental Progression**: Tasks build systematically without orphaned code
- **Task Quality**: Clear objectives, actionable descriptions, proper scope definition

**Quality Scoring System:**

- Document Quality Score: Weighted average across all criteria
- Compliance Rate: Percentage adherence to Kiro standards  
- Completeness Assessment: Coverage and thoroughness evaluation
- Recommendation Priority: Critical, important, or enhancement improvements

---

## Section 4: Cross-Stage Traceability Validation

**Systematic Traceability Analysis:**

**Requirement → Design Mapping:**

- Verification that all requirements are addressed in design.md
- Assessment of requirement coverage depth and accuracy
- Identification of requirements without corresponding design elements
- Quality of requirement-to-design connection clarity

**Requirement → Task Mapping:**

- Verification that all requirements have corresponding implementation tasks
- Granular traceability check (specific acceptance criteria, not just user stories)
- Assessment of requirement coverage completeness in task breakdown
- Identification of requirements without implementation tasks

**Design → Task Mapping:**

- Verification that all design components have corresponding tasks
- Assessment of architectural element implementation coverage
- Identification of design elements without implementation tasks
- Validation of technical specification translation to actionable tasks

**Context Dependency Validation:**

- Stage 4 context usage: Verification that task execution references all context documents
- Context completeness: All required documents available for task execution
- Context currency: Documents reflect current approved state
- Context integration: Evidence of context influence on implementation decisions

**Gap Identification and Resolution:**

- Missing traceability links with specific identification
- Consistency issues between stages with detailed analysis
- Orphaned elements (requirements/design/tasks without connections)
- Recommendations for gap resolution with priority assessment

---

## Section 5: Steering System Integration Analysis

**Comprehensive Steering Assessment:**

**Core Steering Document Analysis:**

- **product.md**: Presence, quality, and influence on current work
  - Content assessment: Product context completeness
  - Integration evaluation: Evidence of product context usage in workflow
  - Quality metrics: Clarity, currency, and strategic alignment
  
- **tech.md**: Technical guidance effectiveness analysis
  - Content assessment: Technology stack and architectural decisions completeness
  - Integration evaluation: Evidence of technical context usage in design/implementation
  - Quality metrics: Technical accuracy, decision rationale, and implementation guidance
  
- **structure.md**: Code organization guidance assessment
  - Content assessment: File organization and pattern guidance completeness
  - Integration evaluation: Evidence of structure context usage in task creation
  - Quality metrics: Pattern consistency, organizational clarity, and implementation utility

**Custom Steering Document Analysis:**

- Domain-specific steering presence and quality assessment
- Specialized context integration (API standards, testing, security, etc.)
- Custom steering effectiveness in workflow guidance
- Conditional inclusion pattern utilization (if implemented)

**Steering Influence Assessment:**

- Evidence of steering context influencing requirements prioritization
- Evidence of steering context guiding design decisions
- Evidence of steering context informing task organization
- Overall steering system effectiveness in maintaining project consistency

**Steering System Recommendations:**

- Missing steering documents that would benefit current work
- Outdated steering content requiring updates
- Steering document quality improvements for enhanced guidance
- Custom steering opportunities for specialized domain needs

---

## Section 6: Quality Control Dashboard

**Comprehensive Project Health Assessment:**

**Overall Project Health Score:**

- Workflow progression score (0-100%): Based on stage completion and approval status
- Document quality score (0-100%): Weighted average across all document quality metrics
- Traceability completeness score (0-100%): Cross-stage mapping effectiveness
- Steering integration score (0-100%): Context utilization and guidance effectiveness
- **Combined Health Score**: Weighted calculation across all dimensions

**Stage-Specific Quality Metrics:**

**Requirements Stage Metrics:**

- EARS format compliance percentage
- User story structure adherence rate
- Coverage completeness assessment (functional/non-functional/technical/edge cases)
- Content quality rating (clarity, testability, scope, value)

**Design Stage Metrics:**

- Section completeness percentage (6 mandatory sections)
- Research integration effectiveness rating
- Requirement coverage completeness percentage
- Technical quality assessment (architecture, interfaces, data models)

**Implementation Stage Metrics:**

- Format compliance percentage (checkbox structure, hierarchy)
- Coding exclusivity compliance rate (non-coding task elimination)
- Requirement traceability completeness percentage
- Task quality assessment (clarity, actionability, progression logic)

**Kiro Behavioral Constraint Compliance:**

- Stage progression rule adherence (no skipping approval gates)
- Document format compliance across all templates
- Quality standard maintenance throughout workflow
- Approval process integrity (explicit approval requirement compliance)

**Issue Identification and Severity Assessment:**

- **Critical Issues**: Workflow blockers requiring immediate attention
- **Important Issues**: Quality gaps affecting output effectiveness
- **Enhancement Opportunities**: Improvements for optimization
- **Compliance Concerns**: Kiro standard adherence issues

**Quality Trend Analysis:**

- Document quality progression across stages
- Consistency maintenance across workflow elements
- Quality improvement opportunities identification
- Standards compliance trend assessment

---

## Section 7: Recommendations and Next Steps

**Strategic Workflow Guidance:**

**Logical Next Command Recommendations:**

Based on current workflow state analysis, I'll provide specific command recommendations:

**If workflow is incomplete:**

- Specific stage recommendations with reasoning (e.g., "/kiro:2-requirements-clarification if requirements need generation/revision")
- Quality improvement priorities before progression
- Gap resolution strategies for missing elements

**If workflow is progressing normally:**

- Next logical stage command with justification
- Preparation recommendations for upcoming stage
- Quality validation suggestions before stage progression

**If workflow is complete:**

- Task execution recommendations (/kiro:5-task-execution with specific task suggestions)
- Quality maintenance strategies
- Feature completion assessment and next feature initiation

**Quality Improvement Recommendations:**

**Critical Quality Issues (Immediate Attention Required):**

- Specific improvement guidance with examples
- Template compliance corrections with exact formatting requirements
- Content completeness gaps with specific addition recommendations

**Important Quality Enhancements (High Impact Improvements):**

- Document quality improvements with specific suggestions
- Traceability strengthening recommendations with mapping guidance  
- Steering integration enhancement opportunities

**Workflow Optimization Recommendations:**

- Process efficiency improvements based on current state analysis
- Quality standard maintenance strategies for sustained excellence
- Integration opportunities with existing project context

**Issue Resolution Strategies:**

- Specific resolution approaches for identified problems
- Priority sequencing for multiple issue resolution
- Resource and time investment guidance for improvements

**Strategic Workflow Insights:**

- Long-term workflow health assessment
- Pattern identification for process improvement
- Best practice recommendations based on current workflow characteristics
- Success metric tracking suggestions for continuous improvement

**Educational Context:**
For each recommendation, I'll provide:

- Clear reasoning for why the recommendation is valuable
- Expected outcomes from following the guidance
- Connections to Kiro workflow principles and quality standards
- Resource requirements and time investment expectations

This comprehensive analysis maintains Kiro's rigorous quality standards while providing actionable insights for productive workflow progression, ensuring your spec-driven development process remains effective, high-quality, and aligned with established best practices.
