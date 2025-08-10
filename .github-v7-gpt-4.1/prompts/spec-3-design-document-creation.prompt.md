---
description: "Execute Kiro Stage 2 design document creation with research integration and comprehensive validation"
mode: agent
---

# Kiro Design Document Creation Workflow

## Methodology Reinforcement

You are executing Kiro Stage 2: systematic design document creation with the following approach:

- **6-Section Design Template**: Create comprehensive design documents with exact structure: Overview, Architecture, Components and Interfaces, Data Models, Error Handling, Testing Strategy
- **Research Integration**: Conduct systematic research based on approved requirements to inform technology choices and architecture patterns
- **Reasoning-Based Scope Discipline**: Carry forward requirements boundaries with clear explanations rather than prohibition language
- **Draft State Intelligence**: Detect existing design state and route workflow optimally for user efficiency
- **Cross-Stage Traceability**: Maintain complete mapping from requirements to design components
- **Quality Validation**: Execute transparent frameworks with educational feedback for continuous improvement

## Systematic Research and Design Framework

First, systematically analyze all approved requirements to identify specific research areas and technology evaluation needs based on functional and non-functional requirements.

Then, conduct targeted research on identified areas including technology stack evaluation, architecture patterns, integration approaches, and security considerations relevant only to approved requirements.

Next, synthesize research findings into concrete technology recommendations and architectural decisions that serve the approved requirements without over-engineering.

Finally, validate that all research findings align with requirements scope and project constraints before proceeding to design planning and generation.

# Context Loading and Prerequisites Validation

## Step 1: Feature Selection and Validation

**Before proceeding, think step by step about:**

1. What features are available in the .kiro/specs/ directory?
2. Does the specified feature exist and have proper initialization?
3. What context documents should be loaded for design creation?

**Execution Process:**

- Check for available features in .kiro/specs/ directory using appropriate tools
- If feature argument missing, display available features and wait for user selection
- If feature doesn't exist, provide guidance on using feature initialization first
- Validate feature has proper spec.yaml structure before proceeding

## Step 2: Context Document Loading and Prerequisites Check

**Systematic Context Loading Strategy:**

**Think through what context is available:**

- Feature specification: .kiro/specs/[feature-name]/spec.yaml
- Approved requirements: .kiro/specs/[feature-name]/requirements.md (REQUIRED)
- Existing design: .kiro/specs/[feature-name]/design.md (if exists)
- Product steering: .kiro/steering/product.md (if exists)
- Technical steering: .kiro/steering/tech.md (if exists)
- Structure steering: .kiro/steering/structure.md (if exists)

**Load all available context documents systematically:**

- Read complete content of each available document
- Validate document accessibility and completeness
- Note any missing context that might affect design quality

## Step 3: Critical Prerequisites Assessment

**Before proceeding with design creation, verify:**

**Critical Stage 2 Prerequisites:**

- Feature is properly initialized with valid spec.yaml
- Requirements stage MUST be approved (check spec.yaml approval status)
- Requirements.md exists and accessible for design foundation
- Context documents loaded successfully for design guidance

**Prerequisites Validation:**

- Feature: [feature-name] initialized successfully
- Stage 1 (Requirements): MUST show requirements.approved: true in spec.yaml
- Requirements Document: requirements.md must exist and be readable
- Context Documents: Verify steering document accessibility

**If prerequisites not met:**

- Explain specific missing requirements and impact on design quality
- Provide exact commands needed to resolve issues
- For requirements not approved: redirect to /kiro:2-requirements-clarification [feature-name]
- Wait for prerequisite resolution before continuing with design creation

# Draft State Detection and Intelligent Workflow Routing

## Comprehensive State Analysis Process

**After loading all context documents, systematically analyze the current design state:**

**Think step by step about the optimal workflow path:**

1. Does design.md already exist for this feature?
2. What is the generation and approval status from spec.yaml?
3. What workflow path provides the best user experience?

**State Detection Framework:**

### State 1: Fresh Design Generation Path

**Conditions**: design.generated: false OR design.md doesn't exist
**Workflow**: Complete research integration → design planning → generation → review
**User Experience**: Full design creation process with research and validation

### State 2: Existing Draft Review Path

**Conditions**: design.generated: true AND design.approved: false
**Workflow**: Load existing design → optional research update → direct to review cycle
**User Experience**: Efficient review and refinement of existing draft
**Research Option**: "By default, I'll skip research phase for efficiency, but if you want updated research context, just say 'update research' and I'll conduct fresh research before review."

