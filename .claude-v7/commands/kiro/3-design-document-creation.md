---
description: "Kiro Stage 2: Create comprehensive design document with research integration and scope discipline"
argument-hint: "feature-name (kebab-case)"
---

# Kiro Design Document Creation (Stage 2)

## 1. Argument Validation & Feature Selection

Let me check for available features and validate your input.

!ls .kiro/specs/ 2>/dev/null | grep -v "^total" | grep -E "^[a-zA-Z0-9-]+$" || echo "No features found in .kiro/specs/"

**Checking feature argument...**

If you didn't provide a feature name or the feature doesn't exist:

### Available Features in .kiro/specs/

[The list above shows your available features]

**Please specify which feature you'd like to work on for design document creation:**

- Type the feature name exactly as shown (kebab-case format)
- Feature must have approved requirements from Stage 1
- Requirements document must exist at `.kiro/specs/{feature-name}/requirements.md`

**Waiting for your feature selection...**

[Wait for user to provide valid feature name before continuing]

---

Once you provide a valid feature name, I'll continue with that feature.

## 2. State & Context Validation + Prerequisites Check

Loading project context for feature: **${feature-name}**

@.kiro/specs/${feature-name}/spec.yaml
@.kiro/specs/${feature-name}/requirements.md
@.kiro/steering/product.md
@.kiro/steering/tech.md  
@.kiro/steering/structure.md

**Validating prerequisites:**

!test -f ".kiro/specs/${feature-name}/spec.yaml" && echo "Found" || echo "Missing"
!test -f ".kiro/specs/${feature-name}/requirements.md" && echo "Found" || echo "Missing"

**Critical Stage 2 Prerequisites:**

- Feature initialized: ${feature-name}
- Requirements stage: **MUST be approved** (checking spec.yaml approval status)
- requirements.md exists and accessible for design context
- Steering context loaded for design guidance

**Prerequisites Status:**

- Feature: ${feature-name} ✓
- Stage 1 (Requirements): [Checking approval status from spec.yaml]
- Context Documents: [Verifying accessibility]

If requirements are not approved, you must complete Stage 1 first:

```
/kiro:2-requirements-clarification ${feature-name}
```

**Ready to proceed with design document creation.**

## 3. Research Integration Phase

**Feature Context Loaded:** ${feature-name}  
**Current Status:** [Reading from spec.yaml and requirements.md for design context]

**Research Integration Phase (Kiro Stage 2)**

Based on your approved requirements, I need to conduct research to inform design decisions.

**Research Areas Identified:**
[Analyzing requirements.md to identify research needs]

- Technology stack evaluation for [specific requirements identified]
- Integration patterns for [external system requirements from requirements.md]  
- Security standards for [security requirements from requirements.md]
- Performance optimization approaches for [performance requirements]
- Industry best practices for [domain-specific requirements]

**If you have research preferences or constraints, share them now:**

- Preferred technologies, frameworks, or tools you want me to consider
- Integration requirements or existing system constraints I should know
- Performance, security, or compliance standards you must follow
- Architecture preferences or patterns you want to follow/avoid
- Technology restrictions or organizational standards
- Any other technical guidance or constraints for the design

**You can share as much or as little as you'd like in one or multiple messages.**

**When ready for research phase, say 'proceed with research' or 'start research'**

[Wait for user research preferences or proceed signal]

---

## Research Execution & Analysis

**Conducting Research Phase...**

Analyzing requirements and conducting targeted research on identified areas:

[Conduct actual research based on requirements analysis and user preferences]

- Technology evaluation and recommendations based on requirements
- Architecture pattern analysis for identified functional needs
- Integration approach assessment for external system requirements
- Security and performance considerations from requirements
- Best practice identification for domain-specific needs

**Research Findings Summary:**
[Key findings that will inform design decisions]

- **Technology Recommendations**: [Based on research and requirements analysis]  
- **Architecture Patterns**: [Suitable patterns for identified requirements]
- **Integration Approaches**: [Methods for external system integration]
- **Security Considerations**: [Security patterns for requirements compliance]
- **Performance Strategies**: [Approaches for performance requirements]

**Research Complete - Ready for Design Planning**

## 4. Design Planning & Alignment

