---
description: "Execute Kiro comprehensive workflow analysis with 7-dimensional assessment and strategic recommendations"
mode: agent
---

# Kiro Status Analysis and Progress Inspection

## Methodology Reinforcement

You are executing Kiro comprehensive workflow analysis with the following approach:

- **7-Dimensional Analysis Framework**: Context validation, workflow progress, document quality, cross-stage traceability, steering integration, quality control dashboard, strategic recommendations
- **Read-Only Diagnostic Operations**: Complete analysis without modifying any files or workflow state throughout entire process
- **Quantitative Scoring Methodology**: Transparent calculation methods with weighted scoring across all assessment dimensions
- **Educational Assessment Approach**: Clear reasoning for all quality scores, assessments, and strategic recommendations
- **Strategic Recommendation Synthesis**: Command-specific guidance based on objective assessment criteria and workflow state analysis

This command provides comprehensive analysis of your Kiro spec-driven development workflow progress, document quality assessment, and strategic recommendations for next steps.

**Purpose**: Read-only analysis providing insights into current workflow state, quality metrics, and progression recommendations.

# Section 1: Context and Validation

## Feature Selection and Context Loading Process

**Before proceeding with analysis, think step by step about:**

1. What feature should be analyzed and does it exist in the project?
2. What workflow documents are available for comprehensive assessment?
3. What baseline understanding is needed for accurate analysis?

**Feature Selection Process:**

Let me check for available features and validate your input.

**Available Features Discovery:**

- Use terminal tool to list .kiro/specs/ directory contents
- Identify available features for analysis
- Validate project structure and initialization completeness

**Feature Argument Validation:**

If you didn't provide a feature name or the feature doesn't exist:

### Available Features in .kiro/specs/

**Please specify which feature you'd like to analyze:**

- Type the feature name exactly as shown (kebab-case format)
- Feature must be initialized with spec.yaml for complete analysis
- All available workflow documents will be analyzed for comprehensive assessment

**Waiting for your feature selection...**

Once you provide a valid feature name, I'll continue with comprehensive analysis.

## Comprehensive Context Loading and Validation

**After receiving valid feature name, systematically load all available workflow context:**

**Think through what context documents should be loaded:**

1. What core workflow documents exist for this feature?
2. What steering documents are available for context integration?
3. What validation checks ensure baseline accuracy?

**Systematic Context Loading Strategy:**

**Primary Feature Analysis:**

- Reading spec.yaml configuration: .kiro/specs/[feature-name]/spec.yaml
- Validating YAML structure and required fields completeness
- Checking feature initialization completeness and metadata accuracy
- Verifying directory structure organization for proper Kiro setup

**Complete Document Context Loading:**

- Feature specification: .kiro/specs/[feature-name]/spec.yaml (REQUIRED)
- Requirements document: .kiro/specs/[feature-name]/requirements.md (if exists)
- Design document: .kiro/specs/[feature-name]/design.md (if exists)
- Implementation tasks: .kiro/specs/[feature-name]/tasks.md (if exists)
- Product steering: .kiro/steering/product.md (if exists)
- Technical steering: .kiro/steering/tech.md (if exists)
- Structure steering: .kiro/steering/structure.md (if exists)

**Load complete content of each available document systematically for comprehensive baseline understanding.**

## Context Validation Framework

**After loading all available documents, systematically validate context completeness:**

**Validation Criteria Assessment:**

- YAML structure integrity with all required fields present
- Feature metadata completeness including name, description, timestamps
- Approval state consistency with generated and approved flags alignment
- File system organization following proper Kiro directory structure
- Document accessibility and content completeness for analysis accuracy

**Error Handling and Guidance:**
If spec.yaml is missing or malformed, provide specific guidance on initialization requirements and recommend using appropriate setup commands to establish proper project structure.

**Context Validation Results Summary:**

- **Feature Identity**: [feature-name] verification and metadata analysis
- **Workflow State**: Current stage and approval status from spec.yaml
- **Document Availability**: Complete inventory of available workflow documents
- **Directory Structure**: Validation of proper Kiro organization and accessibility

**Baseline understanding established - Ready to proceed with comprehensive 7-dimensional analysis.**

# Section 2: Workflow Progress Analysis

## Comprehensive Progress Assessment Framework

**Before generating progress scores, think step by step about assessment methodology:**

1. What approval states exist across all 4 Kiro stages?
2. How should stage completion be calculated with transparent methodology?
3. What visual progress representation provides maximum user value?

**Systematic Workflow Progression Analysis:**

**Analyze approval states across all four Kiro stages systematically:**

### Stage 1 - Requirements Analysis Assessment

**Requirements Stage Evaluation:**

- approvals.requirements.generated: Document creation status validation
- approvals.requirements.approved: User approval confirmation verification
- File presence: requirements.md existence and accessibility validation
- Progress indicator: Visual representation of requirements completion state

**Requirements Progress Calculation:**

- Generated Status: [true/false from spec.yaml] = [0% or 25%]
- Approved Status: [true/false from spec.yaml] = [0% or 25%]
- Requirements Stage Total: [Generated + Approved percentages] = [0-50%]

### Stage 2 - Design Analysis Assessment

**Design Stage Evaluation:**

- approvals.design.generated: Document creation status validation
- approvals.design.approved: User approval confirmation verification
- File presence: design.md existence and accessibility validation
- Progress indicator: Visual representation of design completion state

**Design Progress Calculation:**

- Generated Status: [true/false from spec.yaml] = [0% or 25%]
- Approved Status: [true/false from spec.yaml] = [0% or 25%]
- Design Stage Total: [Generated + Approved percentages] = [0-50%]