### State 3: Approved Design Complete

**Conditions**: design.generated: true AND design.approved: true
**Workflow**: Inform user of completion status → provide next stage guidance
**User Experience**: Clear status communication and next steps
**Next Step**: "Design document approved and ready for implementation planning. Use /kiro:4-implementation-planning [feature-name] to proceed."

**Selected Workflow Path Determination:**
Based on systematic state analysis, the optimal path is: [State X - reasoning for selection]

**Proceeding with selected workflow path...**

# Research Integration Phase

## Requirements Analysis for Research Planning

**Before conducting research, systematically analyze requirements to identify research needs:**

**Research Area Identification Process:**

1. What functional requirements drive technology stack decisions?
2. What non-functional requirements (performance, security, scalability) need research?
3. What integration requirements need architecture pattern research?
4. What domain-specific requirements need industry best practice research?

**Research Areas Identified from Requirements Analysis:**

- Technology stack evaluation for [specific functional requirements identified]
- Architecture pattern research for [system requirements from requirements.md]
- Integration approaches for [external system requirements from requirements.md]
- Security standards research for [security requirements from requirements.md]
- Performance optimization approaches for [performance requirements identified]
- Industry best practices for [domain-specific requirements from approved scope]

## User Research Preferences and Constraints Collection

**Research Preferences Gathering (Bounded Context Approach):**

**If you have research preferences or constraints, share them now:**

- Preferred technologies, frameworks, or tools you want me to consider
- Integration requirements or existing system constraints I should know about
- Performance, security, or compliance standards you must follow
- Architecture preferences or patterns you want to follow or avoid
- Technology restrictions or organizational standards that apply
- Any other technical guidance or constraints that should inform the design

**Context Accumulation Strategy:**

- You can share as much or as little as you'd like in one or multiple messages
- I'll accumulate all research context before proceeding with research execution
- No follow-up questions during research phase - provide complete context now

**When ready for research phase, say 'proceed with research' or 'start research'**

**Wait for user research preferences or proceed signal before continuing**

## Research Execution and Analysis

**After receiving proceed signal, conduct systematic research:**

**Before starting research, plan the research approach:**

1. What specific questions need answers based on requirements analysis?
2. What research sources and methods will provide reliable information?
3. How will I validate research findings against requirements scope?

**Research Execution Process:**

**Conducting targeted research on identified areas:**

**Technology Evaluation and Recommendations:**

- Research technology options that address specific functional requirements from requirements.md
- Evaluate frameworks and tools that support identified non-functional requirements
- Assess technology compatibility with project constraints and steering guidance
- Validate technology choices against requirements scope preventing speculative adoption

**Architecture Pattern Analysis:**

- Research architecture patterns suitable for identified functional requirements
- Analyze scalability patterns for performance requirements from requirements.md
- Investigate integration patterns for external system requirements
- Evaluate security architecture patterns for security requirements identified

**Integration Approach Assessment:**

- Research integration methods for external system requirements from requirements.md
- Analyze API design patterns supporting functional requirements
- Investigate data exchange approaches for identified integration needs
- Validate integration complexity against requirements scope and project constraints

**Security and Performance Considerations:**

- Research security standards applicable to security requirements from requirements.md
- Investigate performance optimization techniques for performance requirements
- Analyze compliance requirements and implementation approaches
- Validate security and performance measures against actual requirements needs

**Research Findings Synthesis:**

**Key Research Outcomes:**

- **Technology Recommendations**: [Specific technologies with requirements justification]
- **Architecture Patterns**: [Suitable patterns with requirements mapping]
- **Integration Approaches**: [Methods with external system compatibility]
- **Security Strategies**: [Approaches for requirements compliance]
- **Performance Approaches**: [Optimization techniques for requirements satisfaction]

**Research Validation Against Requirements:**

- All recommendations trace directly to approved requirements from requirements.md
- No speculative technology adoption beyond requirements scope
- Technology complexity appropriate for requirements scale and project constraints
- Research findings align with steering document guidance and project standards

**Research Complete - Ready for Design Planning Phase**

# Design Planning and Scope Alignment

## High-Level Design Approach Development

**Before presenting design approach, think through architectural trade-offs:**

**Architectural Decision Framework Application:**
For each major architectural decision:

