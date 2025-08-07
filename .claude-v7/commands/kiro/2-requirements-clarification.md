---
description: "Kiro Stage 1: Generate comprehensive requirements using EARS format with quality validation"
argument-hint: "feature-name (kebab-case)"
---

# Kiro Requirements Clarification (Stage 1)

## 1. Argument Validation & Feature Selection

Let me check for available features and validate your input.

!ls .kiro/specs/ 2>/dev/null | grep -v "^total" | grep -E "^[a-zA-Z0-9-]+$" || echo "No features found in .kiro/specs/"

**Checking feature argument...**

If you didn't provide a feature name or the feature doesn't exist:

### Available Features in .kiro/specs/

[The list above shows your available features]

**Please specify which feature you'd like to work on for requirements clarification:**

- Type the feature name exactly as shown (kebab-case format)
- If starting a new feature, use `/kiro:1-init feature-name` first
- Feature must already be initialized with spec.yaml

**Waiting for your feature selection...**

[Wait for user to provide valid feature name before continuing]

---

Once you provide a valid feature name, I'll continue with that feature.

## 2. State & Context Validation

Loading project context for feature: **${feature-name}**

@.kiro/specs/${feature-name}/spec.yaml
@.kiro/steering/product.md
@.kiro/steering/tech.md  
@.kiro/steering/structure.md

**Validating prerequisites:**

- Feature initialized: ${feature-name}
- spec.yaml exists with proper structure
- Steering context loaded for decision guidance
- Ready to proceed with requirements clarification

## 3. Context Gathering

**Feature Context Loaded:** ${feature-name}  
**Current Status:** [Reading from spec.yaml - feature_description and current approval states]

I'm ready to generate comprehensive requirements for this feature following all Kiro standards.

**If you have any context to share, please provide it now:**

- Initial ideas, user stories, or scenarios you're envisioning
- Technical constraints or integration requirements you already know
- Performance, security, or usability considerations
- Examples or references you'd like me to consider
- Any other relevant context or requirements you have in mind

**You can share as much or as little as you'd like in one or multiple messages.**

**When you're ready for me to proceed with generating the requirements draft, just say 'proceed' or 'generate requirements'.**

[Wait for user context inputs until they say to proceed]

---

## Requirements Scope Planning

Based on your context, here's what I understand you want built:

**Core Features to Include:**
- [Feature 1] - From your context about [specific user input]
- [Feature 2] - Necessary for [specific scenario you mentioned]
- [Essential capability X] - Required for [your stated need]

**🚫 Will NOT Include (Staying Focused):**
- [Common feature Y] - Not mentioned in your context, would add complexity
- [Advanced capability Z] - Beyond current scope, could be future enhancement  
- [Speculative requirement] - No indication this is needed for your use case

**Boundary Questions:**
- Should I include [borderline feature]? (Related to your context but not explicit)
- Any scope boundaries you want me to respect?
- Features you specifically want me to avoid adding?

**Scope looks right? Say 'proceed' to generate requirements within these boundaries.**

[Wait for scope confirmation before generation]

## 4. Requirements Generation (Kiro Stage 1)

**Generating comprehensive requirements incorporating all context provided...**

Now I'll create complete requirements based on ALL available context:

- Your provided context and ideas from above
- Feature description from spec.yaml
- Steering document guidance (product, tech, structure)
- Industry best practices and comprehensive coverage
- Exact Kiro behavioral constraints and formatting standards

**CRITICAL KIRO STAGE 1 CONSTRAINTS:**

- Generate comprehensive requirements based on all available context
- Use EARS format for all acceptance criteria
- Include exact user story template structure  
- Ensure complete coverage: functional, non-functional, technical constraints, edge cases
- Follow exact Kiro document template structure

**Generating requirements.md...**

Creating comprehensive requirements document at: `.kiro/specs/${feature-name}/requirements.md`

**KIRO REQUIREMENTS TEMPLATE:**