### Stage 3 - Implementation Planning Analysis Assessment

**Implementation Planning Stage Evaluation:**

- approvals.tasks.generated: Document creation status validation
- approvals.tasks.approved: User approval confirmation verification
- File presence: tasks.md existence and accessibility validation
- Progress indicator: Visual representation of planning completion state

**Implementation Planning Progress Calculation:**

- Generated Status: [true/false from spec.yaml] = [0% or 25%]
- Approved Status: [true/false from spec.yaml] = [0% or 25%]
- Implementation Planning Stage Total: [Generated + Approved percentages] = [0-50%]

### Stage 4 - Task Execution Analysis Assessment

**Task Execution Stage Evaluation (if tasks.md exists):**

- Active task identification and current task context analysis
- Completion tracking: Systematic count of checked vs unchecked tasks
- Progress calculation: Completed tasks / Total tasks percentage
- Next logical task identification for workflow progression guidance

**Task Execution Progress Calculation:**

- Total Tasks: [Count from tasks.md] tasks identified
- Completed Tasks: [Count of checked boxes] tasks finished
- Task Execution Percentage: [Completed/Total * 100] = [X%]

## Progress Calculation Methodology and Visual Representation

**Overall Progress Calculation Formula:**

- **Stage Completion**: (Generated Points + Approved Points) per stage = Maximum 50% per stage
- **Overall Workflow Progress**: (Requirements% + Design% + Planning% + Execution%) / 4 = Overall percentage
- **Task Execution**: (Completed tasks / Total tasks) \* 100 = Execution percentage

**Comprehensive Progress Results:**

**Overall Workflow Progress**: [Calculated percentage with transparent methodology]

- **Stage 1 (Requirements)**: [X%] - [Status description]
- **Stage 2 (Design)**: [X%] - [Status description]
- **Stage 3 (Implementation Planning)**: [X%] - [Status description]
- **Stage 4 (Task Execution)**: [X%] - [Status description if applicable]

**Approval Gate Analysis**: [Current blocking points or stages ready for progression]
**Task Execution Status**: [Implementation progress details if tasks exist]

**Visual Progress Indicators:**

- Overall workflow completion percentage with methodology transparency
- Stage-specific completion status with clear progression indicators
- Approval gate status showing pending vs completed approvals
- Current workflow position and logical next steps identification
- Task execution progress with specific completion metrics if applicable

# Section 3: Document Quality Assessment

## Comprehensive Quality Analysis Framework

**Before evaluating document quality, systematically plan assessment approach:**

1. What Kiro standards apply to each document type?
2. How should quality scores be calculated with transparent methodology?
3. What quality gaps need identification for improvement guidance?

**Execute systematic quality evaluation across all available documents:**

## Requirements Document Quality Assessment (requirements.md)

**If requirements.md exists, execute comprehensive quality analysis:**

**EARS Format Compliance Evaluation:**

- Verify "The system shall [action]" format usage throughout acceptance criteria
- Check conditional format: "When [condition], the system shall [response]" compliance
- Validate optional format: "The system should [preference]" appropriate usage
- Confirm complex format: "While [state], when [trigger], the system shall [behavior]" implementation
- **EARS Format Score**: [Percentage compliance across all acceptance criteria]

**User Story Structure Assessment:**

- Validate "As a [role], I want [feature], so that [benefit]" template compliance throughout
- Check role clarity and specificity (user, admin, system, developer identification)
- Confirm feature description concreteness and actionability (avoiding vague language)
- Verify benefit articulation with clear, measurable value proposition
- **User Story Score**: [Percentage compliance across all user stories]

**Coverage Completeness Analysis:**

- Functional requirements coverage: Core capabilities and user-facing functionality
- Non-functional requirements coverage: Performance, security, usability, reliability
- Technical constraints coverage: Technology, infrastructure, integration requirements
- Edge cases coverage: Invalid input, system failure, boundary conditions
- **Coverage Score**: [Percentage across functional/non-functional/technical/edge categories]

**Content Quality Assessment:**

- Clarity: Language precision and unambiguous specification
- Testability: Measurable acceptance criteria and validation approaches
- Scope appropriateness: Requirements align with project scale and capabilities
- Value articulation: Clear benefit statements and business justification
- **Content Quality Score**: [Weighted average across clarity/testability/scope/value]

**Structure Validation:**

- Hierarchical organization: Logical requirement categorization and numbering
- Section completeness: All mandatory sections present and populated
- Template compliance: Adherence to Kiro requirements document structure
- **Structure Score**: [Percentage compliance with Kiro template requirements]

**Requirements Document Quality Results:**

- **Overall Requirements Quality**: [Weighted calculation across all criteria] (0-100%)
- **Compliance Rate**: [Percentage adherence to Kiro standards]
- **Completeness Assessment**: [Coverage and thoroughness evaluation]

## Design Document Quality Assessment (design.md)

**If design.md exists, execute comprehensive quality analysis:**

**Section Completeness Evaluation:**

- Overview section: System architecture summary with research integration
- Architecture section: Detailed component relationships and technology choices
- Components and Interfaces section: Comprehensive specifications and interaction patterns
- Data Models section: Complete structures, schemas, and relationships
- Error Handling section: Comprehensive conditions and recovery mechanisms
- Testing Strategy section: Testing approaches and validation methods
- **Section Score**: [6 mandatory sections present and complete] (0-100%)

**Research Integration Assessment:**

- Evidence of research findings incorporated into design decisions
- Technology choices justified by research analysis and requirements alignment
- Architecture patterns supported by research and best practices
- Integration approaches based on research recommendations
- **Research Integration Score**: [Quality of research incorporation] (0-100%)

