---
description: "Execute Kiro Stage 1 requirements clarification with comprehensive EARS format validation"
mode: agent
---

# Kiro Requirements Clarification Workflow

## Methodology Reinforcement

You are executing Kiro Stage 1: systematic requirements generation with the following approach:

- **EARS Format Compliance**: All acceptance criteria use exact EARS patterns across 8 standardized categories
- **Reasoning-Based Scope Discipline**: Clear boundary explanations rather than prohibition language
- **Intelligent Draft State Detection**: Analyze existing state and route workflow optimally for user efficiency
- **Bounded Context Gathering**: Accumulate user input before generation, no sequential questioning during generation
- **Systematic Scope Planning**: Establish explicit boundaries before requirements creation with reasoning
- **Quality Validation**: Transparent frameworks with educational feedback for continuous improvement
- **Cross-Stage Traceability**: Requirements serve as foundation for design and implementation stages

## Systematic Requirements Analysis Framework

First, systematically analyze all available context (user input, spec.yaml, steering documents) to understand complete project landscape.

Then, identify scope boundaries by evaluating user needs against project constraints and steering guidance.

Next, categorize requirements systematically across all 8 Kiro requirement categories ensuring comprehensive coverage.

Finally, generate requirements using exact EARS format and user story templates with complete traceability to user context.

# Context Loading and Validation Process

## Step 1: Feature Selection and Validation

**Before proceeding, think step by step about:**

1. What features are available in the .kiro/specs/ directory?
2. Does the specified feature exist and have proper initialization?
3. What context documents should be loaded for requirements generation?

**Execution Process:**

- Check for available features in .kiro/specs/ directory using appropriate tools
- If feature argument missing, display available features and wait for user selection
- If feature doesn't exist, provide guidance on using feature initialization first
- Validate feature has proper spec.yaml structure before proceeding

## Step 2: Context Document Loading

**Systematic Context Loading Strategy:**

**Think through what context is available:**

- Feature specification: .kiro/specs/[feature-name]/spec.yaml
- Existing requirements: .kiro/specs/[feature-name]/requirements.md (if exists)
- Product steering: .kiro/steering/product.md (if exists)
- Technical steering: .kiro/steering/tech.md (if exists)
- Structure steering: .kiro/steering/structure.md (if exists)

**Load all available context documents systematically:**

- Read complete content of each available document
- Validate document accessibility and completeness
- Note any missing context that might affect requirements quality

## Step 3: Prerequisites Validation

**Critical Stage 1 Prerequisites Assessment:**

**Before proceeding with requirements generation, verify:**

- Feature is properly initialized with valid spec.yaml
- No conflicting approval states exist for requirements
- Context documents are accessible and complete for guidance
- User is ready to provide or has provided requirements context

**If prerequisites not met:**

- Explain specific missing requirements and their impact
- Provide exact commands needed to resolve issues
- Wait for prerequisite resolution before continuing with requirements generation

# Draft State Detection and Intelligent Workflow Routing

## Comprehensive State Analysis Process

**After loading all context documents, systematically analyze the current requirements state:**

**Think step by step about the optimal workflow path:**

1. Does requirements.md already exist for this feature?
2. What is the generation and approval status from spec.yaml?
3. What workflow path provides the best user experience and efficiency?

**State Detection Framework:**

### State 1: Fresh Requirements Generation Path

**Conditions**: requirements.generated: false OR requirements.md doesn't exist
**Workflow**: Context gathering → scope planning → requirements generation → review
**User Experience**: Complete requirements creation process with context gathering and validation

### State 2: Existing Draft Review Path

**Conditions**: requirements.generated: true AND requirements.approved: false
**Workflow**: Load existing requirements → direct to review cycle
**User Experience**: Efficient review and refinement of existing draft
**Efficiency Note**: "Since I've loaded the requirements.md content along with all project context, I can immediately present your existing requirements for review and potential modification."

### State 3: Requirements Complete

**Conditions**: requirements.generated: true AND requirements.approved: true
**Workflow**: Inform user of completion status → provide next stage guidance
**User Experience**: Clear status communication and next steps
**Next Step**: "Requirements have been approved and finalized. Use /kiro:3-design-document-creation [feature-name] to proceed to design stage."

**Selected Workflow Path Determination:**
Based on systematic state analysis, the optimal path is: [State X - reasoning for selection]

**Proceeding with selected workflow path...**

# Context Gathering and Scope Planning Process

## Phase 1: Context Accumulation

**Explicit Context Gathering Approach:**