```markdown
# ${feature-name} Requirements

## Introduction
[Clear feature summary incorporating user context and steering guidance]

## Requirements

### 1. Core Functionality Requirements
**User Story**: As a [role], I want [feature], so that [benefit]

**Acceptance Criteria**:
1. The system shall [specific action/capability]
2. When [condition], the system shall [response/behavior]  
3. The system should [optional/preferred behavior]
4. While [state], when [trigger], the system shall [complex conditional behavior]

### 2. User Experience Requirements  
**User Story**: As a [user type], I want [interaction capability], so that [user value]

**Acceptance Criteria**:
1. The system shall [UX requirement]
2. When [user action], the system shall [response requirement]
3. The system should [usability enhancement]

### 3. Technical Requirements
**User Story**: As a [system/developer], I want [technical capability], so that [technical benefit]

**Acceptance Criteria**:
1. The system shall [technical constraint/requirement]
2. The system shall [integration requirement]  
3. The system should [performance requirement]

### 4. Security Requirements
**User Story**: As a [stakeholder], I want [security protection], so that [security benefit]

**Acceptance Criteria**:
1. The system shall [security control]
2. When [security event], the system shall [security response]
3. The system shall [compliance requirement]

### 5. Error Handling Requirements
**User Story**: As a [user], I want [error recovery], so that [continuity benefit]  

**Acceptance Criteria**:
1. The system shall [error detection]
2. When [error condition], the system shall [error response]
3. The system shall [recovery mechanism]

### 6. Performance Requirements
**User Story**: As a [user], I want [performance expectation], so that [efficiency benefit]

**Acceptance Criteria**:
1. The system shall [performance metric]
2. The system shall [scalability requirement]  
3. The system should [optimization target]

### 7. Integration Requirements
**User Story**: As a [system integrator], I want [integration capability], so that [integration benefit]

**Acceptance Criteria**:
1. The system shall [integration interface]
2. The system shall [data exchange requirement]
3. The system should [compatibility requirement]

### 8. Edge Case Requirements  
**User Story**: As a [user], I want [edge case handling], so that [robustness benefit]

**Acceptance Criteria**:
1. The system shall [boundary condition handling]
2. When [invalid input], the system shall [validation response]
3. When [system failure], the system shall [failure response]
4. The system shall [data integrity protection]

## 🚫 Out of Scope (Requirements Discipline)

### Features Explicitly NOT Included
- [Feature 1] - Not in user context, would create unnecessary complexity
- [Feature 2] - Common addition but not requested for this use case
- [Advanced capability] - Future consideration, not current requirements

### Non-Functional Elements NOT Included  
- [Performance level X] - Beyond stated needs
- [Security measure Y] - Not required for described use case
- [Integration Z] - Not mentioned in context

### Edge Cases NOT Addressed
- [Extreme edge case 1] - Very low probability, would add significant complexity
- [Theoretical scenario 2] - Not relevant to stated use cases
- [Speculative failure mode] - Over-engineering for current scope

### Why These Boundaries Matter

**Resource Focus**: Defining only needed requirements allows concentrated effort on understanding and specifying core functionality rather than spreading across speculative features.

**Implementation Efficiency**: Each additional requirement creates development overhead - coding, testing, documentation, maintenance that compounds throughout the project lifecycle.

**User Experience Coherence**: Requirements should serve the user's stated needs. Adding unmentioned features can create confusion and complexity for users.

**Project Success**: Clear boundaries prevent scope creep, which is a primary cause of project delays and budget overruns.

### Future Considerations (Noted but NOT Required)
- [Enhancement 1] - Could be valuable in future iterations
- [Capability 2] - Monitor need based on actual usage
- [Integration 3] - Evaluate when business case emerges

**Requirements Philosophy**: Focus on user's stated needs and essential supporting functionality, avoiding speculative additions that create unnecessary complexity without validated need.
```

[Generate actual comprehensive content based on all gathered context]

## 5. Quality Validation Framework

**Executing Kiro Stage 1 quality validation checkpoints...**

### Document Structure Validation

- Check: `.kiro/specs/${feature-name}/requirements.md` created successfully
- Check: Document contains Introduction section with clear feature summary
- Check: Requirements organized in hierarchical numbered list format (1., 2., 3.)  
- Check: Document follows exact Kiro template structure
- Check: All requirement categories present and properly formatted

### User Story Validation  

- Check: Each requirement includes exact format: "As a [role], I want [feature], so that [benefit]"
- Check: Role clearly identified and specific (user, admin, system, developer, etc.)
- Check: Feature described concretely and actionably (not vague)
- Check: Benefit articulates clear, measurable value proposition
- Check: User stories align with provided context and user needs

### EARS Format Compliance

- Check: Simple format: "The system shall [action]" compliance
- Check: Conditional format: "When [condition], the system shall [action]" compliance
- Check: Optional format: "The system should [action]" compliance
- Check: Complex format: "While [state], when [condition], the system shall [action]" compliance
- Check: No ambiguous language (avoiding "might", "could", "usually")

### Coverage Completeness Assessment

- Check: Functional requirements identified covering core capabilities
- Check: Non-functional requirements included (Performance, security, usability, reliability)
- Check: Technical constraints documented (Technology, infrastructure, integration requirements)  
- Check: Edge cases addressed comprehensively (Invalid input, system failure, boundary conditions)
- Check: Success criteria defined with measurable outcomes
- Check: User provided context fully incorporated