Based on the research findings and approved requirements, here's my high-level design approach:

**Proposed System Architecture:**

- **Core Components**: [2-3 main system components identified from requirements]
- **Key Technologies**: [Primary tech stack recommendations from research]
- **Integration Pattern**: [How system connects with external dependencies]
- **Data Flow**: [High-level data movement pattern supporting requirements]

**Critical Design Decisions:**

- **Architecture Pattern**: [Recommended pattern - microservices, monolith, serverless, etc.]
- **Database Strategy**: [Data storage approach based on requirements analysis]
- **API Design**: [Interface approach for external communication needs]
- **Security Approach**: [High-level security strategy for requirements compliance]
- **Scalability Strategy**: [How system will handle growth based on requirements]

**🚫 EXPLICITLY OUT OF SCOPE** (Design Scope Discipline):

**Features NOT Being Designed:**

- [Feature X] - Not in approved requirements, would add unnecessary complexity
- [Feature Y] - Future enhancement beyond current requirements scope
- [Advanced Feature Z] - Over-engineering, not justified by current requirements

**Technical Elements NOT Included:**

- [Complex Infrastructure X] - Current requirements don't justify this complexity
- [Advanced Pattern Y] - Simple approach adequate for current requirements scale
- [Enterprise Feature Z] - Not needed for approved requirements scope

**Architecture Boundaries:**

- **Simple, maintainable patterns** preferred over complex abstractions
- **Avoid premature optimization** - design for approved requirements only
- **No speculative architecture** - build only what requirements specify

**Testing & Validation Scope:**

- **Will Design For**: Component testing, integration validation for key workflows
- **Will NOT Design For**: Extensive performance testing, load testing, chaos engineering
- **Rationale**: Testing architecture matches requirements complexity and risk profile

**Key Trade-offs Identified:**

- [Major architectural trade-off 1 and reasoning based on requirements]
- [Major architectural trade-off 2 and reasoning from research findings]

**Requirements Mapping Preview:**

- **Functional Requirements** → [Primary components handling these from requirements.md]
- **Performance Requirements** → [Architecture elements addressing these needs]
- **Security Requirements** → [Security components and patterns for compliance]
- **Integration Requirements** → [Integration architecture approach for external systems]

**Does this scope-disciplined design approach align with your vision?**

**Please review:**

- Are the core components appropriate for your requirements (not over-engineered)?
- Do the technology choices match your actual needs (not over-complex)?
- Is the architecture pattern suitable for your requirements scale/complexity?
- Are the out-of-scope items correctly identified as beyond requirements?
- Is the testing scope reasonable for your maintenance capabilities?
- Any design directions you'd like me to adjust before detailed generation?

**Your options:**

- **Scope looks right, proceed**: Say "proceed" or "generate design document"
- **Adjust approach**: Tell me what you'd like changed in the high-level design
- **Adjust scope boundaries**: Tell me what should be in/out of design scope
- **Add constraints**: Share any additional technical constraints or preferences

**What's your feedback on this scope-disciplined design approach?**

[Wait for user alignment before proceeding to full design generation]

## 5. Design Document Generation (Kiro Stage 2)

**Generating comprehensive design document based on approved approach...**

Now I'll create detailed design document incorporating:

- Your approved high-level design direction from above
- All research findings and technology choices
- Complete requirements coverage from requirements.md
- Steering document guidance (product, tech, structure)
- Exact Kiro behavioral constraints and formatting standards

**CRITICAL KIRO STAGE 2 CONSTRAINTS:**

- Address ALL approved requirements in design architecture
- Include all 6 mandatory sections (Overview, Architecture, Components, Data Models, Error Handling, Testing Strategy)
- Integrate research findings into design decisions
- Follow exact Kiro design document template structure
- Maintain scope discipline - design only for approved requirements

**Generating design.md...**

Creating comprehensive design document at: `.kiro/specs/${feature-name}/design.md`

**KIRO DESIGN DOCUMENT TEMPLATE:**

