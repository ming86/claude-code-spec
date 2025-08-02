---
description: Architecture and design documentation standards
applyTo: ".spec-workflow/**/design.md"
---

# Design Documentation Standards

Standards for technical design documents in the spec-driven development workflow.

## Document Structure Template

Design documents MUST follow this comprehensive structure:

```markdown
# Design Specification: {Feature Name}

## Overview

Brief description of the technical design and its purpose.

## Architecture Overview

### System Architecture

**MUST include mermaid diagram** showing:

- System components and their relationships
- Data flow between components
- Integration points with existing systems
- External dependencies and services

### Core Components

Detailed description of each major component:

- **Purpose**: What the component does
- **Location**: File paths and module organization
- **Lifetime**: Singleton, transient, scoped, etc.
- **Responsibilities**: Key functions and capabilities

## {Component/Feature} Design

### State Model Design (if applicable)

Class diagrams or state representations using mermaid:

- Data structures and their relationships
- State transitions and business logic
- Validation rules and constraints

### API Design (if applicable)

- Endpoint specifications with request/response formats
- Authentication and authorization requirements
- Error response formats and status codes

### Database Design (if applicable)

- Schema definitions and relationships
- Migration strategies
- Performance considerations

## Integration Patterns

### {System/Component} Integration

Detailed integration patterns:

- How feature integrates with existing codebase
- Interface definitions and contracts
- Data transformation requirements
- Communication protocols

## Data Model Specifications

### Entity Definitions

Code examples showing:

- Class/interface definitions
- Type specifications
- Validation requirements
- Serialization considerations

## Error Handling Strategy

### Exception Management

- Error types and classifications
- Error propagation patterns
- Logging and monitoring strategies
- Recovery mechanisms

## Performance Specifications

### Memory Efficiency

- Resource usage patterns
- Memory management strategies
- Performance optimization techniques

### Performance Requirements

- Latency requirements and benchmarks
- Throughput specifications
- Scalability considerations

## Security Considerations

### Thread Safety (if applicable)

- Concurrency patterns and locking strategies
- Race condition prevention
- Deadlock avoidance techniques

### Data Integrity

- Validation strategies
- Consistency guarantees
- Transaction management

## Testing Strategy

### Unit Testing Approach

- Test structure and organization
- Mock/stub strategies
- Code coverage requirements

### Integration Testing

- Integration test scenarios
- Test data management
- Performance testing approaches

## Dependencies and Integration

### Existing System Integration

- Architectural pattern compliance
- Dependency injection patterns
- Service integration approaches

### Required Dependencies

- External libraries and frameworks
- System dependencies
- Configuration requirements

## Implementation Validation

### Design Validation Checklist

- [ ] All approved requirements addressed in design with clear traceability
- [ ] **SCOPE CONTROL**: Design addresses only approved requirements - no additional functional requirements added
- [ ] Non-functional requirements addressed with specific metrics where applicable
- [ ] Integration patterns defined with clear interface specifications
- [ ] Error handling strategy appropriate with patterns and examples
- [ ] Performance specifications include measurable criteria and benchmarks where applicable
- [ ] Security considerations addressed appropriate to feature scope
- [ ] Testing strategy appropriate for all design components
- [ ] Architectural diagrams provided using mermaid where applicable
- [ ] Scenario-based technology approach applied (greenfield/brownfield/hybrid as appropriate)
- [ ] Research findings properly documented with source citations where applicable

## Conclusion

Summary of design decisions and next steps for implementation.
```

## Architecture Documentation Requirements

### Required Elements

- **SHOULD use mermaid diagrams** for system architecture visualization where applicable
- **MUST define clear component interfaces** and responsibilities with appropriate examples
- **MUST specify data models** with type definitions and validation rules where applicable
- **MUST include error handling strategy** with appropriate patterns and examples
- **MUST address performance requirements** with specific metrics and benchmarks where applicable
- **MUST include security considerations** appropriate to the feature scope

### Diagram Standards