### Context Integration Validation

- Check: Product steering guidance applied to feature prioritization
- Check: Technical steering constraints incorporated into requirements
- Check: Structural steering patterns reflected in requirement organization
- Check: User context seamlessly integrated throughout
- Check: Steering document cross-references maintained

### Quality Standards Compliance  

- Check: All criteria testable (can be validated through automated/manual testing)
- Check: Requirements scope appropriate for implementation (not too broad/narrow)
- Check: Terminology consistent throughout document  
- Check: No duplicate or conflicting requirements identified
- Check: Requirements prioritized appropriately (shall vs should)

### Requirements Scope Validation

- Check: All requirements trace to user-provided context or logical necessity
- Check: No speculative or "nice to have" requirements added beyond context
- Check: Requirements complexity appropriate for stated use case
- Check: Out of scope section documents boundary decisions clearly
- Check: Edge cases limited to realistic scenarios within scope
- Check: Future considerations noted but not required in current scope

**Quality Validation Results:**

**Kiro Stage 1 Quality Assessment:**

- **Structure Validation**: Perfect compliance with Kiro template
- **EARS Format Compliance**: All criteria properly formatted using 4 EARS patterns
- **User Story Structure**: All stories follow exact "As a/I want/so that" template  
- **Coverage Analysis**:
  - Functional requirements: Comprehensive categories covering core functionality
  - Non-functional requirements: Performance, security, UX, reliability addressed
  - Technical constraints: Integration, technology, infrastructure requirements included
  - Edge cases: Failure scenarios comprehensively covered
  - User context integration: All provided context seamlessly incorporated

- **Context Integration**: All steering guidance and user input applied
- **Quality Standards**: All requirements testable and appropriately scoped  
- **Format Compliance**: Perfect adherence to Kiro document structure
- **Scope Discipline**: Requirements focused on user context, out-of-scope boundaries documented

**Overall Quality Score: [Calculated based on validation results]**

## 6. Requirements Review & Revision Cycle

## Requirements Draft Complete

I've generated comprehensive requirements following all Kiro Stage 1 standards, incorporating:

- Your context and input from our discussion
- Complete EARS format compliance with all 4 syntax patterns
- Comprehensive coverage across all requirement categories
- All steering context guidance applied
- Industry best practices for edge cases and error handling

**Generated Document:**
**Location**: `.kiro/specs/${feature-name}/requirements.md`  
**Quality Score**: [Score] (meeting all Kiro validation standards)

[Display key highlights of generated requirements]

**Please review your requirements document.**

**Consider:**

- Do the requirements capture your vision and needs accurately?
- Are there any user stories or scenarios missing?
- Do the acceptance criteria feel complete and testable?
- Are technical constraints and integration needs addressed properly?
- Do performance and security requirements match your expectations?
- Are error handling and edge cases comprehensive enough?
- Is the language clear and unambiguous?

**Your options:**

- **Request Changes**: Tell me what needs to be modified, added, or refined
- **Minor Tweaks**: Point out specific sections that need adjustment  
- **Ready to Approve**: If satisfied, say "looks good", "approved", or "yes"

**What's your feedback?**

[Handle user feedback and revision cycle]

---

### Revision Cycle (if changes requested)

[If user requests changes:]

1. **Analyze specific feedback** and identify areas for modification
2. **Update requirements.md** with requested changes while maintaining Kiro compliance
3. **Re-run quality validation** to ensure standards maintained  
4. **Present updated version** for another review cycle
5. **Continue until explicit approval received**

## 7. Final Approval & State Management

### Requirements Approved

Thank you for the approval! The requirements document is now finalized and ready for the design stage.

**Updating project state...**

```yaml
# Updating .kiro/specs/${feature-name}/spec.yaml
approvals:
  requirements: 
    generated: true
    approved: true
updated_at: "[current timestamp]"
```

**State Updated Successfully:**

- Requirements stage marked as completed and approved
- Project ready for next stage: Design Document Creation
- Use `/kiro:3-design-document-creation ${feature-name}` to proceed

**Final Deliverables:**

- **Requirements Document**: `.kiro/specs/${feature-name}/requirements.md` (Kiro-compliant, comprehensive)
- **Updated Project State**: `.kiro/specs/${feature-name}/spec.yaml` (requirements approved)
- **Quality Validation**: All Kiro Stage 1 standards met

### Next Steps

Ready to move to **Stage 2: Design Document Creation**? Run:

```
/kiro:3-design-document-creation ${feature-name}
```

**Kiro Stage 1 Complete - Requirements Clarification Successful!**