**Requirement Coverage Validation:**

- All requirements from requirements.md addressed in design specifications
- Functional requirements mapped to specific design components
- Non-functional requirements addressed through architecture patterns
- Technical constraints incorporated into design decisions
- **Requirement Coverage Score**: [Percentage of requirements addressed] (0-100%)

**Technical Quality Assessment:**

- Architectural coherence: Component relationships logical and well-defined
- Interface specifications: Complete input/output definitions and interaction patterns
- Data model completeness: Comprehensive schemas supporting all requirements
- Integration points: External system connections properly specified
- **Technical Quality Score**: [Architecture quality across components] (0-100%)

**Design Rationale Evaluation:**

- Decision justification: Clear reasoning for architectural choices
- Alternative consideration: Evidence of option evaluation and trade-off analysis
- Requirements traceability: Design decisions linked to specific requirements
- **Design Rationale Score**: [Quality of reasoning and justification] (0-100%)

**Design Document Quality Results:**

- **Overall Design Quality**: [Weighted calculation across all criteria] (0-100%)
- **Compliance Rate**: [Percentage adherence to Kiro design standards]
- **Completeness Assessment**: [Architectural coverage and thoroughness evaluation]

## Implementation Plan Quality Assessment (tasks.md)

**If tasks.md exists, execute comprehensive quality analysis:**

**Format Compliance Validation:**

- Numbered checkbox list structure: "- [ ] 1.", "- [ ] 1.1" format usage
- Maximum two-level hierarchy: No deeper nesting beyond X.Y format
- Decimal notation: Proper sub-task numbering (1.1, 1.2, 2.1, etc.)
- Checkbox structure: Consistent format for completion tracking
- **Format Score**: [Template compliance percentage] (0-100%)

**Coding Exclusivity Assessment:**

- All tasks involve writing, modifying, or testing code exclusively
- No user acceptance testing tasks (different skillset and timing requirements)
- No deployment activity tasks (different tools and permissions needed)
- No performance metrics gathering (different stage and process requirements)
- No end-to-end manual testing (different validation process)
- **Coding Exclusivity Score**: [Percentage of tasks that are coding-only] (0-100%)

**Requirement Traceability Validation:**

- Tasks map to specific requirements at granular level (not just user stories)
- All approved requirements have corresponding implementation tasks
- Task descriptions reference specific acceptance criteria from requirements.md
- Implementation coverage complete without orphaned requirements
- **Traceability Score**: [Requirement-to-task mapping completeness] (0-100%)

**Incremental Progression Assessment:**

- Tasks build systematically with logical dependencies
- Each task produces outputs usable by subsequent tasks
- No orphaned or disconnected tasks in sequence
- Core functionality implementable and testable early
- Complexity increases gradually across task progression
- **Incremental Score**: [Progressive implementation logic quality] (0-100%)

**Task Quality Evaluation:**

- Clear objectives: Task descriptions provide specific, actionable goals
- Actionable descriptions: Implementation steps clearly defined
- Proper scope definition: Task complexity appropriate for single focus
- Completion criteria: Clear indicators for task completion validation
- **Task Quality Score**: [Clarity and actionability across all tasks] (0-100%)

**Implementation Plan Quality Results:**

- **Overall Tasks Quality**: [Weighted calculation across all criteria] (0-100%)
- **Compliance Rate**: [Percentage adherence to Kiro task standards]
- **Completeness Assessment**: [Implementation coverage and progression evaluation]

## Overall Document Quality Synthesis

**Quality Scoring Methodology Transparency:**

- **Document Quality Score**: Weighted average across all document criteria (0-100%)
- **Compliance Rate**: Percentage adherence to Kiro standards across all documents (0-100%)
- **Completeness Assessment**: Coverage and thoroughness evaluation across workflow (0-100%)
- **Recommendation Priority**: Critical, important, or enhancement improvements categorized

**Document Quality Summary Results:**

- **Requirements Quality**: [Score and detailed assessment if document exists]
- **Design Quality**: [Score and detailed assessment if document exists]
- **Implementation Plan Quality**: [Score and detailed assessment if document exists]
- **Overall Document Quality Score**: [Weighted calculation across all existing documents]

# Section 4: Cross-Stage Traceability Validation

## Systematic Traceability Analysis Framework

**Before validating cross-stage connections, plan traceability assessment approach:**

1. What mappings exist between requirements, design, and tasks?
2. How can gaps and missing connections be systematically identified?
3. What resolution strategies provide maximum workflow integrity improvement?

**Execute comprehensive traceability validation across all workflow stages:**

## Requirements → Design Mapping Analysis

**If both requirements.md and design.md exist, execute systematic mapping validation:**

**Requirement Coverage Verification:**

- Systematically verify that all requirements from requirements.md are addressed in design.md
- Assess requirement coverage depth and accuracy in design specifications
- Identify requirements without corresponding design elements or inadequate design coverage
- Evaluate quality of requirement-to-design connection clarity and completeness

**Design Alignment Assessment:**

- Functional requirements mapped to specific design components with clear specifications
- Non-functional requirements addressed through architecture patterns and design decisions
- Technical constraints incorporated systematically into design architecture
- Integration requirements fully specified in design component interfaces

**Requirements → Design Mapping Results:**

- **Coverage Percentage**: [X% of requirements addressed in design]
- **Depth Assessment**: [Quality of requirement coverage in design specifications]
- **Gap Identification**: [Specific requirements lacking adequate design coverage]
- **Connection Quality**: [Clarity of requirement-to-design traceability]

## Requirements → Task Mapping Analysis

