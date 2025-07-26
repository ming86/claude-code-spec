---
description: Enhanced specification initialization with project analysis and codebase integration
allowed-tools: Bash, Read, Write, Glob, Grep, Task
---

# Enhanced Spec Initialization

Initialize a new specification with comprehensive project analysis and codebase integration:

**Project Description**: $ARGUMENTS

## Enhanced Context Analysis

### Steering Context Validation

- Structure context: @.kiro/steering/structure.md
- Technical constraints: @.kiro/steering/tech.md  
- Product context: @.kiro/steering/product.md

### Steering Files Assessment

!`ls -la .kiro/steering/ 2>/dev/null && echo "📁 Steering documents available for context" || echo "📁 No steering documents - will use codebase analysis"`

### Codebase Integration Analysis

!`echo "🔍 Codebase Pattern Analysis:"; find . -maxdepth 2 -name "*.ts" -o -name "*.js" -o -name "*.py" -o -name "*.jsx" -o -name "*.tsx" | head -5 | sed 's/^/  - /'`

### Project Technology Context

!`echo "⚙️ Technology Context:"; if [ -f "package.json" ]; then echo "- Node.js/JavaScript project"; FRAMEWORK=$(grep -o '"react"\|"vue"\|"next"\|"nuxt"' package.json | head -1 | tr -d '"'); if [ -n "$FRAMEWORK" ]; then echo "  - Framework: $FRAMEWORK"; fi; fi; if [ -f "requirements.txt" ] || [ -f "pyproject.toml" ]; then echo "- Python project"; fi; if [ -f "Cargo.toml" ]; then echo "- Rust project"; fi`

### Existing Patterns Detection

!`echo "🎯 Code Patterns:"; if [ -d "src/components" ]; then COMP_COUNT=$(find src/components -name "*.tsx" -o -name "*.jsx" | wc -l); echo "- Components: $COMP_COUNT files"; fi; if [ -d "src/pages" ] || [ -d "pages" ]; then PAGE_COUNT=$(find src/pages pages -name "*.tsx" -o -name "*.jsx" 2>/dev/null | wc -l); echo "- Pages: $PAGE_COUNT files"; fi; if [ -d "src/api" ] || [ -d "api" ]; then API_COUNT=$(find src/api api -name "*.js" -o -name "*.ts" -o -name "*.py" 2>/dev/null | wc -l); echo "- API endpoints: $API_COUNT files"; fi`

## Enhanced Project Description Analysis

### 1. Intelligent Feature Name Generation

Analyze the provided description to extract:

#### Project Purpose Extraction

- **Primary Goal**: Identify the main purpose and objective
- **Domain Context**: Understand the business or technical domain
- **Scope Boundaries**: Determine what's included and excluded
- **User Focus**: Identify target users and their needs

#### Technical Scope Analysis

- **Complexity Assessment**: Evaluate technical complexity level
- **Integration Requirements**: Identify system integration needs
- **Performance Considerations**: Extract performance requirements
- **Security Requirements**: Identify security considerations

#### Feature Name Algorithm

Generate a concise, descriptive feature name that:

1. **Captures core functionality** - Main purpose in 2-4 words
2. **Uses project terminology** - Consistent with existing codebase
3. **Avoids generic terms** - Specific to the actual feature
4. **Follows naming conventions** - Matches project patterns

### 2. Codebase-Informed Context Analysis

Use existing code patterns to inform specification setup:

#### Architecture Pattern Detection

!`echo "🏗️ Architecture Analysis:"; if grep -r "useState\|useEffect" src/ 2>/dev/null | head -1 >/dev/null; then echo "- React hooks pattern detected"; fi; if grep -r "class.*Component" src/ 2>/dev/null | head -1 >/dev/null; then echo "- Class component pattern detected"; fi; if grep -r "createSlice\|configureStore" src/ 2>/dev/null | head -1 >/dev/null; then echo "- Redux Toolkit pattern detected"; fi; if grep -r "router\|Route" src/ 2>/dev/null | head -1 >/dev/null; then echo "- Routing pattern detected"; fi`

#### API Pattern Analysis

!`echo "🌐 API Patterns:"; if grep -r "fetch\|axios" src/ 2>/dev/null | head -1 >/dev/null; then echo "- HTTP client pattern detected"; fi; if grep -r "POST\|GET\|PUT\|DELETE" src/ 2>/dev/null | head -1 >/dev/null; then echo "- REST API pattern detected"; fi; if grep -r "GraphQL\|gql" src/ 2>/dev/null | head -1 >/dev/null; then echo "- GraphQL pattern detected"; fi`

#### Testing Pattern Detection