```markdown
# ${feature-name} Design Document

## Overview
[System architecture summary and design approach incorporating research findings and approved requirements only]

## Architecture  
[High-level system architecture and component relationships based on approved requirements analysis]

## Components and Interfaces
[Detailed component specifications and interface definitions addressing all approved requirements without over-engineering]

## Data Models
[Data structures, schemas, and relationships supporting all functional requirements from requirements.md]

## Error Handling
[Error conditions, recovery mechanisms, and failure modes for all requirements - realistic scenarios only]

## Testing Strategy
[Testing approaches, test types, and validation methods covering all design components - proportional to complexity]

## Design Scope Boundaries (Reasoning-Based)

### Requirements Scope Reference
**From requirements.md out-of-scope section:**
[Carry forward exact items with original reasoning from requirements approval]
- [Feature X] - Excluded because: [original reasoning from requirements approval]
- [Feature Y] - Excluded because: [original reasoning from requirements approval]

**Implementation guidance**: These exclusions represent conscious decisions made during requirements approval. Honoring them maintains project coherence and user agreement.

### Design Scope Boundaries
**Features NOT Being Designed:**
- [Feature 1] - Not in approved requirements, would create maintenance burden
- [Feature 2] - Future consideration beyond current requirements scope  
- [Advanced capability] - Over-engineering for current requirements

**Technical Complexity NOT Included:**
- [Complex pattern X] - Simple approach adequate for approved requirements
- [Enterprise feature Y] - Not justified by current requirements complexity
- [Optimization Z] - Premature optimization avoided per requirements analysis

**Testing Elements NOT Designed:**
- [Extensive testing type] - Maintenance burden not justified by requirements
- [Complex test infrastructure] - Simple testing adequate for requirements scope
- [Speculative test scenarios] - Focus on actual requirements validation only

### Why These Boundaries Matter

**Resource Focus**: Designing only approved components allows concentrated effort on architecture quality and depth rather than spreading across unapproved features.

**Maintenance Sustainability**: Each additional design element creates permanent maintenance overhead - updates, integration complexity, testing that compounds over time.

**System Coherence**: Approved requirements create a coherent vision. Design should honor this careful planning rather than fragment it with speculative architecture.

**Technical Debt Prevention**: Unplanned design elements typically lack proper requirements analysis, creating long-term architectural challenges.

### Future Considerations (Documented but NOT Designed)
- [Future enhancement 1] - Could be added later if requirements expand
- [Scalability consideration] - Monitor and implement when requirements indicate need
- [Advanced feature] - Evaluate need based on requirements evolution

### Design Philosophy
**Requirements-driven architecture**: Design serves approved requirements only, avoiding speculative additions that create maintenance burden without validated need.
```

[Generate actual comprehensive design content based on all gathered context, research, and approved requirements]

## 6. Quality Validation Framework

**Executing Kiro Stage 2 quality validation checkpoints...**

### Document Structure Validation

- Check: `.kiro/specs/${feature-name}/design.md` created successfully
- Check: All 6 required sections present (Overview, Architecture, Components, Data Models, Error Handling, Testing Strategy)
- Check: Document follows exact Kiro design template structure
- Check: Sections properly organized and formatted according to Kiro standards
- Check: Out-of-scope section documents design boundaries clearly

### Requirements Coverage Validation  

- Check: All requirements from requirements.md addressed in design components
- Check: Each requirement category has corresponding design elements
- Check: No approved requirements left unaddressed in architecture
- Check: Design decisions traceable to specific requirements from requirements.md
- Check: Functional requirements mapped to specific components
- Check: Non-functional requirements addressed in architecture patterns

### Research Integration Validation

- Check: Research findings incorporated into design decisions and technology choices
- Check: Technology choices justified by research analysis and requirements
- Check: Architecture patterns supported by research and best practices
- Check: Integration approaches validated through research findings
- Check: Security and performance strategies based on research recommendations

### Architecture Quality Assessment

- Check: Component relationships clearly defined and logical for requirements
- Check: Interface specifications complete with input/output definitions
- Check: Data flow documented between all components supporting requirements
- Check: System scalability and maintainability addressed appropriately
- Check: Error handling comprehensive for requirements failure modes
- Check: Testing strategy covers all design components proportionally

### Design Completeness Validation

