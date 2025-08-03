---
description: Core workflow principles for all spec-driven development phases
applyTo: ".spec-workflow/**/*"
---

# Spec-Driven Development Workflow

Core workflow principles that apply to all spec-driven development phases.

## Phase Dependencies

### Sequential Workflow Requirements

- **Design phase requires approved requirements**
- **Tasks phase requires approved design**
- **Implementation requires approved tasks**
- **Each phase builds on the previous phase's deliverables**

### Approval Workflow

- **Manual review and approval required between phases**
- **Update spec metadata to indicate approval status**
- **Ensure quality standards are met before progression**
- **No automatic progression between phases**

## Requirements Methodology

### Hybrid USDD → EARS → SDD Approach

- **User Value Clarification**: Transform vague requests into clear user-focused understanding when needed
- **EARS Formalization**: Convert user value understanding into precise, testable requirements
- **SDD Execution**: Maintain direct executable specifications in implementation stages

### Personal Productivity Integration

- **Stakeholder Clarity**: Use user stories to clarify ambiguous requests and build understanding
- **Vague-to-Actionable Pipeline**: Systematic transformation from unclear requests to structured plans
- **Documentation Generation**: Structured progression suitable for ticket documentation and handoffs

## Workflow Integration

### File Structure Standards

- Use `.spec-workflow/specs/{feature}/` directory structure
- Maintain consistent file naming across all specifications
- Follow established metadata format in `spec.yaml`

### Language Handling

- **Check language field** in spec.yaml for all content generation
- **Generate content in specified language** (English default)
- **Maintain language consistency** across all phase documents

These workflow principles ensure consistent, disciplined spec-driven development across all projects.
