---
description: Create technical design for a specification
mode: agent
tools: ['search', 'codebase', 'editFiles']
---

# Technical Design

Create comprehensive technical design for feature: **${input:feature:Enter feature name}**

## Approval Gate: Requirements Check

**CRITICAL**: Design can only be generated after requirements are approved.

### Approval Status Check

Check spec metadata: [spec.yaml](../../.spec-workflow/specs/${input:feature}/spec.yaml)

**STOP HERE** if spec.yaml shows:

```yaml
approvals:
  requirements:
    approved: false
```

**Required Actions for Requirements Approval**:

1. **Review requirements.md** - Read through the generated requirements thoroughly
2. **Edit if needed** - Make any necessary changes directly in the requirements.md file
3. **Manual approval required** - Update spec.yaml manually to set `requirements.approved: true`
4. **Reasoning**: Human review ensures requirements accuracy before design phase

**Example approval in spec.yaml**:

```yaml
approvals:
  requirements:
    generated: true
    approved: true # ← Set this to true after human review
phase: "requirements-approved"
```

**Only proceed to design generation after requirements are explicitly approved by human review.**

## Context Analysis

### Steering Context

Reference steering documents if available:

- Current architecture: [structure.md](../../.spec-workflow/steering/structure.md)
- Technology stack: [tech.md](../../.spec-workflow/steering/tech.md)
- Product constraints: [product.md](../../.spec-workflow/steering/product.md)

### Requirements Context (APPROVED)

- Feature requirements: [requirements.md](../../.spec-workflow/specs/${input:feature}/requirements.md)
- Current design: [design.md](../../.spec-workflow/specs/${input:feature}/design.md)
- Spec metadata: [spec.yaml](../../.spec-workflow/specs/${input:feature}/spec.yaml)

## Task: Create Technical Design

**Prerequisites Verified**: Requirements are approved and ready for design phase.

Generate comprehensive design document in the language specified in spec.yaml:

### 1. Design Document Structure

Create design.md in the language specified in spec.yaml (check language field):

````markdown
# Technical Design

## Overview

[Technical overview of the implementation approach]

## Architecture

[Architecture diagram using mermaid]

```mermaid
graph TB
    A[Frontend Layer] --> B[API Gateway]
    B --> C[Business Logic]
    C --> D[Data Layer]
    D --> E[Database]
```
````

## Technology Stack

- **Frontend**: [React/Vue/Next.js] + [TypeScript]
- **Backend**: [FastAPI/Express/Django] + [Language]
- **Database**: [PostgreSQL/MySQL/MongoDB]
- **Authentication**: [JWT/OAuth/Auth0]
- **Testing**: [Jest/pytest] + [Testing Library/Playwright]
- **Deployment**: [Docker/Vercel/AWS]

## Components and Interfaces

[Detailed component design with clear interfaces]

### API Endpoints

```
GET /api/[resource]
POST /api/[resource]
PUT /api/[resource]/:id
DELETE /api/[resource]/:id
```

### Data Flow

[Description of how data flows through the system]

## Data Models

[Data structures and database schemas]

```typescript
interface [ModelName] {
  id: string;
  // Add relevant fields
}
```

## Error Handling

[Comprehensive error handling strategy]

## Security Considerations

[Authentication, authorization, data validation]

## Performance & Scalability

[Caching, optimization, scaling strategy]

## Testing Strategy

[Unit, integration, and E2E testing approach]

````

### 2. Design Quality Guidelines
- **Architecture Alignment**: Follow existing architectural patterns
- **Technology Consistency**: Use established technology stack
- **Interface Design**: Define clear component interfaces
- **Data Modeling**: Design appropriate data structures
- **Error Handling**: Plan comprehensive error scenarios
- **Testing Strategy**: Include unit, integration, and E2E testing

### 3. Integration Considerations
Based on steering and requirements:
- How components integrate with existing architecture
- Database schema changes required
- API endpoint design
- Performance considerations
- Security requirements

### 4. Mermaid Diagrams
Include relevant diagrams:
- System architecture
- Component interactions
- Data flow diagrams
- Sequence diagrams for key workflows

### 5. Update Metadata
Update spec.yaml with:
```yaml
phase: "design-generated"
progress:
  requirements: 100
  design: 100
  tasks: 0
approvals:
  requirements:
    generated: true
    approved: true
  design:
    generated: true
    approved: false
updated_at: "{current_timestamp}"
````

### 6. Document Generation Only

Generate the design document content ONLY. Do not include any review or approval instructions in the actual document file.

## Refinement Options

What would you like me to refine about this technical design?

- **Adjust architecture**: Modify system components or data flow?
- **Update technology choices**: Different frameworks or tools?
- **Refine API design**: Additional endpoints or modified interfaces?
- **Enhance security considerations**: Additional security measures?
- **Modify performance approach**: Different caching or optimization strategies?
- **Update integration points**: Better alignment with existing systems?
- **Proceed if satisfied** with design?

I can iterate on the design in our conversation until you're satisfied.

## Human Review Process

After generation, the design must be reviewed and approved before proceeding to tasks:

1. **Human reviews** the generated design.md
2. **Manual edits** can be made directly to the file if needed
3. **Approval** is granted by manually updating spec.yaml:
   ```yaml
   approvals:
     requirements:
       generated: true
       approved: true
     design:
       generated: true
       approved: true
   phase: "design-approved"
   ```
4. **Only after approval** can /spec-4-tasks: feature={feature-name} be used

## Instructions

1. **Check spec.yaml for language** - Use the language specified in the metadata
2. **Analyze requirements thoroughly** to understand scope
3. **Follow existing architecture patterns** from steering
4. **Create detailed component design** with clear interfaces
5. **Include comprehensive diagrams** using mermaid
6. **Plan error handling and testing** strategies
7. **Update tracking metadata** upon completion

Generate design that provides clear blueprint for implementation phase.