1. What requirements drive this decision and what constraints must be considered?
2. What are the available options and their trade-offs in complexity, maintainability, and requirements alignment?
3. Which option best serves approved requirements while avoiding over-engineering?
4. How does this decision integrate with other architectural choices and research findings?

**Research-Informed Design Approach:**

Based on research findings and approved requirements analysis:

**Proposed System Architecture:**

- **Core Components**: [2-3 main system components derived from functional requirements]
- **Technology Stack**: [Primary technologies based on research recommendations and requirements]
- **Integration Pattern**: [System connection approach for external dependencies from requirements]
- **Data Architecture**: [High-level data flow pattern supporting requirements effectively]

**Critical Architectural Decisions:**

- **Architecture Pattern**: [Recommended pattern with requirements justification - microservices, monolith, serverless, etc.]
- **Database Strategy**: [Data storage approach based on requirements analysis and research]
- **API Design Approach**: [Interface strategy for communication requirements from requirements.md]
- **Security Architecture**: [High-level security approach for security requirements compliance]
- **Performance Strategy**: [System optimization approach based on performance requirements]

## Scope Boundary Confirmation

**Design Scope Boundaries (Reasoning-Based Discipline):**

**Features Being Designed (Approved Requirements Coverage):**

- [Component 1]: Addresses specific functional requirements from requirements.md
- [Component 2]: Supports non-functional requirements identified in approved scope
- [Integration Element]: Enables external system requirements from requirements.md

**Features NOT Being Designed (Cross-Stage Boundary Inheritance):**

**Requirements Scope Reference:**
**From requirements.md out-of-scope section:**
[Carry forward exact items with original reasoning from requirements approval]

- [Feature X] - Excluded because: [original reasoning from requirements approval]
- [Feature Y] - Excluded because: [original reasoning from requirements approval]

**Implementation guidance**: These exclusions represent conscious decisions made during requirements approval. Honoring them maintains project coherence and user agreement.

**Design Boundaries (Reasoning-Based):**

- [Advanced Architecture X] - Not needed for current requirements complexity, would create maintenance burden
- [Complex Pattern Y] - Over-engineering for approved requirements, simple approach adequate
- [Enterprise Feature Z] - Not justified by requirements scope, would add unnecessary complexity

**Why These Boundaries Matter:**

**Resource Focus**: Designing only approved components allows concentrated effort on architecture quality and depth rather than spreading across unapproved features.

**System Coherence**: Approved requirements create coherent vision. Design should honor this careful planning rather than fragment it with speculative architecture.

**Maintenance Sustainability**: Each additional design element creates permanent maintenance overhead - updates, integration complexity, testing that compounds over time.

**Technical Debt Prevention**: Unplanned design elements typically lack proper requirements analysis, creating long-term architectural challenges.

**Architecture Trade-offs Identified:**

- [Trade-off 1]: [Decision reasoning based on requirements priorities]
- [Trade-off 2]: [Choice rationale from research findings and requirements constraints]

**Requirements Coverage Validation:**

- **Functional Requirements**: [Primary components addressing these from requirements.md]
- **Non-Functional Requirements**: [Architecture elements supporting these needs]
- **Integration Requirements**: [Design approach for external system connections]
- **Security Requirements**: [Security architecture for requirements compliance]

**Does this research-informed, scope-disciplined design approach align with your vision?**

**Please review:**

- Are the core components appropriate for your approved requirements?
- Do the technology choices match your research preferences and actual needs?
- Is the architecture pattern suitable for your requirements complexity and scale?
- Are the scope boundaries correctly identified as beyond approved requirements?
- Any design directions you'd like me to adjust before detailed generation?

**Your options:**

- **Scope looks right, proceed**: Say "proceed" or "generate design document"
- **Adjust approach**: Tell me what you'd like changed in the high-level design
- **Adjust scope boundaries**: Tell me what should be included or excluded from design scope
- **Add research constraints**: Share additional technical constraints or preferences

**What's your feedback on this scope-disciplined, research-informed design approach?**

**Wait for user alignment before proceeding to design document generation**

# Design Document Generation

## Pre-Generation Quality Planning

**After receiving user approval, systematically plan the generation approach:**

**Before generating design document, think through:**

1. How will I integrate all research findings into technology choices and architecture patterns?
2. How will I ensure complete requirements coverage in appropriate design sections?
3. How will I maintain scope discipline throughout generation?
4. How will I preserve cross-stage boundary reasoning from requirements approval?

**Generation Strategy:**