!`echo "🧪 Testing Patterns:"; if find . -name "*.test.*" -o -name "*.spec.*" | head -1 >/dev/null; then echo "- Unit testing pattern detected"; fi; if grep -r "describe\|it\|test" src/ 2>/dev/null | head -1 >/dev/null; then echo "- Test framework usage detected"; fi; if find . -name "cypress" -o -name "playwright" | head -1 >/dev/null; then echo "- E2E testing pattern detected"; fi`

## Task: Enhanced Specification Structure Creation

### 1. Advanced Project Description Processing

#### Natural Language Analysis

- Extract key entities and relationships from description
- Identify user roles and interactions
- Determine system boundaries and external dependencies
- Parse functional and non-functional requirements

#### Complexity Assessment

- **Simple Feature** (1-2 components): Basic CRUD or UI enhancement
- **Medium Feature** (3-5 components): Integration or workflow feature
- **Complex Feature** (6+ components): Multi-system integration or major functionality

#### EARS Preparation Analysis

Pre-analyze description for EARS conversion readiness:

- Identify conditional statements that can become WHEN/THEN
- Extract user actions that map to GIVEN/WHEN/THEN scenarios
- Identify exception cases for IF/THEN handling

### 2. Enhanced Feature Name Generation

Generate feature name using intelligent analysis:

#### Context-Aware Naming

- **Domain-Specific**: Use terminology from project domain
- **Pattern-Consistent**: Follow existing naming conventions
- **Scope-Appropriate**: Match complexity and scope
- **Future-Proof**: Allow for natural extension

#### Feature Name Validation

!`echo "📝 Feature Name Generation:"; SUGGESTED_NAME=$(echo "$ARGUMENTS" | sed 's/[^a-zA-Z0-9 ]//g' | awk '{for(i=1;i<=3;i++) printf "%s-", tolower($i)}' | sed 's/-$//'); echo "- Suggested name: $SUGGESTED_NAME"`

### 3. Create Enhanced Spec Directory Structure

Create `.kiro/specs/{generated-feature-name}/` with enhanced templates:

#### Directory Creation with Validation

!`mkdir -p .kiro/specs/`

### 4. Enhanced spec.json Metadata

Create comprehensive metadata with codebase integration:

```json
{
  "feature_name": "{generated-feature-name}",
  "project_description": "$ARGUMENTS",
  "created_at": "current_timestamp",
  "updated_at": "current_timestamp",
  "language": "japanese",
  "phase": "initialized",
  "methodology": "EARS",
  "codebase_context": {
    "technology_stack": "{detected-stack}",
    "architecture_patterns": ["{detected-patterns}"],
    "testing_framework": "{detected-testing}",
    "api_patterns": ["{detected-api-patterns}"]
  },
  "complexity_assessment": {
    "level": "{simple|medium|complex}",
    "estimated_components": "{count}",
    "integration_points": ["{detected-integrations}"],
    "technical_challenges": ["{identified-challenges}"]
  },
  "approvals": {
    "requirements": {
      "generated": false,
      "approved": false,
      "methodology": "EARS"
    },
    "design": {
      "generated": false,
      "approved": false,
      "research_integrated": false
    },
    "tasks": {
      "generated": false,
      "approved": false,
      "multi_task_ready": false,
      "ears_traceable": false
    }
  },
  "progress": {
    "requirements": 0,
    "design": 0,
    "tasks": 0
  },
  "workflow_features": {
    "ears_methodology": true,
    "research_integration": true,
    "multi_task_execution": true,
    "task_validation": true
  },
  "ready_for_implementation": false,
  "multi_task_execution": false
}
```

### 5. Enhanced Template Files with Context

#### requirements.md (EARS-Prepared Template)

```markdown
# Requirements Document

## Project Overview
{Intelligent summary based on description analysis and codebase context}

## Original Project Description
$ARGUMENTS

## Codebase Integration Context
- **Technology Stack**: {detected-stack}
- **Architecture Patterns**: {detected-patterns}
- **Existing Patterns**: {patterns-to-follow}
- **Integration Points**: {detected-integrations}

## EARS Requirements
<!-- This section will use EARS methodology (WHEN/THEN format) -->
<!-- Generated requirements will follow: -->
<!-- WHEN [condition] THEN [outcome] -->
<!-- GIVEN [context] WHEN [action] THEN [response] -->
<!-- IF [exception] THEN [handling] -->

### Requirements Preparation Notes
Based on analysis, potential EARS patterns identified:
{Pre-identified WHEN/THEN scenarios from description}

---
**STATUS**: Ready for EARS requirements generation
**METHODOLOGY**: EARS (Easy Approach to Requirements Syntax)
**NEXT STEP**: Run `/spec-requirements {feature-name}` to generate EARS-format requirements
```