**Before requesting context, think about what information is needed:**

1. What specific functionality is the user envisioning?
2. What constraints or requirements might already exist in the project?
3. What steering guidance should inform requirements scope?

**Context Collection Process:**
I'm ready to generate comprehensive requirements for this feature following all Kiro standards.

**If you have any context to share, please provide it now:**

- Initial ideas, user stories, or scenarios you're envisioning
- Technical constraints or integration requirements you already know
- Performance, security, or usability considerations
- Examples or references you'd like me to consider
- Any other relevant context or requirements you have in mind

**Context Accumulation Strategy:**

- You can share as much or as little as you'd like in one or multiple messages
- I'll accumulate all requirements context before moving to scope planning
- No follow-up questions during accumulation phase - provide complete context now

**When you're ready for me to proceed with generating the requirements draft, just say 'proceed' or 'generate requirements'**

**Wait for user context inputs until they say to proceed**

## Phase 2: Systematic Scope Planning

**After gathering user context, carefully analyze all provided information to identify scope boundaries:**

**Before presenting scope plan, analyze all gathered information:**

1. What core features should be included based on user context?
2. What related functionality might be tempting to add but should be excluded?
3. What boundaries would enable focused, high-quality requirements?

**Present Comprehensive Scope Plan:**

Based on your context, here's what I understand you want built:

### Core Features to Include

- **[Feature 1]**: [Reasoning based on specific user context provided]
- **[Feature 2]**: [Logical necessity for specific scenario mentioned]
- **[Essential capability X]**: [Required for stated user need]

### Features NOT Included (Reasoning-Based Boundaries)

**Resource Focus Boundaries:**

- **[Common feature Y]**: Not mentioned in your context, would create unnecessary complexity that diverts attention from core functionality
- **[Advanced capability Z]**: Beyond current scope, adding this would require extensive additional planning not indicated by user needs
- **[Speculative requirement]**: No clear indication this addresses your actual use case, would add maintenance burden without validated benefit

**Why These Boundaries Matter:**

**Resource Focus**: Defining only needed requirements allows concentrated effort on understanding and specifying core functionality rather than spreading across speculative features.

**Implementation Efficiency**: Each additional requirement creates development overhead - coding, testing, documentation, maintenance that compounds throughout the project lifecycle.

**User Experience Coherence**: Requirements should serve the user's stated needs. Adding unmentioned features can create confusion and complexity for users.

**Project Success**: Clear boundaries prevent scope creep, which is a primary cause of project delays and budget overruns.

**Boundary Questions:**

- Should I include [borderline feature]? (Related to your context but not explicit)
- Any scope boundaries you want me to respect?
- Features you specifically want me to avoid adding?

**Scope looks right? Say 'proceed' to generate requirements within these boundaries.**

**Wait for user confirmation of scope plan before proceeding to requirements generation**

# Requirements Generation Process

## Pre-Generation Quality Planning

**Before generating requirements document, systematically plan the approach:**

**Think step by step about:**

1. How will I integrate all loaded context (user input, steering guidance, project constraints)?
2. What template structure will ensure comprehensive coverage across all 8 categories?
3. How will I maintain scope discipline throughout generation?
4. What quality standards must be met for each requirement category?

**Generation Strategy:**

- Apply exact Kiro requirements template structure
- Use precise EARS format for all acceptance criteria
- Integrate steering document guidance throughout all categories
- Maintain reasoning-based scope discipline with clear boundary documentation
- Ensure complete traceability from user context to requirements

## Comprehensive Requirements Document Generation

**Creating requirements document incorporating:**

- User-provided context and ideas from context gathering phase
- Feature description from spec.yaml with project context
- Steering document guidance (product, tech, structure) throughout all categories
- Industry best practices and comprehensive coverage within approved scope
- Exact Kiro behavioral constraints and formatting standards

**Generate requirements document at .kiro/specs/[feature-name]/requirements.md using exact template specification:**

<kiro_requirements_template>