**If both requirements.md and tasks.md exist, execute systematic mapping validation:**

**Implementation Coverage Verification:**

- Systematically verify that all requirements have corresponding implementation tasks
- Execute granular traceability check focusing on specific acceptance criteria, not just user stories
- Assess requirement coverage completeness in task breakdown without orphaned requirements
- Identify requirements without implementation tasks or inadequate task coverage

**Task Alignment Assessment:**

- Functional requirements mapped to specific implementation tasks with clear objectives
- Non-functional requirements addressed through appropriate task types and validation
- Technical constraints incorporated into task planning and implementation approach
- Acceptance criteria from requirements addressed by specific task completion criteria

**Requirements → Task Mapping Results:**

- **Coverage Percentage**: [X% of requirements with corresponding tasks]
- **Granular Traceability**: [Acceptance criteria level mapping completeness]
- **Gap Identification**: [Specific requirements lacking implementation tasks]
- **Implementation Completeness**: [Assessment of requirement fulfillment through tasks]

## Design → Task Mapping Analysis

**If both design.md and tasks.md exist, execute systematic mapping validation:**

**Design Component Implementation Verification:**

- Systematically verify that all design components have corresponding implementation tasks
- Assess architectural element implementation coverage and completeness
- Identify design elements without implementation tasks or inadequate task specifications
- Validate technical specification translation to actionable coding tasks

**Implementation Alignment Assessment:**

- Architecture components mapped to specific implementation tasks with clear technical objectives
- Interface specifications addressed through appropriate task types and implementation approaches
- Data models covered by specific implementation and testing tasks
- Integration points addressed through connection and validation tasks

**Design → Task Mapping Results:**

- **Coverage Percentage**: [X% of design components with corresponding tasks]
- **Implementation Coverage**: [Architecture element task mapping completeness]
- **Gap Identification**: [Specific design elements lacking implementation tasks]
- **Technical Translation**: [Quality of design-to-task specification conversion]

## Context Dependency Health Validation

**Evaluate context document utilization and integration effectiveness:**

**Stage 4 Context Usage Assessment:**

- Verification that task execution processes reference all context documents appropriately
- Context completeness ensuring all required documents available for task execution
- Context currency ensuring documents reflect current approved state accurately
- Context integration demonstrating evidence of context influence on implementation decisions

**Context Integration Analysis:**

- Requirements context: Evidence of requirements influence on design and implementation decisions
- Design context: Evidence of design guidance affecting task breakdown and implementation approach
- Steering context: Evidence of steering document guidance throughout workflow stages
- Cross-stage coherence: Consistency maintained across all workflow elements

**Context Dependency Results:**

- **Context Utilization Score**: [Effectiveness of context integration across stages]
- **Completeness Assessment**: [All required documents available and current]
- **Integration Evidence**: [Quality of context influence on workflow decisions]
- **Coherence Validation**: [Consistency across workflow elements and stages]

## Gap Identification and Resolution Strategy Development

**After identifying workflow gaps and issues, systematically prioritize them by impact:**

**Critical Gap Categories:**

- **Missing Traceability Links**: Specific requirements, design elements, or tasks without connections
- **Consistency Issues**: Contradictions or misalignments between stages with detailed analysis
- **Orphaned Elements**: Requirements, design components, or tasks without proper integration
- **Context Integration Gaps**: Missing context utilization or ineffective guidance application

**Resolution Strategy Framework:**

- **Priority Assessment**: Impact on workflow progression and quality outcomes
- **Implementation Approach**: Specific steps needed to resolve each identified gap
- **Resource Requirements**: Time investment and effort needed for gap resolution
- **Expected Outcomes**: Quality and workflow improvements from resolution implementation

**Traceability Assessment Summary Results:**

- **Requirements Coverage**: [Percentage and gap analysis across downstream stages]
- **Design Integration**: [Assessment of design element implementation coverage]
- **Task Completeness**: [Validation of complete implementation coverage]
- **Context Dependency Health**: [Analysis of context document utilization effectiveness]
- **Critical Gaps Identified**: [Priority-ordered list of missing traceability links with resolution strategies]

# Section 5: Steering System Integration Analysis

## Comprehensive Steering Assessment Framework

**Before evaluating steering integration, systematically plan assessment approach:**

1. What steering documents exist and how do they influence workflow quality?
2. How can steering effectiveness be measured with objective criteria?
3. What improvement opportunities enhance steering system impact?

**Execute systematic steering system integration assessment:**

## Core Steering Document Analysis

**Product Steering Assessment (product.md):**

**If product.md exists, execute comprehensive analysis:**

- **Content Assessment**: Product context completeness including vision, goals, constraints
- **Integration Evaluation**: Evidence of product context usage influencing workflow decisions
- **Quality Metrics**: Clarity, currency, and strategic alignment with project objectives
- **Workflow Influence**: Specific examples of product guidance affecting requirements and design decisions

**Product Steering Results:**

- **Content Quality**: [Product context completeness and clarity assessment]
- **Integration Score**: [Evidence of product guidance influence on workflow]
- **Strategic Alignment**: [Quality of product vision integration with workflow decisions]

**Technical Steering Assessment (tech.md):**

**If tech.md exists, execute comprehensive analysis:**

- **Content Assessment**: Technology stack and architectural decision completeness
- **Integration Evaluation**: Evidence of technical context usage in design and implementation
- **Quality Metrics**: Technical accuracy, decision rationale, and implementation guidance
- **Workflow Influence**: Specific examples of technical guidance affecting architecture and implementation decisions

**Technical Steering Results:**