#### design.md (Research-Ready Template)

```markdown
# Technical Design Document

## Overview
<!-- Research-informed technical design will be generated after EARS requirements approval -->

## Codebase Integration Strategy
- **Existing Architecture**: {current-architecture}
- **Integration Approach**: {how-to-integrate}
- **Technology Alignment**: {technology-consistency}

## Research Areas Identified
Based on project analysis, research may be beneficial for:
{Identified research areas from complexity assessment}

---
**STATUS**: Waiting for EARS requirements approval
**RESEARCH INTEGRATION**: Optional research will enhance design quality
**NEXT STEP**: Complete and approve EARS requirements first
```

#### tasks.md (Multi-Task Ready Template)

```markdown
# Implementation Plan

## Multi-Task Execution Setup
<!-- Enhanced task structure with EARS requirement traceability -->
<!-- Supports parallel execution and validation loops -->

## Codebase Integration Planning
- **Code Organization**: {follow-existing-patterns}
- **Testing Integration**: {use-existing-framework}
- **Development Workflow**: {match-current-process}

---
**STATUS**: Waiting for research-informed design approval
**MULTI-TASK READY**: Supports enhanced execution with validation
**NEXT STEP**: Complete and approve research-informed design first
```

### 6. Enhanced CLAUDE.md Integration

Update active specifications with comprehensive context:

- Feature name with complexity assessment
- Technology integration notes
- Estimated scope and timeline
- Special considerations from analysis

### 7. Codebase Pattern Integration

Ensure new specification aligns with existing patterns:

- **Naming Conventions**: Follow existing file and component naming
- **Architecture Consistency**: Align with current architectural patterns
- **Testing Integration**: Use existing testing frameworks and patterns
- **API Design**: Follow established API patterns and conventions

## Enhanced Next Steps Guidance

### Workflow Path Selection

#### Standard Enhanced Workflow (Recommended)

1. **Generate EARS requirements**: `/spec-requirements {feature-name}`
   - Enhanced with EARS methodology
   - Optional research integration
   - Codebase pattern awareness

2. **Review and approve requirements**: Update spec.json
   - EARS format validation
   - Completeness check
   - Codebase integration review

3. **Generate research-informed design**: `/spec-design {feature-name}`
   - Optional research integration
   - Codebase pattern consistency
   - Architecture alignment

4. **Review and approve design**: Update spec.json
   - Research integration validation
   - Technical accuracy review
   - Implementation readiness check

5. **Generate multi-task implementation plan**: `/spec-tasks {feature-name}`
   - EARS requirement traceability
   - Multi-task execution support
   - Validation framework integration

6. **Review and approve tasks**: Update spec.json
   - Task structure validation
   - EARS traceability check
   - Multi-task readiness confirmation

7. **Execute multi-task implementation**: `/execute-tasks {feature-name}`
   - Self-correcting validation loops
   - Task tool integration
   - Progress tracking

### Advanced Features Available

- **EARS Methodology**: Structured, testable requirements
- **Research Integration**: Optional research for complex features
- **Multi-Task Execution**: Parallel task execution with validation
- **Codebase Integration**: Seamless integration with existing patterns
- **Validation Loops**: Self-correcting implementation with AI validation

## Instructions

1. **Analyze project description comprehensively** - Extract purpose, scope, complexity
2. **Integrate codebase context** - Understand existing patterns and conventions
3. **Generate intelligent feature name** - Context-aware, pattern-consistent naming
4. **Assess complexity and scope** - Determine appropriate workflow approach
5. **Prepare for EARS methodology** - Pre-identify WHEN/THEN scenarios
6. **Set up research readiness** - Identify areas that may benefit from research
7. **Enable multi-task execution** - Structure for enhanced implementation workflow
8. **Ensure codebase integration** - Align with existing architecture and patterns

## Enhanced Output Format

After initialization, provide:

### 1. Comprehensive Analysis Summary

- Generated feature name with rationale
- Complexity assessment and implications
- Codebase integration strategy
- Technology alignment notes

### 2. Context Integration Report

- Detected patterns and conventions
- Architecture consistency plan
- Testing framework integration
- API design alignment

### 3. Enhanced Workflow Guidance

- Specific next steps with generated feature name
- Enhanced workflow benefits explanation
- Expected timeline and complexity notes
- Advanced features available

This enhanced initialization ensures optimal integration with existing codebase while setting up for the advanced EARS-driven, research-integrated, multi-task execution workflow.