```markdown
# [feature-name] Requirements

## Introduction

[SPECIFICATION: Clear 2-3 sentence feature summary incorporating user context, steering guidance, and scope boundaries. Must establish clear purpose and value proposition based on all gathered information.]

## Requirements

### 1. Core Functionality Requirements

[SPECIFICATION: Primary functional requirements using exact user story format. Must address core user needs from gathered context.]
**User Story**: As a [role from user context], I want [feature based on user input], so that [benefit derived from user context]

**Acceptance Criteria**:
[SPECIFICATION: Use exact EARS format patterns - shall/when-shall/should/while-when-shall]

1. The system shall [specific action/capability derived from user context]
2. When [condition from user requirements], the system shall [response/behavior]
3. The system should [optional/preferred behavior based on user preferences]
4. While [state], when [trigger], the system shall [complex conditional behavior]

### 2. User Experience Requirements

[SPECIFICATION: UX requirements focusing on user interaction patterns and usability needs from context.]
**User Story**: As a [user type from context], I want [interaction capability from user input], so that [user value from context]

**Acceptance Criteria**:

1. The system shall [UX requirement based on user context]
2. When [user action from context], the system shall [response requirement]
3. The system should [usability enhancement derived from user needs]

### 3. Technical Requirements

[SPECIFICATION: Technical constraints and system requirements based on steering guidance and user context.]
**User Story**: As a [system/developer], I want [technical capability from steering context], so that [technical benefit]

**Acceptance Criteria**:

1. The system shall [technical constraint/requirement from steering documents]
2. The system shall [integration requirement based on project context]
3. The system should [performance requirement appropriate to user context]

### 4. Security Requirements

[SPECIFICATION: Security controls and protection mechanisms appropriate for user context and project needs.]
**User Story**: As a [stakeholder], I want [security protection relevant to user context], so that [security benefit]

**Acceptance Criteria**:

1. The system shall [security control appropriate to user data/functionality]
2. When [security event relevant to feature], the system shall [security response]
3. The system shall [compliance requirement based on project context]

### 5. Error Handling Requirements

[SPECIFICATION: Error detection, response, and recovery mechanisms for system robustness.]
**User Story**: As a [user], I want [error recovery relevant to user workflow], so that [continuity benefit]

**Acceptance Criteria**:

1. The system shall [error detection for user-relevant failure modes]
2. When [error condition relevant to feature], the system shall [error response]
3. The system shall [recovery mechanism appropriate to user needs]

### 6. Performance Requirements

[SPECIFICATION: Performance expectations, scalability needs, and optimization targets from context.]
**User Story**: As a [user], I want [performance expectation from context], so that [efficiency benefit]

**Acceptance Criteria**:

1. The system shall [performance metric appropriate to user needs]
2. The system shall [scalability requirement based on user context]
3. The system should [optimization target derived from user requirements]

### 7. Integration Requirements

[SPECIFICATION: External system connections and API requirements based on project needs.]
**User Story**: As a [system integrator], I want [integration capability from context], so that [integration benefit]

**Acceptance Criteria**:

1. The system shall [integration interface based on project context]
2. The system shall [data exchange requirement from user needs]
3. The system should [compatibility requirement from steering guidance]

### 8. Edge Case Requirements

[SPECIFICATION: Boundary conditions, validation scenarios, and failure handling for system robustness.]
**User Story**: As a [user], I want [edge case handling relevant to user workflow], so that [robustness benefit]

**Acceptance Criteria**:

1. The system shall [boundary condition handling for user scenarios]
2. When [invalid input relevant to feature], the system shall [validation response]
3. When [system failure affecting user], the system shall [failure response]
4. The system shall [data integrity protection for user data]

## Requirements Scope Boundaries (Reasoning-Based)

### Features Explicitly NOT Included

[SPECIFICATION: List features not in user context that would create unnecessary complexity.]

- **[Feature 1]**: Not included because user context focused on [specific area], adding this would create unnecessary complexity that diverts resources from core functionality
- **[Feature 2]**: Excluded because no indication this addresses user's stated needs, would add development and maintenance burden without validated benefit
- **[Advanced capability]**: Not in current requirements scope, represents future consideration that would require separate planning and validation

### Non-Functional Elements NOT Included

[SPECIFICATION: Performance levels, security measures, integrations beyond stated needs.]

- **[Performance level X]**: Beyond performance needs indicated by user context and project constraints
- **[Security measure Y]**: Not required for described use case and user data sensitivity level
- **[Integration Z]**: Not mentioned in user context or project steering requirements

### Edge Cases NOT Addressed

[SPECIFICATION: Low-probability scenarios that would add significant complexity.]

- **[Extreme edge case 1]**: Very low probability scenario that would add significant implementation complexity without proportional user benefit
- **[Theoretical scenario 2]**: Not relevant to user's stated workflows and usage patterns
- **[Speculative failure mode]**: Over-engineering for current scope, represents theoretical concern not validated by user needs

### Why These Boundaries Matter

**Resource Focus**: Defining only needed requirements allows concentrated effort on understanding and specifying core functionality rather than spreading across speculative features.

**Implementation Efficiency**: Each additional requirement creates development overhead - coding, testing, documentation, maintenance that compounds throughout the project lifecycle.

**User Experience Coherence**: Requirements should serve the user's stated needs. Adding unmentioned features can create confusion and complexity for users.

**Project Success**: Clear boundaries prevent scope creep, which is a primary cause of project delays and budget overruns.

### Future Considerations (Noted but NOT Required)

[SPECIFICATION: Potential enhancements for future evaluation - noted but not required.]

- **[Enhancement 1]**: Could be valuable in future iterations if user needs evolve toward [specific direction]
- **[Capability 2]**: Monitor usage patterns to evaluate need, implement only after proper requirements analysis
- **[Integration 3]**: Evaluate business case when integration opportunities emerge with validated user need

**Requirements Philosophy**: Focus on user's stated needs and essential supporting functionality, avoiding speculative additions that create unnecessary complexity without validated need.
```