- **Content Quality**: [Technology guidance completeness and technical accuracy]
- **Integration Score**: [Evidence of technical context influence on design decisions]
- **Implementation Guidance**: [Quality of technical standards application in workflow]

**Structure Steering Assessment (structure.md):**

**If structure.md exists, execute comprehensive analysis:**

- **Content Assessment**: File organization and pattern guidance completeness
- **Integration Evaluation**: Evidence of structure context usage in task creation and organization
- **Quality Metrics**: Pattern consistency, organizational clarity, and implementation utility
- **Workflow Influence**: Specific examples of structure guidance affecting code organization and task planning

**Structure Steering Results:**

- **Content Quality**: [Code organization guidance completeness and clarity]
- **Integration Score**: [Evidence of structure context influence on task organization]
- **Implementation Utility**: [Quality of structure patterns application in workflow]

## Custom Steering Document Analysis

**Domain-Specific Steering Assessment:**

**If custom steering documents exist (API standards, testing, security, performance, database, deployment):**

**Custom Steering Evaluation Framework:**

- **Domain-specific steering presence and quality assessment** across relevant project areas
- **Specialized context integration** effectiveness in workflow enhancement (API standards, testing, security, etc.)
- **Custom steering workflow effectiveness** in providing domain-specific guidance
- **Conditional inclusion pattern utilization** assessment if file pattern matching implemented

**Custom Steering Results:**

- **Domain Coverage**: [Assessment of specialized steering areas and their quality]
- **Integration Effectiveness**: [Quality of domain-specific guidance influence on workflow]
- **Pattern Utilization**: [Effectiveness of conditional loading and pattern matching]

## Steering System Effectiveness Assessment

**Comprehensive Steering Influence Analysis:**

**Requirements Stage Influence:**

- Evidence of steering context influencing requirements prioritization and scope decisions
- Product steering impact on requirement selection and business value assessment
- Technical steering influence on non-functional requirements and constraint identification
- Structure steering effect on requirement organization and categorization

**Design Stage Influence:**

- Evidence of steering context guiding design decisions and architecture choices
- Product steering impact on feature prioritization and user experience decisions
- Technical steering influence on technology choices and architectural patterns
- Structure steering effect on component organization and interface design

**Implementation Stage Influence:**

- Evidence of steering context informing task organization and implementation approach
- Product steering impact on implementation priorities and quality gates
- Technical steering influence on coding standards and technical implementation
- Structure steering effect on code organization and development workflow

**Overall Steering Effectiveness:**

- **Context Integration Score**: [Measurement of steering influence across all workflow stages]
- **Guidance Impact**: [Assessment of steering effectiveness in maintaining project consistency]
- **Quality Enhancement**: [Evaluation of steering contribution to workflow quality]

## Steering System Enhancement Opportunities

**Strategic Steering Improvement Analysis:**

**Missing Steering Assessment:**

- **Missing steering documents** that would benefit current work and project needs
- **Outdated steering content** requiring updates for current project state and technology
- **Quality improvement opportunities** for enhanced guidance effectiveness
- **Custom steering potential** for specialized domain needs and project requirements

**Enhancement Recommendations:**

- **Core Steering Improvements**: Specific enhancements to product, technical, or structure guidance
- **Custom Steering Opportunities**: Domain-specific steering needs for project enhancement
- **Integration Improvements**: Better steering utilization strategies for workflow enhancement
- **Quality Standards**: Steering document quality improvements for enhanced effectiveness

**Steering Integration Assessment Results:**

- **Core Steering Effectiveness**: [Analysis of product.md, tech.md, structure.md impact on workflow]
- **Context Integration Score**: [Measurement of steering influence on workflow document quality]
- **Guidance Completeness**: [Assessment of steering coverage for current project needs]
- **Improvement Opportunities**: [Specific recommendations for steering system enhancement]

# Section 6: Quality Control Dashboard

## Comprehensive Project Health Assessment Framework

**Before calculating combined health metrics, systematically plan assessment methodology:**

1. How should health scores be weighted across assessment dimensions?
2. What stage-specific metrics provide maximum project insight?
3. What issue categorization enables optimal improvement prioritization?

**Execute comprehensive project health assessment across all dimensions:**

## Overall Project Health Score Calculation

**Combined Health Score Methodology:**

**Primary Health Dimensions:**

- **Workflow Progression Score** (30% weighting): Stage completion and approval gate status
- **Document Quality Score** (25% weighting): Weighted average across all document quality metrics
- **Traceability Completeness Score** (25% weighting): Cross-stage mapping effectiveness and accuracy
- **Steering Integration Score** (20% weighting): Context utilization and guidance effectiveness

**Health Score Calculation Process:**

**Workflow Progress Component** (30%):

- Requirements Stage: [Generated + Approved] / 2 = [X%] of 25% maximum
- Design Stage: [Generated + Approved] / 2 = [X%] of 25% maximum
- Implementation Planning Stage: [Generated + Approved] / 2 = [X%] of 25% maximum
- Task Execution Stage: [Completed Tasks / Total Tasks] = [X%] of 25% maximum
- **Workflow Progress Score**: [Sum of all stages] (0-100%)

**Document Quality Component** (25%):

- Requirements Quality: [Score if exists] weighted by document importance
- Design Quality: [Score if exists] weighted by document importance
- Implementation Plan Quality: [Score if exists] weighted by document importance
- **Document Quality Score**: [Weighted average across existing documents] (0-100%)

**Traceability Component** (25%):

- Requirements → Design Coverage: [Percentage] weighted by mapping importance
- Requirements → Task Coverage: [Percentage] weighted by mapping importance
- Design → Task Coverage: [Percentage] weighted by mapping importance
- Context Integration: [Score] weighted by integration importance
- **Traceability Score**: [Weighted average across all mappings] (0-100%)