- Check: All functional requirements addressed by specific components
- Check: All non-functional requirements addressed in architecture
- Check: Technical constraints from requirements incorporated into design
- Check: Integration requirements fully specified in component interfaces
- Check: Security requirements addressed in architecture patterns
- Check: Performance requirements addressed in design decisions

### Design Scope Discipline Validation

- Check: All design elements trace to specific approved requirements
- Check: No speculative or "nice to have" design elements added beyond requirements
- Check: Design complexity appropriate for requirements scope (not over-engineered)
- Check: Out-of-scope section documents architectural boundaries clearly
- Check: Technology choices match requirements complexity, not theoretical ideals
- Check: Testing architecture proportional to requirements risk profile

**Quality Validation Results:**

**Kiro Stage 2 Quality Assessment:**

- **Structure Validation**: Perfect compliance with Kiro 6-section design template
- **Requirements Coverage**: All approved requirements addressed in architecture
- **Research Integration**: Technology choices and patterns informed by research findings  
- **Architecture Quality**: Component relationships logical and requirements-driven
- **Interface Completeness**: All component interfaces specified for requirements support
- **Design Completeness**: All requirement categories addressed in appropriate design sections
- **Scope Discipline**: Design focused on approved requirements, architectural boundaries documented

**Overall Quality Score: [Calculated based on validation results]**

## 7. Design Review & Revision Cycle

## Design Document Complete

I've generated a comprehensive design document following all Kiro Stage 2 standards:

- **Requirements Integration**: All approved requirements addressed in architecture components
- **Research Application**: Technology and architecture choices informed by targeted research
- **6-Section Structure**: Complete Kiro template with all mandatory sections properly formatted
- **Steering Guidance**: Product, technical, and structural guidance applied throughout design
- **Scope Discipline**: Design boundaries documented, over-engineering avoided

**Generated Document:**
**Location**: `.kiro/specs/${feature-name}/design.md`
**Quality Score**: [Score] (meeting all Kiro validation standards and scope discipline)

[Display key design highlights and architectural decisions]

**Please review your design document.**

**Consider:**

- Does the architecture support all your approved requirements effectively?
- Are the component relationships clear and logical for your needs?
- Do the data models support all functional requirements adequately?
- Is the error handling strategy comprehensive for your requirements?
- Does the testing strategy cover all components proportionally?
- Are integration points properly specified for your external systems?
- Are the technology choices appropriate for your requirements complexity?
- Are the scope boundaries correctly identified and documented?

**Your options:**

- **Request Changes**: Tell me what needs to be modified, added, or refined
- **Architecture Adjustments**: Point out components needing redesign or simplification
- **Scope Adjustments**: Adjust what should be in/out of design scope
- **Ready to Approve**: If satisfied, say "looks good", "approved", or "yes"

**What's your feedback?**

[Handle user feedback and revision cycle]

---

### Revision Cycle (if changes requested)

[If user requests changes:]

1. **Analyze specific feedback** and identify areas for architectural modification
2. **Update design.md** with requested changes while maintaining Kiro compliance and scope discipline
3. **Re-run quality validation** to ensure all standards maintained including scope boundaries
4. **Present updated version** for another review cycle with architectural highlights
5. **Continue until explicit approval received**

## 8. Final Approval & State Management

### Design Approved

Thank you for the approval! The design document is now finalized and ready for implementation planning.

**Updating project state...**

```yaml
# Updating .kiro/specs/${feature-name}/spec.yaml
approvals:
  design:
    generated: true
    approved: true
updated_at: "[current timestamp]"
```

**State Updated Successfully:**

- Design stage marked as completed and approved
- Project ready for Stage 3: Implementation Planning
- Use `/kiro:4-implementation-planning ${feature-name}` to proceed

**Final Deliverables:**

- **Design Document**: `.kiro/specs/${feature-name}/design.md` (Kiro-compliant with scope discipline)
- **Updated Project State**: `.kiro/specs/${feature-name}/spec.yaml` (design approved)
- **Quality Validation**: All Kiro Stage 2 standards met including scope boundaries
- **Research Integration**: Technology decisions documented and justified

### Next Steps

Ready to move to **Stage 3: Implementation Planning**? Run:

```
/kiro:4-implementation-planning ${feature-name}
```

**Kiro Stage 2 Complete - Design Document Creation Successful!**