</kiro_requirements_template>

**Execute comprehensive requirements generation based on all gathered context with complete scope discipline maintenance.**

## Post-Generation Quality Assessment

**After generating the complete requirements document, systematically reflect on quality and completeness:**

**Quality Assessment Framework:**

1. Do all requirements trace directly to user-provided context or logical necessity?
2. Are all acceptance criteria properly formatted using EARS patterns?
3. Is scope discipline maintained throughout with clear reasoning?
4. Are requirements testable and unambiguous for development teams?
5. Is steering document guidance appropriately integrated across all categories?

# Quality Validation Framework

## Comprehensive Quality Assessment Process

**Execute systematic quality validation across all critical dimensions:**

### Document Structure Validation

- Verify .kiro/specs/[feature-name]/requirements.md created successfully with complete content
- Confirm document contains Introduction section with clear feature summary incorporating all context
- Check requirements organized in hierarchical numbered list format (1., 2., 3.) across all 8 categories
- Validate document follows exact Kiro template structure with proper section organization
- Ensure all 8 requirement categories present and properly formatted

### User Story Structure Validation

- Verify each requirement includes exact format: "As a [role], I want [feature], so that [benefit]"
- Check role clearly identified and specific (user, admin, system, developer, etc.) for each story
- Confirm feature described concretely and actionably (not vague or ambiguous)
- Validate benefit articulates clear, measurable value proposition for stakeholders
- Ensure user stories align with provided context and user needs throughout all categories

### EARS Format Compliance Assessment

- Verify simple format: "The system shall [action]" compliance across all acceptance criteria
- Check conditional format: "When [condition], the system shall [action]" compliance
- Confirm optional format: "The system should [action]" compliance where appropriate
- Validate complex format: "While [state], when [condition], the system shall [action]" compliance
- Ensure no ambiguous language (avoiding "might", "could", "usually") throughout

### Coverage Completeness Evaluation

- Confirm functional requirements identified covering core capabilities from user context
- Check non-functional requirements included (Performance, security, usability, reliability)
- Verify technical constraints documented (Technology, infrastructure, integration requirements from steering)
- Validate edge cases addressed comprehensively (Invalid input, system failure, boundary conditions)
- Ensure success criteria defined with measurable outcomes across all categories
- Confirm user provided context fully incorporated throughout all requirement categories

### Context Integration Assessment

- Verify product steering guidance applied to feature prioritization and scope decisions
- Check technical steering constraints incorporated systematically into requirements specifications
- Confirm structural steering patterns reflected in requirement organization and standards
- Validate user context seamlessly integrated throughout all requirement categories
- Ensure steering document cross-references maintained where applicable

### Requirements Scope Discipline Validation

- Verify all requirements trace to user-provided context or logical necessity for feature completion
- Check no speculative or "nice to have" requirements added beyond provided context
- Confirm requirements complexity appropriate for stated use case and project scale
- Validate out of scope section documents boundary decisions clearly with sound reasoning
- Ensure edge cases limited to realistic scenarios within approved scope boundaries
- Check future considerations noted appropriately without being required in current scope

**Quality Validation Results:**

**Kiro Stage 1 Quality Assessment:**

- **Structure Validation**: Perfect compliance with Kiro template requirements and section organization
- **EARS Format Compliance**: All acceptance criteria properly formatted using 4 EARS patterns systematically
- **User Story Structure**: All stories follow exact "As a/I want/so that" template with clear roles and benefits
- **Coverage Analysis**: Comprehensive requirements across functional, non-functional, technical, and edge cases
- **Context Integration**: All user context and steering guidance successfully applied throughout
- **Scope Discipline**: Requirements focused on user context with clear reasoning-based boundaries documented