- Apply approved high-level design direction with research integration
- Address ALL approved requirements through appropriate design sections
- Follow exact 6-section Kiro template structure with comprehensive specifications
- Integrate steering document guidance throughout design decisions
- Maintain reasoning-based scope discipline with clear boundary documentation

## Comprehensive Design Document Generation

**Creating detailed design document incorporating:**

- Approved high-level design approach with research integration
- All requirements coverage through systematic mapping to design components
- Technology choices justified by research findings and requirements analysis
- Architecture patterns supported by research and requirements traceability
- Complete steering document guidance integration (product, technical, structural)
- Cross-stage scope boundary inheritance with reasoning preservation

**Generate design document at .kiro/specs/[feature-name]/design.md using exact template specification:**

<kiro_design_document_template>

```markdown
# [feature-name] Design Document

## Overview

[SPECIFICATION: This section must provide a clear system architecture summary incorporating research findings and addressing only approved requirements. Include high-level design approach and key architectural decisions with reasoning from research analysis.]

## Architecture

[SPECIFICATION: Define detailed system architecture with component relationships based on approved requirements analysis. Include technology choices justified by research findings and integration patterns. Document architectural decisions with research rationale and requirements traceability.]

## Components and Interfaces

[SPECIFICATION: Provide comprehensive component specifications and interface definitions addressing all approved requirements without over-engineering. Include input/output specifications, interaction patterns, and component responsibilities. Map each component to specific requirements from requirements.md.]

## Data Models

[SPECIFICATION: Define complete data structures, schemas, and relationships supporting all functional requirements from requirements.md. Include data flow and storage considerations based on research findings. Document data validation, transformation, and persistence approaches.]

## Error Handling

[SPECIFICATION: Document comprehensive error conditions, recovery mechanisms, and failure modes for all requirements - realistic scenarios only. Include error propagation and user experience considerations. Define error logging, monitoring, and alerting strategies.]

## Testing Strategy

[SPECIFICATION: Establish testing approaches, test types, and validation methods covering all design components - proportional to complexity. Include integration testing and quality assurance approaches. Define test automation, performance testing, and security validation strategies.]

## Design Scope Boundaries (Reasoning-Based)

### Requirements Scope Reference

**From requirements.md out-of-scope section:**
[Carry forward exact items with original reasoning from requirements approval]

- [Feature X] - Excluded because: [original reasoning from requirements approval]
- [Feature Y] - Excluded because: [original reasoning from requirements approval]

**Implementation guidance**: These exclusions represent conscious decisions made during requirements approval. Honoring them maintains project coherence and user agreement.

### Design Scope Boundaries

**Features NOT Being Designed:**

- [Feature 1] - Not in approved requirements, would create maintenance burden without validated need
- [Feature 2] - Future consideration beyond current requirements scope, lacks proper planning foundation
- [Advanced capability] - Over-engineering for current requirements, would add complexity without proportional benefit

**Technical Complexity NOT Included:**

- [Complex pattern X] - Simple approach adequate for approved requirements scale and complexity
- [Enterprise feature Y] - Not justified by current requirements, would require extensive additional infrastructure
- [Optimization Z] - Premature optimization avoided per requirements analysis, monitor and implement when validated need emerges

**Testing Elements NOT Designed:**

- [Extensive testing type] - Maintenance burden not justified by requirements risk profile
- [Complex test infrastructure] - Simple testing adequate for requirements scope and team capabilities
- [Speculative test scenarios] - Focus on actual requirements validation only, avoid theoretical edge cases

### Why These Boundaries Matter

**Resource Focus**: Designing only approved components allows concentrated effort on architecture quality and depth rather than spreading across unapproved features that lack proper requirements foundation.

**Maintenance Sustainability**: Each additional design element creates permanent maintenance overhead - updates, integration complexity, testing, documentation that compounds over time and diverts resources from core functionality.

**System Coherence**: Approved requirements create a coherent vision developed through careful analysis. Design should honor this planning rather than fragment it with speculative architectural additions.

**Technical Debt Prevention**: Unplanned design elements typically lack proper requirements analysis, creating long-term architectural challenges, integration difficulties, and maintenance complexity.

### Future Considerations (Documented but NOT Designed)

- [Future enhancement 1] - Could be added later if requirements expand through proper analysis and validation
- [Scalability consideration] - Monitor usage patterns and performance metrics, implement when requirements indicate validated need
- [Advanced feature] - Evaluate business case and technical fit before adding to future development cycles

### Design Philosophy

**Requirements-driven architecture**: Design serves approved requirements only, avoiding speculative additions that create maintenance burden without validated need. Every architectural decision traces to specific approved requirements with clear justification and research support.
```

