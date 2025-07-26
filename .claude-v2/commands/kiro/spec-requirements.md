---
description: Generate comprehensive EARS-format requirements with optional research integration
allowed-tools: Bash, Read, Write, Edit, MultiEdit, Update, WebSearch, WebFetch, Task
---

# Enhanced Requirements Generation

Generate comprehensive requirements using **EARS methodology** for feature: **$ARGUMENTS**

## Context Validation

### Steering Context

- Architecture context: @.kiro/steering/structure.md
- Technical constraints: @.kiro/steering/tech.md
- Product context: @.kiro/steering/product.md

### Existing Spec Context

- Current spec directory: !`ls -la .kiro/specs/$ARGUMENTS/`
- Current requirements: @.kiro/specs/$ARGUMENTS/requirements.md
- Spec metadata: @.kiro/specs/$ARGUMENTS/spec.json

## Optional Research Integration

**Conduct research when beneficial for complex or unfamiliar features**:

### When to Research

- Complex business requirements needing industry context
- Technical approaches requiring best practice validation
- Integration with external systems or standards
- Performance, security, or compliance-critical features
- Unfamiliar domain or technology requirements

### Research Process

1. **Identify research needs** based on feature complexity
2. **Use WebSearch** for industry standards and best practices
3. **Use WebFetch** for specific technical documentation
4. **Document key findings** that inform requirements

### Research Documentation Format

When research is conducted, include in requirements.md:

```markdown
## Research Findings

### Industry Standards and Best Practices
- **[Source Name](URL)** - Key insight that informs requirements
- **[Best Practice](URL)** - Approach that influences our implementation
- **[Technical Guide](URL)** - Specific technical considerations

### Research Summary
- **Key Requirements Implications**: How research affects our requirements
- **Technical Constraints**: Research-identified limitations or considerations
- **Implementation Guidance**: Research-based recommendations for design phase
```

## Task: Generate EARS-Format Requirements

Create comprehensive requirements document in the language specified in spec.json:

### 1. EARS Methodology Integration

**CRITICAL**: Use EARS (Easy Approach to Requirements Syntax) format throughout:

#### EARS Format Rules

- **WHEN [condition/trigger] THEN [system response]**
- **GIVEN [context] WHEN [action] THEN [outcome]**
- **IF [exception condition] THEN [error handling]**

#### EARS Examples

```markdown
# Traditional User Story (AVOID):
"As a user, I want to login so I can access my account"

# EARS Format (USE):
WHEN user enters valid credentials AND clicks login button THEN system authenticates user and redirects to dashboard
GIVEN user has invalid credentials WHEN user attempts login THEN system displays error message and remains on login page
IF user fails authentication 3 times THEN system temporarily locks account for 15 minutes
```

### 2. Requirements Document Structure

Generate requirements.md in the language specified in spec.json:

```markdown
# Requirements Specification

## Overview
[Clear overview of the feature and its purpose]

## Research Findings
[Include this section only if research was conducted - see Research Documentation Format above]

## EARS-Format Requirements

### Requirement 1: [Descriptive Name]
**Scope**: [Brief description of what this requirement covers]

#### Primary Scenarios
1. **WHEN** [specific condition] **THEN** [specific expected outcome]
2. **GIVEN** [context] **WHEN** [user action] **THEN** [system response]
3. **WHEN** [another condition] **THEN** [corresponding outcome]

#### Exception Handling
1. **IF** [error condition] **THEN** [error handling behavior]
2. **IF** [edge case] **THEN** [system response]

#### Acceptance Criteria
- [ ] [Testable criterion 1]
- [ ] [Testable criterion 2]
- [ ] [Testable criterion 3]

### Requirement 2: [Descriptive Name]
**Scope**: [Brief description of what this requirement covers]

[Follow same pattern as Requirement 1]

### Requirement 3: [Additional Requirements]
[Continue pattern for all major requirements]

## Non-Functional Requirements

### Performance Requirements
- **WHEN** [load condition] **THEN** system responds within [time limit]
- **GIVEN** [concurrent users] **WHEN** [action] **THEN** system maintains [performance standard]

### Security Requirements
- **WHEN** [security event] **THEN** system [security response]
- **IF** [security violation] **THEN** system [protection measure]

### Usability Requirements
- **WHEN** [user interaction] **THEN** interface provides [usability feature]
- **GIVEN** [user context] **WHEN** [action] **THEN** system ensures [accessibility standard]

## Integration Requirements
[Requirements for integration with existing systems, using EARS format]

## Validation and Testing
Each EARS requirement includes specific conditions that can be directly translated to test cases.
```