**System Architecture Diagrams MUST include:**

- Component relationships and dependencies
- Data flow directions and types
- Integration points with existing systems
- External service dependencies

**Class/State Diagrams MUST include:**

- Entity relationships and cardinality
- Method signatures and interfaces
- State transitions where applicable
- Validation rules and constraints

## Scope Control Requirements

### Design Scope Management

- **MUST address approved requirements** in design specifications with clear traceability for all requirements
- **MUST NOT add new functional requirements** beyond what is specified in approved requirements  
- **SHOULD enhance implementation approaches** for existing requirements through research and best practices
- **MUST document additional feature ideas** for future consideration but exclude from current design scope

## Technology-Specific Design Standards

### Scenario-Based Technology Approach

#### Greenfield Projects (No Existing Codebase)
- **MUST analyze project requirements** to determine appropriate technology stack selection
- **MUST make explicit technology decisions** based on requirements, team expertise, and constraints
- **MUST design specifically for chosen technology stack** once technology decisions are made
- **MUST document technology selection rationale** with clear reasoning

#### Brownfield Projects (Existing Codebase)
- **MUST analyze existing codebase** to identify current technology stack and patterns
- **MUST design for existing technology stack** to maintain consistency and integration
- **MUST follow established architectural patterns** unless compelling reasons exist for changes
- **SHOULD leverage existing components** and frameworks where applicable

#### Hybrid Projects (Adding New Technology)
- **MUST analyze existing technology constraints** and integration requirements
- **MUST justify new technology choices** with clear business or technical rationale
- **MUST design integration patterns** between existing and new technology components
- **MUST document migration strategy** where technology changes affect existing systems

## Integration Requirements

### Architectural Compliance

- **Follow existing architectural patterns** and maintain consistency
- **Use established coding conventions** and style guidelines
- **Leverage existing utilities and components** before creating new ones
- **Consider impact on existing features** and backward compatibility
- **Document integration points** with clear interface specifications

### Code Quality Standards

- **Include code examples** demonstrating key patterns and implementations
- **Specify testing approaches** for design validation
- **Define performance benchmarks** with measurable criteria
- **Address security implications** of design decisions

### Enhanced Quality Criteria

- **MUST address approved requirements** in design specifications with clear traceability for all requirements
- **SHOULD include architectural diagrams** using mermaid for system visualization where applicable
- **MUST specify integration patterns** with clear interface definitions for all external connections
- **SHOULD include research citations** for complex features with proper source attribution
- **MUST validate design completeness** against quality checklist before completion

## Research Integration

### Technical Research Requirements

- **Industry best practices** relevant to the feature design
- **Technology evaluation** when choosing between alternatives
- **Performance analysis** of design choices
- **Security assessment** of proposed solutions

### Source Documentation

- **Include citations** for external research and standards
- **Document design rationale** based on research findings
- **Explain trade-offs** between alternative approaches
- **Reference existing implementations** that inform design decisions

### Research Integration Standards

- **MUST include source citations** for all external research and technical standards with proper URLs
- **MUST document design rationale** based on research findings with clear reasoning and decision criteria
- **MUST explain trade-offs** between alternative approaches with structured pros/cons analysis
- **SHOULD reference existing implementations** that inform design decisions where applicable and relevant
- **MUST focus research on approved requirements** and avoid scope expansion during research activities

## Validation Requirements

### Design Completeness

- **All requirements addressed**: Every functional and non-functional requirement has a corresponding design element
- **Integration verified**: All integration points are clearly specified and validated
- **Performance validated**: Design meets specified performance criteria
- **Security assessed**: Security implications are identified and addressed

### Quality Assurance

- **Reviewability**: Design is clear and complete enough for effective review
- **Implementation Readiness**: Sufficient detail provided for development teams
- **Testability**: Testing strategies are practical and appropriate
- **Maintainability**: Design supports long-term maintenance and evolution

These standards ensure design documents provide appropriate architectural guidance, clear integration patterns, and sufficient detail for reliable implementation.