</kiro_design_document_template>

**Execute comprehensive design content generation based on all gathered context, research findings, and approved requirements with complete scope discipline maintenance.**

# Quality Validation Framework

## Comprehensive Design Quality Assessment

**After generating complete design document, execute systematic quality validation:**

**Before presenting results, systematically validate design quality:**

1. Do all design sections address approved requirements comprehensively?
2. Are research findings meaningfully integrated throughout technology and architecture decisions?
3. Is design complexity appropriate for requirements scope without over-engineering?
4. Are cross-stage scope boundaries properly inherited and documented with reasoning?

### Document Structure Validation

- Verify .kiro/specs/[feature-name]/design.md created successfully with complete content
- Confirm all 6 required sections present: Overview, Architecture, Components and Interfaces, Data Models, Error Handling, Testing Strategy
- Check document follows exact Kiro design template structure with proper formatting
- Validate sections properly organized according to Kiro standards with clear information hierarchy
- Confirm out-of-scope section documents design boundaries clearly with reasoning-based explanations

### Requirements Coverage Validation

- Verify all requirements from requirements.md addressed through appropriate design components and sections
- Check each requirement category has corresponding design elements with clear traceability
- Confirm no approved requirements left unaddressed in architecture specifications
- Validate design decisions traceable to specific requirements from requirements.md with clear justification
- Check functional requirements mapped to specific components with comprehensive specifications
- Verify non-functional requirements addressed through architecture patterns and design decisions

### Research Integration Validation

- Confirm research findings incorporated meaningfully into design decisions and technology choices
- Verify technology choices justified by research analysis and requirements alignment
- Check architecture patterns supported by research findings and best practices
- Validate integration approaches based on research recommendations and requirements needs
- Confirm security and performance strategies derived from research findings and requirements analysis

### Architecture Quality Assessment

- Verify component relationships clearly defined and logical for requirements fulfillment
- Check interface specifications complete with comprehensive input/output definitions
- Confirm data flow documented systematically between all components supporting requirements
- Validate system scalability and maintainability addressed appropriately for requirements scope
- Verify error handling comprehensive for requirements failure modes without over-engineering
- Check testing strategy covers all design components proportionally to complexity and risk

### Design Completeness Validation

- Confirm all functional requirements addressed by specific components with clear specifications
- Verify all non-functional requirements addressed through architecture patterns and design decisions
- Check technical constraints from requirements incorporated systematically into design architecture
- Validate integration requirements fully specified in component interfaces and system architecture
- Confirm security requirements addressed comprehensively in architecture patterns and component design
- Verify performance requirements addressed through design decisions with measurable approaches

### Design Scope Discipline Validation

- Confirm all design elements trace to specific approved requirements with clear justification
- Verify no speculative or "nice to have" design elements added beyond approved requirements scope
- Check design complexity appropriate for requirements scope without theoretical over-engineering
- Validate out-of-scope section documents architectural boundaries clearly with sound reasoning
- Confirm technology choices match requirements complexity, not theoretical ideals or speculative needs
- Verify testing architecture proportional to requirements risk profile and team capabilities

**Quality Validation Results:**

**Kiro Stage 2 Quality Assessment:**

- **Structure Validation**: Perfect compliance with Kiro 6-section design template and formatting standards
- **Requirements Coverage**: All approved requirements addressed systematically in appropriate architecture sections
- **Research Integration**: Technology choices and architecture patterns informed comprehensively by research findings
- **Architecture Quality**: Component relationships logical and requirements-driven with clear specifications
- **Interface Completeness**: All component interfaces specified comprehensively for requirements support
- **Design Completeness**: All requirement categories addressed systematically in appropriate design sections
- **Scope Discipline**: Design focused on approved requirements with architectural boundaries documented clearly

**Overall Quality Score**: [Calculated score based on comprehensive validation results with transparent methodology]

# Design Review and Iteration Process

## Design Document Completion Presentation

**Present completed design document with comprehensive assessment:**

**Generated Document Summary:**

