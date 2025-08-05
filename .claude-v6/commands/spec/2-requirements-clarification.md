---
description: 'Generate comprehensive EARS-format requirements with systematic clarification and optional research'
argument-hint: '[feature-name]'
---

# Role and Objective

Analyze project context thoroughly and generate detailed EARS-format requirements that are testable, prioritized, and fully integrated with existing system capabilities through systematic user story clarification.

# Instructions

## Requirements Generation Strategy

- **USDD → EARS Pipeline**: Transform fuzzy ideas into clear user stories, then into formal EARS requirements
- **Context Integration**: Requirements must align with existing system capabilities and architectural constraints
- **Systematic Clarification**: Apply USDD methodology regardless of initial apparent clarity
- **Research Integration**: Incorporate industry best practices for complex or critical features
- **Quality Focus**: Each requirement must include specific, measurable acceptance criteria

## Anti-Shortcut Quality Patterns

- Follow systematic USDD analysis regardless of initial apparent clarity of feature requests
- Analyze existing system capabilities rather than making assumptions about integration
- Create project-specific requirements based on actual codebase analysis, not generic templates
- Use comprehensive research for complex features rather than assuming implementation approaches

# Execution Steps

## 1. Comprehensive Context Analysis and Validation

**Objective**: Build complete understanding of feature context, system constraints, and integration requirements

**Process**:

- Verify specification exists and is ready for requirements generation
- Examine integration patterns and architectural approaches in existing codebase
- Review steering documents for project context, technical constraints, and objectives
- Analyze current spec.yaml metadata to understand feature scope and initial requirements
- Identify existing user workflows, system boundaries, and technical constraints
- Understand integration points where feature connects with existing system components

## 2. User Story Generation and Feature Scope Definition

**Objective**: Transform feature descriptions into clear user stories through systematic USDD analysis

**USDD (User Story Driven Development) Process**:

- **Always apply systematic analysis** regardless of initial apparent clarity
- **Transform fuzzy ideas** into clear user-focused understanding through exploration
- **Generate user stories** in "As a [persona], I want [intent], so that [value]" format
- **Systematically explore** personas, use cases, contexts, and underlying problems
- **Focus on understanding** who benefits and what problem is being solved
- **Determine research needs** for complex requirements, technical approaches, or industry standards
- **Use research** to inform requirements with industry best practices and proven approaches
- **Define clear feature boundaries** with explicit included vs. excluded scope

## 3. EARS Requirements Development and Validation

**Objective**: Convert user stories into comprehensive, properly formatted EARS requirements

**EARS (Easy Approach to Requirements Syntax) Process**:

- **Generate functional requirements** using proper EARS format: "WHEN [condition] THEN [response]"
- **Develop specific acceptance criteria** with clear pass/fail conditions and edge case handling
- **Assign priority levels** (must-have, should-have, could-have) with clear impact rationale
- **Document dependencies** on other features, external systems, infrastructure, or data components
- **Create non-functional requirements** covering performance, security, usability, and system integration
- **Validate each requirement** against quality criteria: specific, testable, complete, consistent, feasible

## 4. Documentation Integration and Workflow Update

**Objective**: Ensure proper documentation integration and update workflow tracking

**Process**:

- Update requirements.md with comprehensive requirements document
- Verify all requirements align with existing system capabilities and constraints
- Confirm acceptance criteria are measurable and testable within project capabilities
- Update spec.yaml with generation tracking and phase progression
- Provide clear next steps guidance for human review and approval workflow
- Document assumptions, risks, or areas requiring further clarification

# USDD → EARS Methodology (SURGICAL Consolidation)

## USDD (User Story Driven Development)

**Purpose**: Transform fuzzy ideas into clear user-focused understanding

**Process**:

- **Systematic Analysis**: Always clarify through analysis regardless of initial apparent clarity
- **User Focus**: Capture user empathy through "As a [persona], I want [intent], so that [value]" format
- **Problem Exploration**: Systematically explore personas, use cases, contexts, and underlying problems
- **Value Understanding**: Focus on understanding who benefits and what problem is being solved

## EARS (Easy Approach to Requirements Syntax)

**Purpose**: Convert user value understanding into precise, testable requirements

**Format Standards**:

- **Primary Format**: WHEN [condition] THEN [response]
- **Extended Format**: GIVEN [context] WHEN [action] THEN [outcome]
- **Quality Requirements**: Specific, measurable conditions and outcomes
- **Acceptance Criteria**: Clear pass/fail conditions for each requirement

## Research Integration Framework

### When to Conduct Research

- **Complex Requirements**: Industry-specific workflows or compliance requirements
- **Technical Standards**: Integration with external systems or industry protocols
- **Security-Sensitive**: Authentication, authorization, data protection features
- **Performance-Critical**: High-throughput, low-latency, or resource-intensive operations

### Research Documentation Format

```markdown
## Research Findings

### Industry Standards and Best Practices

- [Standard/Specification](URL) - Key requirements and constraints
- [Industry Resource](URL) - Best practices and recommendations

### Technical Research Findings

- [Technical Resource](URL) - Implementation approaches and considerations
- [Framework Documentation](URL) - Integration requirements and capabilities

### Key Insights for Requirements

- Research-driven requirement refinements
- Risk mitigation strategies
- Implementation approach recommendations

### Impact on Requirements

- How research findings influenced requirement definitions
- Trade-offs and decisions made based on research
- Future considerations identified
```

# Requirements Document Structure

## Feature Overview Section

```markdown
# Requirements Document: {Feature Name}

## Feature Overview

### Purpose and Project Value

{Clear description of why this feature is needed and what project value it provides}

### Integration with Existing System

{How this feature connects with current system components and user workflows}

### Scope Definition

**Included in Scope:**

- {Specific functionality and capabilities included}
- {User workflows and use cases covered}

**Excluded from Scope:**

- {Functionality explicitly not included in this phase}
- {Future enhancements or related features}

### Success Criteria

{Measurable criteria for determining feature success}
```

## User Stories Section

```markdown
## User Stories

{Generated through systematic USDD analysis}

### Primary User Stories

- As a [persona], I want [intent], so that [value]
- As a [persona], I want [intent], so that [value]

### Edge Case User Stories

- As a [persona], I want [intent], so that [value]
```

## Functional Requirements Section

```markdown
## Functional Requirements

### {Requirement Category}

**REQ-{ID}**: {EARS Format Statement}

**Acceptance Criteria:**

- {Specific, testable condition with measurable outcome}
- {Edge case handling and error condition responses}
- {Performance or quality thresholds where applicable}

**Priority:** {Must-have|Should-have|Could-have} - {Project rationale}

**Dependencies:**

- {Other features, systems, or components this requirement depends on}
- {External integrations or data requirements}

**Testing Notes:**

- {Specific testing approaches or considerations}
- {Test data requirements or environmental needs}
```

## Non-Functional Requirements Section

```markdown
## Non-Functional Requirements

### Performance Requirements

- **Response Time**: {Specific time thresholds for different operations}
- **Throughput**: {Expected transaction volume and capacity requirements}
- **Scalability**: {Growth expectations and scaling considerations}
- **Resource Usage**: {Memory, CPU, storage constraints and expectations}

### Security Requirements

- **Authentication**: {Required authentication mechanisms and standards}
- **Authorization**: {Permission and access control requirements}
- **Data Protection**: {Encryption, privacy, and data handling requirements}
- **Compliance**: {Regulatory or security standards that must be met}

### Usability and Compatibility Requirements

- **User Experience**: {Accessibility, responsiveness, and interaction standards}
- **Browser/Device Support**: {Specific compatibility requirements}
- **Integration Standards**: {API compatibility and data format requirements}
- **Internationalization**: {Language, locale, and cultural considerations}
```

# EARS Format Standards and Examples

## Quality EARS Examples

```markdown
REQ-001: WHEN user clicks "Submit" button AND all required fields are filled THEN system processes request within 2 seconds

REQ-002: GIVEN user is authenticated WHEN user accesses protected resource THEN system grants access and logs access attempt

REQ-003: WHEN invalid data is submitted THEN system displays specific error message highlighting problematic fields within 1 second

REQ-004: GIVEN system is under high load with >1000 concurrent users WHEN user submits data processing request THEN system maintains response time under 5 seconds and queues request if necessary

REQ-005: GIVEN user has unsaved changes WHEN user attempts to navigate away THEN system displays confirmation dialog and prevents navigation until user confirms or saves changes
```