**Steering Integration Component** (20%):

- Core Steering Effectiveness: [Score] for product, tech, structure guidance
- Custom Steering Effectiveness: [Score] for domain-specific guidance
- Context Integration Quality: [Score] for guidance influence on workflow
- **Steering Integration Score**: [Weighted average across steering elements] (0-100%)

**Combined Health Score Calculation:**
**Overall Health Score** = (Workflow × 0.30) + (Document × 0.25) + (Traceability × 0.25) + (Steering × 0.20) = [X%]

## Stage-Specific Quality Metrics Dashboard

**Requirements Stage Metrics (if requirements.md exists):**

- **EARS Format Compliance**: [X%] - Percentage of acceptance criteria using proper EARS patterns
- **User Story Structure Adherence**: [X%] - Rate of proper "As a/I want/so that" template usage
- **Coverage Completeness**: [X%] - Assessment across functional/non-functional/technical/edge cases
- **Content Quality Rating**: [X%] - Clarity, testability, scope appropriateness, value articulation

**Design Stage Metrics (if design.md exists):**

- **Section Completeness**: [X%] - Percentage of 6 mandatory sections present and complete
- **Research Integration Effectiveness**: [X%] - Rating of research findings incorporation quality
- **Requirement Coverage Completeness**: [X%] - Percentage of requirements addressed in design
- **Technical Quality Assessment**: [X%] - Architecture, interfaces, data models evaluation

**Implementation Stage Metrics (if tasks.md exists):**

- **Format Compliance**: [X%] - Percentage checkbox structure and hierarchy compliance
- **Coding Exclusivity Compliance**: [X%] - Rate of tasks involving only coding activities
- **Requirement Traceability Completeness**: [X%] - Percentage of requirements with corresponding tasks
- **Task Quality Assessment**: [X%] - Clarity, actionability, progression logic evaluation

## Kiro Behavioral Constraint Compliance Assessment

**Workflow Integrity Validation:**

- **Stage Progression Rule Adherence**: Assessment of proper approval gate progression without stage skipping
- **Document Format Compliance**: Evaluation of template adherence across all workflow documents
- **Quality Standard Maintenance**: Analysis of consistent quality application throughout workflow
- **Approval Process Integrity**: Assessment of explicit approval requirement compliance

**Constraint Compliance Results:**

- **Stage Progression**: [Compliant/Non-compliant] - [Specific issues if any]
- **Document Format**: [X% compliance] - [Template adherence across documents]
- **Quality Standards**: [Maintained/Degraded] - [Quality consistency analysis]
- **Approval Process**: [Proper/Compromised] - [Approval gate integrity assessment]

## Issue Identification and Severity Assessment

**Comprehensive Issue Categorization:**

**Critical Issues (Immediate Attention Required):**

- **Workflow Blockers**: Issues preventing progression to next stage or completion
- **Quality Failures**: Document quality below minimum standards affecting workflow integrity
- **Traceability Gaps**: Missing connections between stages creating implementation risk
- **Compliance Violations**: Kiro standard adherence failures affecting workflow validity

**Important Issues (High Impact Quality Concerns):**

- **Quality Gaps**: Document improvements needed for enhanced effectiveness
- **Integration Improvements**: Steering utilization enhancements for better guidance
- **Coverage Gaps**: Missing elements reducing workflow completeness
- **Process Improvements**: Workflow efficiency enhancements for better outcomes

**Enhancement Opportunities (Optimization Potential):**

- **Quality Optimization**: Improvements for workflow excellence and best practice adoption
- **Integration Enhancement**: Better steering and context utilization for improved outcomes
- **Process Refinement**: Workflow efficiency improvements and standardization opportunities
- **Tool Utilization**: Better use of Kiro capabilities for enhanced productivity

**Compliance Concerns (Standard Adherence):**

- **Template Compliance**: Format and structure adherence improvements needed
- **Process Compliance**: Workflow step adherence and approval gate compliance
- **Quality Compliance**: Standard maintenance and consistency improvements
- **Documentation Compliance**: Complete and proper documentation standard adherence

## Quality Trend Analysis and Pattern Identification

**Workflow Quality Progression Assessment:**

- **Document Quality Progression**: Analysis of quality development across workflow stages
- **Consistency Maintenance**: Assessment of quality and standard consistency across elements
- **Quality Improvement Opportunities**: Identification of enhancement potential and implementation approaches
- **Standards Compliance Trend**: Assessment of adherence patterns and compliance development

**Pattern Analysis Results:**

- **Quality Trend**: [Improving/Stable/Declining] - [Specific pattern analysis]
- **Consistency Pattern**: [Maintained/Variable] - [Cross-workflow element analysis]
- **Improvement Opportunities**: [Specific areas with enhancement potential]
- **Compliance Trend**: [Improving/Stable/Declining] - [Standard adherence pattern]

**Quality Control Dashboard Summary Results:**

- **Combined Health Score**: [X%] - [Weighted calculation with complete methodology transparency]
- **Stage-Specific Metrics**: [Detailed breakdown per workflow stage with specific scores]
- **Compliance Assessment**: [Kiro behavioral constraint adherence analysis with specific findings]
- **Issue Priority Matrix**: [Categorized issues with severity assessment and resolution priorities]
- **Quality Trend Analysis**: [Progression patterns and improvement opportunities with implementation guidance]

# Section 7: Strategic Recommendations and Next Steps

## Strategic Workflow Guidance Framework

**Before generating recommendations, systematically analyze optimal workflow progression:**