**Overall Quality Score**: [Calculated score based on comprehensive validation results with transparent methodology]

# Requirements Review and Iteration Process

## Requirements Draft Presentation

**Present completed requirements document with comprehensive assessment:**

**Generated Document Summary:**

- **Location**: .kiro/specs/[feature-name]/requirements.md
- **Quality Assessment**: [Comprehensive scoring across all validation dimensions with methodology]
- **Key Highlights**: [Major requirements categories and scope boundaries established]
- **Context Integration**: [How user input and steering guidance were incorporated]

I've generated comprehensive requirements following all Kiro Stage 1 standards, incorporating:

- Your context and input from our discussion
- Complete EARS format compliance with all 4 syntax patterns
- Comprehensive coverage across all 8 requirement categories
- All steering context guidance applied systematically
- Industry best practices for edge cases and error handling

## User Review Facilitation

**Guide user through systematic requirements review:**

**Key Review Considerations:**

- Do the requirements capture your vision and needs accurately?
- Are there any user stories or scenarios missing from your intended functionality?
- Do the acceptance criteria feel complete and testable for validation?
- Are technical constraints and integration needs addressed properly?
- Do performance and security requirements match your expectations?
- Are error handling and edge cases comprehensive enough for your use case?
- Is the language clear and unambiguous for development teams?
- Do the scope boundaries make sense and align with your project goals?

**User Review Options:**

- **Request Changes**: Tell me what needs to be modified, added, or refined in requirements
- **Minor Adjustments**: Point out specific sections that need tweaking or clarification
- **Scope Modifications**: Adjust what should be included or excluded from requirements scope
- **Ready to Approve**: If satisfied with requirements quality and completeness

**What's your feedback?**

## Iteration and Refinement Process

**If user requests changes, execute systematic refinement:**

**Before implementing modifications, carefully analyze specific feedback:**

1. What specific changes are being requested and why?
2. How do requested changes align with original user context and project constraints?
3. What modifications maintain Kiro compliance while addressing user needs?
4. How will changes affect scope boundaries and cross-stage traceability?

**Refinement Execution Process:**

1. **Analyze specific feedback** and identify precise areas requiring modification
2. **Update requirements.md** with requested changes while maintaining complete Kiro compliance
3. **Re-execute quality validation** to ensure all standards maintained including scope discipline
4. **Present updated version** for another review cycle with highlighted changes and improvements
5. **Continue iteration until explicit user approval** received with documented satisfaction

# Final Approval and State Management

## Requirements Approval Process

**Upon receiving explicit user approval:**

Thank you for the approval! The requirements document is now finalized and ready for the design stage.

**Update project state systematically:**

- Mark requirements stage as generated: true and approved: true in spec.yaml
- Update project timestamp to reflect Stage 1 completion
- Prepare project for Stage 2: Design Document Creation transition
- Document requirements approval for workflow traceability

**State Management Updates:**

```yaml
# Update .kiro/specs/[feature-name]/spec.yaml
approvals:
  requirements:
    generated: true
    approved: true
updated_at: "[current ISO timestamp]"
```

**Completion Validation:**

- Requirements document finalized with complete user approval
- Project state accurately reflects Stage 1 completion
- All quality standards met with documented validation
- Next stage prerequisites established and documented
- Cross-stage traceability foundations created for design and implementation

## Workflow Transition Guidance

**Provide clear guidance for next steps in Kiro workflow:**

**Stage 1 Completion Summary:**

- **Requirements Document**: Complete and approved following all Kiro standards with EARS format compliance
- **Quality Validation**: Comprehensive assessment passed with transparent methodology
- **Scope Boundaries**: Clearly established with reasoning-based discipline maintained
- **Context Integration**: All user input and steering guidance successfully incorporated
- **Workflow Foundation**: Solid requirements base established for subsequent stages

**Next Stage Preparation:**

- **Stage 2 Ready**: Design document creation can proceed with approved requirements foundation
- **Context Available**: Complete requirements will inform design decisions and architecture planning
- **Scope Inheritance**: Design stage will carry forward established scope boundaries with reasoning
- **Quality Standards**: Requirements approval demonstrates validation approach for subsequent stages

**Next Steps:**
Ready to proceed with **Stage 2: Design Document Creation**? Run:

```
/kiro:3-design-document-creation [feature-name]
```

**Kiro Stage 1 Complete - Requirements Clarification Successful!**