## EARS Quality Standards

- **Specificity**: Use precise, measurable conditions and outcomes avoiding vague terms like "quickly" or "properly"
- **Testability**: Include quantifiable criteria that can be verified through automated or manual testing
- **Completeness**: Cover normal flow, edge cases, and error conditions for comprehensive feature coverage
- **Consistency**: Use consistent terminology, formatting, and measurement units across all requirements

# Quality Validation

## Requirements Quality Checklist

- [ ] All functional requirements use proper EARS format where condition/response patterns apply
- [ ] Each requirement has detailed, testable acceptance criteria with clear pass/fail conditions
- [ ] Priority levels assigned to all requirements with clear impact rationale
- [ ] Dependencies and constraints clearly documented with specific integration requirements
- [ ] Non-functional requirements comprehensively address performance, security, usability, and compatibility
- [ ] Integration with existing system capabilities verified through codebase analysis
- [ ] Research findings incorporated where applicable with proper source citations
- [ ] User stories generated through systematic USDD analysis regardless of initial clarity
- [ ] Edge cases and error conditions explicitly addressed in requirements and acceptance criteria

## Documentation Quality Standards

- [ ] Professional language focused on observable user and system behavior rather than implementation details
- [ ] Clear scope boundaries and feature limitations explicitly defined to prevent scope creep
- [ ] All requirements are actionable and implementable within project constraints
- [ ] Consistent terminology and measurement units used throughout document
- [ ] Source citations included for research-informed requirements with relevant insights documented
- [ ] Requirements are traceable to project objectives and user needs
- [ ] Document structure follows template format for consistency and completeness

## Integration and Workflow Validation

- [ ] Requirements document successfully updated at `.spec-workflow/specs/{feature}/requirements.md`
- [ ] Spec metadata updated at `.spec-workflow/specs/{feature}/spec.yaml` with proper generation tracking
- [ ] Phase updated to "requirements-generated" with approval workflow properly configured
- [ ] Next steps guidance provided for human review and approval process
- [ ] Integration verified with existing project structure and development workflow
- [ ] No conflicts with existing system capabilities or architectural constraints
- [ ] All assumptions, risks, and clarification needs clearly documented

# Examples

## Argument Handling

```bash
/spec:2-requirements-clarification user-authentication-system
/spec:2-requirements-clarification payment-processing-integration
/spec:2-requirements-clarification real-time-notifications
```

## USDD Analysis Example

1. **Input**: "Add user login functionality"
2. **USDD Analysis**: "Who needs to log in? Why do they need access? What value does authentication provide? What are the different user types?"
3. **User Stories**:
   - "As a returning user, I want to log in with my credentials, so that I can access my personalized dashboard"
   - "As a system administrator, I want to review login attempts, so that I can monitor security"
4. **EARS Requirements**: "WHEN user enters valid credentials AND clicks login THEN system authenticates user and redirects to dashboard within 2 seconds"

## Research Integration Example

- **Complex Feature**: OAuth integration with multiple providers
- **Research Conducted**: Industry OAuth 2.0 standards, security best practices, provider-specific requirements
- **Requirements Impact**: Additional security requirements based on IETF specifications, provider-specific authentication flows

## Systematic Clarification Example

- **Initial Request**: "Add notifications"
- **USDD Questions**: "Who needs notifications? What events trigger them? How should they be delivered? What happens if users are offline?"
- **Generated User Stories**:
  - "As a project member, I want to receive notifications when tasks are assigned to me, so that I can respond promptly"
  - "As a project manager, I want to be notified when deadlines approach, so that I can take corrective action"

## Complete Requirements Workflow

1. **Context Analysis**: "Analyzing existing authentication patterns in codebase... Found JWT implementation with role-based access"
2. **USDD Analysis**: "Exploring user personas and authentication needs... Identified 3 user types with different access requirements"
3. **Research Integration**: "Researching OAuth 2.0 best practices for secure authentication... Analyzing industry standards"
4. **EARS Generation**: "Converting user stories to formal requirements... Creating testable acceptance criteria"
5. **Validation**: "Verifying requirements align with existing system capabilities and architectural constraints"

Create comprehensive, research-informed requirements that provide a solid foundation for technical design while maintaining full integration with existing system capabilities and industry best practices.