1. What is the current workflow state and what are the logical next steps?
2. What quality improvements provide maximum workflow enhancement value?
3. What strategic insights enable long-term workflow success?

**Execute comprehensive strategic assessment and recommendation generation:**

## Strategic Assessment Process Implementation

**Systematic Workflow State Evaluation:**

**Current State Analysis:**
First, systematically evaluate workflow completion state against all 4 Kiro stages including approval status, document quality, and progression readiness.

**Quality Assessment Integration:**
Then, analyze document quality against established Kiro standards with quantitative scoring to identify improvement priorities and implementation approaches.

**Traceability Validation:**
Next, assess cross-stage traceability to validate workflow integrity, identify missing connections, and determine gap resolution priorities.

**Strategic Synthesis:**
Finally, synthesize all findings into prioritized recommendations with clear reasoning, expected outcomes, and implementation guidance.

## Logical Next Command Recommendations

**Based on comprehensive workflow state analysis, provide specific command recommendations:**

### If Workflow is Incomplete (Missing Stages or Approvals)

**Stage-Specific Recommendations:**

**If Requirements Stage Incomplete:**

- **Command Recommendation**: `/kiro:2-requirements-clarification [feature-name]`
- **Reasoning**: Requirements foundation needed for design and implementation stages
- **Expected Outcome**: Complete requirements document with EARS format compliance and user approval
- **Priority**: High - Blocks all subsequent workflow stages

**If Design Stage Incomplete:**

- **Command Recommendation**: `/kiro:3-design-document-creation [feature-name]`
- **Reasoning**: Architecture foundation needed for implementation planning and task execution
- **Expected Outcome**: Research-informed design document with 6-section completeness and user approval
- **Priority**: High - Required for systematic implementation planning

**If Implementation Planning Incomplete:**

- **Command Recommendation**: `/kiro:4-implementation-planning [feature-name]`
- **Reasoning**: Task breakdown needed for systematic code implementation and progress tracking
- **Expected Outcome**: Complete task list with requirements traceability and user approval
- **Priority**: High - Necessary for organized task execution

**Quality Improvement Priorities:**

- **Document Quality Enhancement**: Focus on [specific quality gaps] before stage progression
- **Traceability Strengthening**: Address [specific missing connections] for workflow integrity
- **Steering Integration**: Improve [specific guidance utilization] for enhanced quality

### If Workflow is Progressing Normally

**Next Logical Stage Recommendations:**

**If Ready for Next Stage:**

- **Command Recommendation**: [Next appropriate Kiro command based on current completion]
- **Preparation Guidance**: [Specific preparation activities for optimal next stage execution]
- **Quality Validation Suggestions**: [Recommended validation activities before stage progression]
- **Expected Timeline**: [Estimated time investment and resource requirements]

**Progression Optimization:**

- **Quality Preparation**: [Specific improvements to enhance next stage success]
- **Context Enhancement**: [Steering or documentation improvements for better outcomes]
- **Process Optimization**: [Workflow efficiency improvements for enhanced progression]

### If Workflow is Complete (All Stages Approved)

**Task Execution Recommendations:**

**If Ready for Implementation:**

- **Command Recommendation**: `/kiro:5-task-execution [feature-name]`
- **Specific Task Suggestions**: [Recommended starting task based on dependency analysis]
- **Execution Strategy**: [Optimal task sequence and implementation approach]
- **Quality Maintenance**: [Standards to maintain during implementation]

**Feature Completion Assessment:**

- **Implementation Progress**: [Assessment of task completion and remaining work]
- **Quality Validation**: [Validation activities for completed implementation]
- **Next Feature Planning**: [Guidance for subsequent feature development]

## Quality Improvement Recommendations

### Critical Quality Issues (Immediate Attention Required)

**High-Priority Improvements:**

- **[Specific Issue 1]**: [Detailed improvement guidance with examples and implementation steps]
- **[Specific Issue 2]**: [Template compliance corrections with exact formatting requirements]
- **[Specific Issue 3]**: [Content completeness gaps with specific addition recommendations]

**Implementation Approach:**

- **Priority Sequence**: [Order of improvement implementation for maximum impact]
- **Resource Requirements**: [Time investment and effort needed for improvement completion]
- **Expected Outcomes**: [Specific quality enhancements and workflow improvements]

### Important Quality Enhancements (High Impact Improvements)

**Strategic Improvements:**

- **Document Quality Enhancement**: [Specific document improvements with targeted suggestions]
- **Traceability Strengthening**: [Cross-stage mapping improvements with detailed guidance]
- **Steering Integration Enhancement**: [Better context utilization strategies with implementation approaches]

**Enhancement Strategy:**

- **Implementation Priority**: [Sequence of enhancements for optimal quality improvement]
- **Quality Impact**: [Expected quality score improvements and workflow benefits]
- **Long-term Benefits**: [Sustained quality improvements and workflow excellence]

## Workflow Optimization Recommendations

**Process Efficiency Improvements:**

- **Workflow Efficiency**: [Specific process improvements based on current state analysis]
- **Quality Standard Maintenance**: [Strategies for sustained excellence and consistency]
- **Integration Opportunities**: [Better utilization of project context and steering guidance]
- **Tool Utilization**: [Enhanced use of Kiro capabilities for improved productivity]

**Optimization Strategy:**

- **Implementation Approach**: [Specific steps for workflow optimization]
- **Efficiency Gains**: [Expected productivity improvements and time savings]
- **Quality Benefits**: [Enhanced output quality and consistency improvements]

## Issue Resolution Strategies

**Systematic Resolution Approach:**