### 3. EARS Quality Validation

After generating requirements, validate EARS compliance:

#### EARS Compliance Checklist

- [ ] All functional requirements use WHEN/THEN or GIVEN/WHEN/THEN structure
- [ ] Exception handling uses IF/THEN structure  
- [ ] Requirements are specific and testable
- [ ] Conditions and outcomes are clearly defined
- [ ] No vague language like "user-friendly" or "efficient"

#### Validation Commands

!`grep -c "WHEN.*THEN" .kiro/specs/$ARGUMENTS/requirements.md || echo "❌ Requirements missing EARS format"`
!`grep -c "GIVEN.*WHEN.*THEN\|IF.*THEN" .kiro/specs/$ARGUMENTS/requirements.md || echo "⚠️  Check complex EARS patterns"`

### 4. Requirements Quality Guidelines

- **Testable**: Each EARS requirement should be directly verifiable
- **Specific**: Use concrete conditions and measurable outcomes
- **Complete**: Cover all major user scenarios and edge cases
- **Traceable**: Clear mapping from user needs to system behavior
- **Consistent**: Follow EARS format throughout

### 5. Integration Considerations

Based on steering context, ensure requirements address:

- How this feature integrates with existing architecture
- Technical constraints that affect requirements
- Existing user workflows that need integration
- Performance and scalability implications
- Security and compliance requirements

### 6. Update Metadata

Update spec.json with:

```json
{
  "phase": "requirements-generated",
  "methodology": "EARS",
  "progress": {
    "requirements": 100,
    "design": 0,
    "tasks": 0
  },
  "approvals": {
    "requirements": {
      "generated": true,
      "approved": false,
      "methodology": "EARS"
    }
  },
  "updated_at": "current_timestamp"
}
```

### 7. Research Integration Tracking

If research was conducted, add to spec.json:

```json
{
  "research": {
    "conducted": true,
    "sources_count": "[number of sources]",
    "research_areas": ["[area1]", "[area2]"]
  }
}
```

## EARS Format Validation and Enhancement

### Automatic EARS Conversion

If starting with user stories or generic requirements, convert them:

#### Conversion Examples

```markdown
# Before (Generic):
"User should be able to search for products"

# After (EARS):
WHEN user enters search term in search box AND clicks search button THEN system displays relevant products matching the search criteria
GIVEN no products match search criteria WHEN user performs search THEN system displays "No results found" message with suggested alternatives
IF search term contains special characters THEN system sanitizes input and performs safe search
```

### Enhanced Error Handling Requirements

All EARS requirements must include corresponding error scenarios:

```markdown
# For every WHEN/THEN, consider:
WHEN [normal condition] THEN [expected response]
IF [error condition] THEN [error handling]
IF [edge case] THEN [edge case handling]
```

---

## REVIEW AND APPROVAL PROCESS (Not included in document)

### Human Review Required

After generating requirements.md, inform the user:

**NEXT STEP**: Human review required before proceeding to design phase.

### EARS Review Checklist

- [ ] All requirements use proper EARS format (WHEN/THEN, GIVEN/WHEN/THEN, IF/THEN)
- [ ] Requirements are specific and testable
- [ ] Exception handling is comprehensive
- [ ] Research findings are properly integrated (if applicable)
- [ ] Requirements align with project goals and constraints

### To Approve

After reviewing, update `.kiro/specs/$ARGUMENTS/spec.json`:

```json
{
  "approvals": {
    "requirements": {
      "generated": true,
      "approved": true,
      "methodology": "EARS"
    }
  },
  "phase": "requirements-approved"
}
```

**Only after approval can you proceed to `/spec-design $ARGUMENTS`**

## Instructions

1. **Check spec.json for language** - Use the language specified in the metadata
2. **Assess research needs** - Determine if WebSearch/WebFetch would benefit requirement quality
3. **Apply EARS methodology** - Convert all requirements to WHEN/THEN format
4. **Validate EARS compliance** - Use validation commands to ensure format adherence
5. **Consider technical constraints** - Reference steering documents for context
6. **Ensure comprehensive coverage** - Include normal, error, and edge case scenarios
7. **Update tracking metadata** - Include EARS methodology and research status

Generate requirements that provide clear, testable foundation for design phase using EARS methodology.