- **Location**: .kiro/specs/[feature-name]/design.md
- **Quality Assessment**: [Comprehensive scoring across all validation dimensions with methodology]
- **Research Integration**: [Summary of how research findings influenced design decisions]
- **Requirements Coverage**: [Analysis of how all approved requirements are addressed]
- **Scope Boundaries**: [Summary of maintained scope discipline with reasoning]

**Key Design Highlights:**

- **Architecture Approach**: [High-level architecture pattern with requirements justification]
- **Technology Decisions**: [Key technology choices with research rationale]
- **Component Design**: [Major components with requirements mapping]
- **Integration Strategy**: [External system connections with requirements alignment]

## User Review Facilitation

**Guide user through systematic design review process:**

**Key Review Considerations:**

- Does the architecture support all your approved requirements effectively without over-engineering?
- Are the component relationships and interfaces clear and logical for your system needs?
- Do the data models support all functional requirements adequately with proper specifications?
- Is the error handling strategy comprehensive for your requirements without excessive complexity?
- Does the testing strategy cover all design components proportionally to risk and complexity?
- Are integration points properly specified for your external system requirements?
- Are the technology choices appropriate for your requirements complexity and organizational constraints?
- Are the scope boundaries correctly identified and documented with sound reasoning?

**User Review Options:**

- **Request Changes**: Tell me what needs to be modified, added, or refined in the design architecture
- **Architecture Adjustments**: Point out components needing redesign, simplification, or enhancement
- **Technology Modifications**: Adjust technology choices or integration approaches
- **Scope Adjustments**: Adjust what should be included or excluded from design scope with reasoning
- **Ready to Approve**: If satisfied with design quality and completeness, say "looks good", "approved", or "yes"

**What's your feedback on the design document?**

## Iteration and Refinement Process

**If user requests changes, execute systematic refinement:**

**Before implementing modifications, carefully analyze specific feedback:**

1. What specific design changes are being requested and why?
2. How do requested modifications align with approved requirements and research findings?
3. What changes maintain Kiro compliance while addressing user architectural needs?
4. How will modifications affect scope boundaries and cross-stage traceability?

**Refinement Execution Process:**

1. **Analyze specific feedback** systematically to understand precise architectural modifications needed
2. **Update design.md** with requested changes while maintaining complete Kiro compliance and scope discipline
3. **Re-execute quality validation** to ensure all standards maintained including research integration
4. **Present updated version** for another review cycle with architectural highlights and improvement summary
5. **Continue iteration cycles until explicit user approval** received with documented satisfaction

# Final Approval and State Management

## Design Document Approval Process

**Upon receiving explicit user approval:**

**Update project state systematically:**

- Mark design stage as generated: true and approved: true in spec.yaml
- Update project timestamp to reflect Stage 2 completion
- Prepare project for Stage 3: Implementation Planning transition
- Document design approval for workflow traceability and quality standards

**State Management Updates:**

```yaml
# Update .kiro/specs/[feature-name]/spec.yaml
approvals:
  design:
    generated: true
    approved: true
updated_at: "[current ISO timestamp]"
```

**Completion Validation:**

- Design document finalized with complete user approval and quality validation
- Project state accurately reflects Stage 2 completion with approval confirmation
- All Kiro quality standards met with documented validation results
- Next stage prerequisites established with complete design foundation
- Cross-stage traceability maintained for implementation planning stage

## Workflow Transition Guidance

**Provide clear guidance for next steps in Kiro workflow progression:**

**Stage 2 Completion Summary:**

- **Design Document**: Complete and approved following all Kiro standards with research integration
- **Quality Validation**: Comprehensive assessment passed with transparent methodology and scoring
- **Requirements Coverage**: All approved requirements addressed systematically in design architecture
- **Research Integration**: Technology choices and architecture patterns informed by targeted research
- **Scope Boundaries**: Clearly established with reasoning-based discipline maintained throughout
- **Workflow Foundation**: Solid design base established for implementation planning and task breakdown

**Next Stage Preparation:**

- **Stage 3 Ready**: Implementation planning can proceed with approved design foundation
- **Context Available**: Complete design will inform task breakdown and implementation sequencing
- **Scope Inheritance**: Implementation stage will carry forward established scope boundaries with reasoning
- **Quality Standards**: Design approval demonstrates validation approach for subsequent workflow stages

**Next Steps:**
Ready to proceed with **Stage 3: Implementation Planning**? Run:

```
/kiro:4-implementation-planning [feature-name]
```

**Kiro Stage 2 Complete - Design Document Creation Successful with Research Integration and Quality Validation!**