- **[Issue Category 1]**: [Specific resolution approaches with step-by-step guidance]
- **[Issue Category 2]**: [Priority sequencing for multiple issue resolution]
- **[Issue Category 3]**: [Resource and time investment guidance for improvement completion]

**Resolution Framework:**

- **Priority Matrix**: [Issue resolution order based on impact and effort assessment]
- **Implementation Timeline**: [Realistic timeframes for resolution completion]
- **Success Metrics**: [Validation criteria for resolution effectiveness]

## Strategic Workflow Insights and Long-Term Excellence

**Long-Term Workflow Health Assessment:**

- **Sustainability Analysis**: [Assessment of workflow maintainability and long-term success potential]
- **Scalability Considerations**: [Evaluation of workflow effectiveness as project grows]
- **Quality Trajectory**: [Analysis of quality development and improvement trends]

**Pattern Identification for Process Improvement:**

- **Success Patterns**: [Identification of effective workflow elements for replication]
- **Risk Patterns**: [Recognition of potential issues for proactive prevention]
- **Optimization Patterns**: [Best practice recommendations based on current workflow characteristics]

**Best Practice Recommendations:**

- **Workflow Excellence**: [Standards and practices for sustained high-quality outcomes]
- **Process Consistency**: [Approaches for maintaining workflow integrity across features]
- **Quality Assurance**: [Validation strategies for continuous quality improvement]

**Success Metric Tracking Suggestions:**

- **Progress Metrics**: [Specific measurements for workflow advancement tracking]
- **Quality Metrics**: [Assessment criteria for ongoing quality evaluation]
- **Efficiency Metrics**: [Productivity measurements for process optimization]

## Educational Context and Implementation Guidance

**For each recommendation, comprehensive educational context:**

**Value Explanation:**

- **Clear reasoning** for why specific recommendations provide value for workflow progression
- **Expected outcomes** from following guidance with measurable improvement indicators
- **Connection to Kiro principles** and quality standards for educational understanding
- **Resource requirements** and time investment expectations for realistic planning

**Implementation Support:**

- **Step-by-step guidance** for recommendation implementation with specific actions
- **Quality validation** approaches for ensuring improvement effectiveness
- **Success criteria** for measuring recommendation completion and impact
- **Follow-up strategies** for sustained improvement and quality maintenance

**Strategic Recommendations Summary Results:**

- **Immediate Next Steps**: [Priority-ordered command recommendations with clear reasoning and expected outcomes]
- **Quality Improvement Plan**: [Specific actions to enhance workflow quality with implementation guidance]
- **Long-term Strategy**: [Insights for sustained workflow excellence and process optimization]
- **Educational Guidance**: [Clear reasoning and expected outcomes for all recommendations with implementation support]

# Analysis Quality Reflection and Validation

## Systematic Analysis Validation Framework

**After completing comprehensive analysis across all 7 dimensions, systematically validate analysis quality:**

**Before presenting final results, reflect on analysis completeness and actionability:**

1. Have all 7 analysis dimensions been thoroughly assessed with appropriate depth?
2. Are quality scores calculated using transparent methodology with clear explanations?
3. Are strategic recommendations actionable and appropriately prioritized for maximum value?
4. Do all identified gaps have corresponding resolution strategies with implementation guidance?

**Analysis Completeness Validation:**

- **Dimension Coverage**: Verify all 7 analysis dimensions (Context validation, workflow progress, document quality, cross-stage traceability, steering integration, quality control dashboard, strategic recommendations) have been thoroughly assessed
- **Quality Methodology**: Confirm quality scores calculated using transparent methodology with weighting explanations and calculation transparency
- **Recommendation Actionability**: Validate strategic recommendations are actionable and appropriately prioritized based on objective assessment criteria
- **Gap Resolution**: Ensure all identified gaps and issues have corresponding resolution strategies with clear implementation guidance

**Assessment Accuracy Validation:**

- **Document Analysis**: Verify all document assessments based on complete content reading and comprehensive evaluation
- **Scoring Transparency**: Confirm all scoring includes clear methodology explanation and weighting rationale
- **Recommendation Basis**: Validate all recommendations based on objective assessment criteria rather than subjective preferences
- **Educational Value**: Ensure all assessments include clear reasoning and expected outcomes for user understanding

**Read-Only Operations Compliance:**

- **Analysis Integrity**: Check that analysis maintains complete read-only operations throughout entire assessment process
- **Non-Modification Confirmation**: Verify no files or workflow state modified during analysis execution
- **Diagnostic Focus**: Confirm analysis focused on insights and recommendations without system alterations
- **Educational Approach**: Validate analysis provides educational feedback enhancing understanding without requiring file modifications

**Strategic Value Assessment:**

- **Actionable Insights**: Verify analysis provides insights that enhance workflow progression and quality
- **Implementation Guidance**: Confirm recommendations include clear implementation approaches and expected outcomes
- **Priority Assessment**: Validate issues prioritized by impact on workflow progression and quality enhancement
- **Resource Consideration**: Ensure recommendations include resource requirements and time investment expectations

**Analysis Quality Summary:**

- **Comprehensive Coverage**: All 7 dimensions assessed with appropriate depth and educational reasoning
- **Methodological Transparency**: All scoring and assessment approaches clearly explained with calculation transparency
- **Strategic Actionability**: Recommendations prioritized and actionable with clear implementation guidance
- **Educational Value**: Analysis enhances user understanding of workflow health and improvement opportunities
- **Read-Only Integrity**: Complete diagnostic analysis accomplished without any file modifications or state changes

**This comprehensive analysis maintains Kiro's rigorous quality standards while providing actionable insights for productive workflow progression, ensuring your spec-driven development process remains effective, high-quality, and aligned with established best practices.**
