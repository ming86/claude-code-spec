---
description: "Kiro Domain-Specific Steering: Create specialized steering documents for enhanced workflow quality"
argument-hint: "domain-name (api-standards, testing, security, performance, database, deployment)"
---

<role>
You are a precision Kiro Domain-Specific Steering engine, specializing in creating specialized steering documents that provide targeted guidance for specific technical domains while seamlessly integrating with core steering documents and maintaining automatic loading capabilities. Your objective is to generate genuinely useful domain-specific guidance that enhances workflow quality across all Kiro stages while maintaining strict compatibility with the core steering system.
</role>

<context>
Domain-specific steering documents extend the core Kiro steering system (product.md, tech.md, structure.md) with specialized guidance for technical domains like API design, testing, security, performance, database management, and deployment. These documents use sophisticated file pattern matching for automatic loading when working on domain-relevant files and provide enhanced context for requirements generation, design decisions, implementation planning, and task execution stages.
</context>

# Kiro Custom Steering Creation

## 1. Argument Validation & Domain Selection

<domain_validation_process>

**First, I'll systematically analyze your domain selection and current steering infrastructure to determine the optimal approach for creating specialized domain guidance.**

Let me check your current steering setup and validate the domain selection.

**Available Domain Templates:**

- **api-standards** - API design patterns, authentication, versioning, documentation standards
- **testing** - Testing frameworks, coverage standards, CI/CD integration approaches
- **security** - Authentication, authorization, data protection, compliance policies  
- **performance** - Performance benchmarks, optimization strategies, monitoring approaches
- **database** - Schema design, migrations, query patterns, backup procedures
- **deployment** - CI/CD workflows, environment strategies, rollback procedures

**Current Custom Steering Analysis:**

!ls .kiro/steering/ 2>/dev/null | grep -v -E "(product|tech|structure)\.md" | grep "\.md$" || echo "No custom steering documents found"

**Checking domain argument...**

If you didn't provide a domain name, please select from the available templates above.

### Domain Selection Help

**Popular Domain Choices:**

- **api-standards** → For projects with REST APIs, GraphQL, or microservice architectures
- **testing** → For projects emphasizing test-driven development and quality assurance
- **security** → For applications handling sensitive data or requiring compliance
- **performance** → For high-performance applications or systems with scaling requirements  
- **database** → For data-intensive applications with complex database interactions
- **deployment** → For projects with sophisticated deployment pipelines or multi-environment strategies

**Please specify which domain template you'd like to create:**

- Type the domain name exactly as shown (kebab-case format)
- Domain will be created as `.kiro/steering/${domain-name}.md`
- Custom steering enhances all workflow stages with domain-specific guidance

**Waiting for your domain selection...**

</domain_validation_process>

[Wait for user to provide valid domain name before continuing]

---

Once you provide a valid domain name, I'll continue with that domain template.

## 2. State & Context Validation + Steering Infrastructure Check

<infrastructure_analysis>

**After validating your domain selection, I'll now carefully reflect on the existing steering infrastructure to ensure optimal integration strategy.**

**Analyzing steering infrastructure for domain:** ${domain-name}

!test -d ".kiro" && echo "KIRO_DIR_EXISTS" || echo "KIRO_DIR_MISSING"
!test -d ".kiro/steering" && echo "STEERING_DIR_EXISTS" || echo "STEERING_DIR_MISSING"
!test -f ".kiro/steering/${domain-name}.md" && echo "DOMAIN_EXISTS" || echo "DOMAIN_NEW"

**Validating steering foundation:**

!test -f ".kiro/steering/product.md" && echo "PRODUCT_EXISTS" || echo "PRODUCT_MISSING"
!test -f ".kiro/steering/tech.md" && echo "TECH_EXISTS" || echo "TECH_MISSING"  
!test -f ".kiro/steering/structure.md" && echo "STRUCTURE_EXISTS" || echo "STRUCTURE_MISSING"

**Steering Infrastructure Status:**

- **Steering Directory**: [Checking if .kiro/steering/ exists]
- **Core Steering Documents**: [Verifying product.md, tech.md, structure.md exist]
- **Domain Document**: ${domain-name}.md [New creation or update of existing]

**Loading existing steering context for integration:**

@.kiro/steering/product.md
@.kiro/steering/tech.md
@.kiro/steering/structure.md

**Infrastructure Recommendations:**

[If core steering missing:]
⚠️  **Core steering documents missing** - recommend running `/kiro:0-steering` first for complete setup

[If core steering exists:]
✅ **Core steering foundation detected** - ready for domain-specific enhancement

**Ready to proceed with ${domain-name} domain steering creation.**

</infrastructure_analysis>

## 3. Domain Context Gathering

<domain_context_gathering>

**Domain Focus:** ${domain-name}  
**Context Integration:** [Leveraging existing core steering for domain-specific enhancement]

**Domain-Specific Context Gathering**

Based on your selected domain, I need to understand your specific needs and preferences in this area. This context will be used to customize the domain steering template to your actual project needs rather than generating generic domain guidance.

**Please share information about your ${domain-name} context:**

### Universal Context (All Domains)

- **Current state**: What you're currently doing in this domain area
- **Pain points**: Specific challenges or inconsistencies you want to address  
- **Goals**: What you want to achieve with domain-specific guidance
- **Standards**: Any existing standards, tools, or approaches you want to preserve/build on

### ${domain-name} Specific Context

#### For API Standards Domain

- **API patterns**: REST, GraphQL, RPC - which do you use/prefer?
- **Authentication approaches**: JWT, OAuth, API keys - your security model?
- **Versioning strategy**: URL versioning, header versioning, semantic versioning preferences?
- **Documentation standards**: OpenAPI/Swagger, custom docs - your documentation approach?
- **Error handling patterns**: Standard error responses, status code conventions?

#### For Testing Domain

- **Testing frameworks**: Jest, pytest, JUnit - what you use or want to use?
- **Coverage expectations**: Coverage targets, types of testing prioritized?
- **Test organization**: File structures, naming conventions, test categorization?
- **CI/CD integration**: How testing fits into your deployment pipeline?
- **Quality gates**: When tests block deployments, performance test requirements?

#### For Security Domain

- **Compliance requirements**: GDPR, HIPAA, SOX - any regulatory requirements?
- **Authentication methods**: Multi-factor, SSO, passwordless - your user security model?
- **Data protection needs**: Encryption requirements, data classification levels?
- **Vulnerability management**: Security scanning, penetration testing, incident response?
- **Access control patterns**: RBAC, ABAC, principle of least privilege implementation?

#### For Performance Domain

- **Performance targets**: Response times, throughput, scalability requirements?
- **Optimization priorities**: Database queries, API responses, UI rendering, background jobs?
- **Monitoring approaches**: APM tools, custom metrics, alerting strategies?
- **Scaling strategies**: Horizontal scaling, caching layers, load balancing approaches?
- **Performance testing**: Load testing tools, performance regression prevention?

#### For Database Domain

- **Database technologies**: PostgreSQL, MySQL, MongoDB - what you use?
- **Schema evolution**: Migration strategies, versioning approaches, rollback procedures?
- **Query optimization**: Indexing strategies, query performance monitoring?
- **Data modeling patterns**: Normalization levels, document structure, relationship management?
- **Backup and recovery**: Backup strategies, disaster recovery, data retention policies?

#### For Deployment Domain

- **CI/CD platforms**: GitHub Actions, GitLab CI, Jenkins - your deployment tools?
- **Environment strategy**: Development, staging, production - how many environments?
- **Deployment patterns**: Blue-green, canary, rolling deployments - your approach?
- **Rollback procedures**: How you handle deployment failures and recovery?
- **Infrastructure management**: Docker, Kubernetes, serverless - your deployment targets?

**Additional Domain Guidance:**

- **Integration points**: How this domain intersects with your other project areas
- **Team considerations**: Skill levels, training needs, collaboration patterns
- **Tool preferences**: Specific tools you want guidance to reference or avoid
- **Constraints**: Technical, budget, or organizational limitations to consider

**You can share as much or as little as you'd like in one or multiple messages.**

**When ready for domain steering generation, say 'proceed' or 'generate ${domain-name} steering'**

</domain_context_gathering>

[Wait for user domain-specific context inputs until they say to proceed]

---

## Domain Steering Scope Planning

<domain_scope_planning>

Based on your context, here's my approach to creating your ${domain-name} domain steering:

**Domain Guidance Will Include:**

- [Context element 1] - Standards and patterns based on your current approach
- [Context element 2] - Guidelines addressing your specific pain points
- [Context element 3] - Quality criteria aligned with your stated goals
- [Integration guidance] - How domain standards enhance your existing workflow

**🚫 Will NOT Include (Domain Focus Discipline):**

- [Unmentioned technologies] - No assumptions about tools you don't use
- [Generic best practices] - Only patterns relevant to your specific context
- [Speculative standards] - Only guidance that addresses your actual needs
- [Over-engineering] - Simple, practical standards that enhance rather than burden development

**Domain Scope Boundaries:**

- **Practical orientation**: Standards that solve your actual problems
- **Integration focus**: Guidance that works with your existing tech stack
- **Team-appropriate**: Standards matching your team's current capabilities
- **Context-driven**: Only include elements that apply to your project reality

**Workflow Integration Preview:**

- **Requirements Enhancement**: How ${domain-name} guidance improves requirement generation quality
- **Design Enhancement**: How domain standards guide architectural decisions  
- **Tasks Enhancement**: How domain patterns influence implementation planning
- **Execution Enhancement**: How domain standards guide coding decisions during task execution

**Does this domain-focused approach align with your needs?**

**Your options:**

- **Scope looks right**: Say 'proceed' to generate ${domain-name} steering with these boundaries
- **Adjust focus**: Tell me what to emphasize or de-emphasize in the guidance
- **Add context**: Share additional ${domain-name} information for better guidance generation
- **Pattern guidance**: Ask about file pattern matching for conditional loading setup

**What's your feedback on this ${domain-name} steering approach?**

</domain_scope_planning>

[Wait for user alignment before proceeding to domain steering generation]

## 4. Domain Steering Generation

<domain_template_generation>

**After gathering complete domain context and confirming scope alignment, I'll now systematically generate specialized ${domain-name} domain steering incorporating all provided information.**

**Generating comprehensive ${domain-name} domain steering...**

Now I'll create specialized domain steering incorporating:

- Your provided ${domain-name} context and preferences from above
- Integration with existing core steering (product, tech, structure)
- Domain-specific standards and guidelines for workflow enhancement
- File pattern configuration for automatic loading during relevant work
- Quality criteria and validation methods specific to ${domain-name}

**CRITICAL DOMAIN STEERING REQUIREMENTS:**

- Address all provided context for ${domain-name} domain
- Include practical standards that enhance rather than burden development
- Provide clear integration guidance for all workflow stages
- Configure appropriate file patterns for conditional loading
- Maintain focus on your specific project needs (no generic over-engineering)

**Generating ${domain-name}.md...**

Creating domain-specific steering document at: `.kiro/steering/${domain-name}.md`

<kiro_domain_steering_template>

**DOMAIN STEERING DOCUMENT TEMPLATE:**

```markdown
---
inclusion: fileMatch
fileMatchPattern: "${domain-specific-pattern-based-on-domain}"
description: "${Domain} standards and guidelines for enhanced Kiro workflow quality"
---

# ${Domain} Steering Document

## Overview

[Domain-specific context and objectives based on user input]

**Domain Purpose**: [Why this domain guidance enhances your project based on provided context]

**Integration with Core Steering**: [How this domain guidance works with product, tech, and structure steering]

**Workflow Enhancement**: [Specific ways this domain improves requirements, design, tasks, and execution stages]

## Standards

### ${Domain}-Specific Standards

[Standards based on user context - tools, frameworks, approaches they mentioned]

### Quality Requirements

[Quality criteria specific to domain based on user goals and pain points]

### Integration Requirements  

[How domain elements should integrate with other project components]

## Guidelines

### Implementation Guidelines

[Practical guidance for implementing domain standards in daily work]

### Best Practices

[Domain-specific best practices based on user context and preferences]

### Common Patterns

[Established patterns for domain work based on user's current approaches]

### Quality Assurance

[Domain-specific quality validation and review processes]

## Examples

### Practical Examples

[Concrete examples relevant to user's technology stack and context]

### Template References

[Reference templates, boilerplate, or starting points for domain work]

### Integration Examples

[Examples of how domain standards apply across different project areas]

## Validation

### Quality Criteria

[Specific measurable criteria for domain work quality]

### Review Processes

[How to validate domain standards are being followed effectively]

### Success Metrics

[How to measure the effectiveness of domain guidance implementation]

## Integration with Kiro Workflow

### Requirements Clarification Enhancement

**How ${domain} guidance improves Stage 1:**
- [Specific way domain context enhances requirement generation]
- [Domain-specific requirement categories to consider]
- [Quality standards for ${domain}-related requirements]

### Design Document Enhancement

**How ${domain} guidance improves Stage 2:**
- [Specific way domain standards guide architectural decisions]
- [Domain-specific design patterns to apply]
- [Integration requirements for ${domain} components]

### Implementation Planning Enhancement

**How ${domain} guidance improves Stage 3:**
- [Specific way domain patterns influence task breakdown]
- [Domain-specific implementation sequence considerations]
- [Quality gates for ${domain}-related tasks]

### Task Execution Enhancement

**How ${domain} guidance improves Stage 4:**
- [Specific way domain standards guide coding decisions]
- [Domain-specific code quality requirements]
- [Validation criteria for ${domain} implementation quality]

## File Pattern Configuration

**Automatic Loading**: This domain steering automatically loads when working on files matching:

```

${domain-specific-file-patterns}

```

**Pattern Examples**:
- [Example file paths that trigger domain guidance loading]
- [Directory patterns where domain standards apply]
- [File naming conventions that activate domain guidance]

**Manual Loading**: Reference this steering in any context using `@${domain-name}` or by mentioning domain-specific needs.

## Scope Boundaries (Reasoning-Based)

### Domain Elements Included

**Standards Included**:
- [Standard 1] - Addresses specific pain point mentioned in user context
- [Standard 2] - Supports technology stack and tools user actually uses  
- [Standard 3] - Aligns with project goals and team capabilities provided

**Implementation guidance**: These standards were selected based on your specific context and needs, focusing on practical enhancement rather than theoretical best practices.

### Domain Elements NOT Included

**Standards NOT Included**:
- [Generic standard 1] - Not relevant to your specific technology choices
- [Over-complex standard 2] - Would add burden without validated benefit for your project
- [Speculative standard 3] - No indication this addresses your actual ${domain} challenges

**Reasoning**: Domain steering should enhance your actual workflow, not impose theoretical standards that don't match your project reality or team capabilities.

### Future Domain Considerations

- [Enhancement 1] - Could be valuable if project ${domain} requirements expand
- [Tool 2] - Monitor for potential integration if team capabilities grow
- [Standard 3] - Evaluate need if business requirements change

**Domain Philosophy**: Practical standards that solve actual ${domain} challenges for your specific project context.
```

</kiro_domain_steering_template>

[Generate actual comprehensive domain steering content based on all gathered context and domain expertise]

</domain_template_generation>

## 5. Quality Validation Framework

<domain_quality_validation>

**Before presenting the domain steering document, I'll systematically execute comprehensive quality validation checkpoints to ensure it meets all domain steering standards and provides genuine workflow enhancement value.**

**Executing domain steering quality validation checkpoints...**

### Document Structure Validation

- Check: `.kiro/steering/${domain-name}.md` created successfully
- Check: Frontmatter includes proper file pattern matching configuration
- Check: All 6 required sections present (Overview, Standards, Guidelines, Examples, Validation, Integration)
- Check: Document follows domain steering template structure  
- Check: File pattern configuration appropriate for domain type
- Check: Scope boundaries section documents domain decisions clearly

### Domain Content Validation

- Check: All provided user context incorporated into domain guidance
- Check: Domain-specific standards address user pain points and goals
- Check: Quality criteria specific to domain type and user requirements
- Check: Integration guidance covers all 4 workflow stages appropriately
- Check: Examples relevant to user's technology stack and context
- Check: Guidelines practical for user's team capabilities and project reality

### File Pattern Configuration Validation

- Check: fileMatchPattern appropriate for domain type (API, testing, security, etc.)
- Check: Pattern covers relevant file types and directory structures
- Check: Pattern examples help users understand when domain guidance applies
- Check: Manual loading options documented for flexible usage
- Check: Pattern integration tested with core steering system

### Workflow Integration Validation

- Check: Requirements stage enhancement clearly defined with domain-specific value
- Check: Design stage enhancement provides concrete architectural guidance
- Check: Implementation stage enhancement influences task planning appropriately  
- Check: Execution stage enhancement guides coding decisions with domain standards
- Check: Integration examples demonstrate practical application across workflow stages

### Domain Scope Discipline Validation

- Check: All domain elements trace to user-provided context or logical domain necessity
- Check: No generic best practices added beyond user's specific needs
- Check: Domain complexity appropriate for user's project scale and team capabilities
- Check: Scope boundaries document reasoning for inclusion/exclusion decisions clearly
- Check: Standards enhance rather than burden user's existing development process

### Core Steering Integration Validation

- Check: Domain steering complements rather than conflicts with core steering
- Check: Integration points with product, tech, and structure guidance clearly defined
- Check: Domain guidance enhances rather than duplicates core steering content
- Check: Conditional loading configured to work with existing steering system

<domain_validation_results>

**Quality Validation Results:**

**Domain Steering Quality Assessment:**

- **Structure Validation**: Perfect compliance with domain steering template structure
- **Content Quality**: All user context incorporated with domain-specific practical guidance
- **Pattern Configuration**: File matching patterns appropriate for ${domain-name} work detection
- **Workflow Integration**: All 4 workflow stages enhanced with concrete domain guidance
- **Scope Discipline**: Domain standards focused on user context, over-engineering avoided
- **Core Integration**: Domain steering enhances existing steering without conflicts

**Overall Quality Score: [Calculated based on validation results]**

</domain_validation_results>

</domain_quality_validation>

## 6. Domain Steering Review & Revision Cycle

<domain_review_cycle>

## Domain Steering Complete

I've generated comprehensive ${domain-name} domain steering following all established standards:

- **Context Integration**: All your provided ${domain-name} context incorporated into practical guidance
- **Workflow Enhancement**: Clear guidance for how domain standards improve all 4 workflow stages  
- **Pattern Configuration**: File matching setup for automatic loading during relevant work
- **Practical Focus**: Standards that enhance rather than burden your development process
- **Scope Discipline**: Domain guidance focused on your specific project needs and context

<domain_deliverables>

**Generated Document:**
**Location**: `.kiro/steering/${domain-name}.md`
**Quality Score**: [Score] (meeting all domain steering standards and practical focus)

[Display key domain guidance highlights and workflow integration benefits]

</domain_deliverables>

**Please review your ${domain-name} domain steering document.**

**Consider:**

- Do the domain standards address your specific pain points and goals effectively?
- Are the quality criteria appropriate for your project scale and team capabilities?
- Do the workflow integration examples show clear value for each stage?
- Are the file pattern matching configurations appropriate for your project structure?
- Do the guidelines provide practical guidance that enhances rather than burdens development?
- Are the scope boundaries correctly focused on your actual domain needs?

**Your options:**

- **Request Changes**: Tell me what needs to be modified, added, or refined
- **Adjust Standards**: Point out domain standards that need simplification or enhancement
- **Pattern Adjustments**: Modify file pattern matching for better automatic loading
- **Integration Refinements**: Adjust workflow stage integration guidance
- **Ready to Complete**: If satisfied, say "looks good", "approved", or "yes"

**What's your feedback?**

</domain_review_cycle>

[Handle user feedback and revision cycle]

---

### Revision Cycle (if changes requested)

[If user requests changes:]

1. **Analyze specific feedback** and identify areas for domain guidance modification
2. **Update ${domain-name}.md** with requested changes while maintaining template compliance and practical focus
3. **Re-run quality validation** to ensure all standards maintained including scope discipline
4. **Present updated version** for another review cycle with domain enhancement highlights
5. **Continue until explicit approval received**

## 7. Final Completion & Integration Guidance

<domain_integration_setup>

### Domain Steering Setup Complete

Thank you! Your ${domain-name} domain steering is now ready to enhance all Kiro workflow operations.

**Final Deliverables:**

- **Domain Steering Document**: `.kiro/steering/${domain-name}.md` (template-compliant with practical focus)
- **Automatic Loading**: File pattern configuration for relevant work detection
- **Workflow Integration**: Enhanced guidance for all 4 workflow stages  
- **Quality Standards**: Domain-specific quality criteria and validation methods

**How ${domain-name} Steering Enhances Your Workflow:**

### Requirements Clarification Enhancement

- **Domain Context**: ${domain-name} guidance provides specialized requirement categories
- **Quality Standards**: Domain-specific acceptance criteria and validation approaches
- **Integration Focus**: Requirements consider ${domain-name} constraints and opportunities

### Design Document Enhancement  

- **Architecture Guidance**: ${domain-name} patterns influence design decisions
- **Component Standards**: Domain-specific interface and integration requirements
- **Quality Patterns**: ${domain-name} best practices integrated into component design

### Implementation Planning Enhancement

- **Task Patterns**: ${domain-name} considerations influence task breakdown and sequencing
- **Quality Gates**: Domain-specific validation checkpoints in implementation sequence
- **Integration Planning**: ${domain-name} requirements integrated into task dependencies

### Task Execution Enhancement

- **Implementation Standards**: ${domain-name} coding standards guide development decisions
- **Quality Validation**: Domain-specific code quality and compliance verification
- **Integration Patterns**: ${domain-name} patterns applied during component development

**Immediate Benefits:**

- **Better Requirements**: ${domain-name} context improves requirement generation quality
- **Stronger Design**: Architecture decisions informed by ${domain-name} standards and constraints
- **Focused Implementation**: Tasks and code guided by domain-specific best practices
- **Quality Assurance**: ${domain-name} validation criteria integrated throughout workflow

### Usage and Integration

**Automatic Loading**:

Domain steering automatically loads when working on files matching your configured patterns:

```
${configured-file-patterns}
```

**Manual Loading**: Reference in any context using:

```
@${domain-name}
```

**Workflow Commands Integration**:

All workflow commands now enhanced with ${domain-name} guidance:

```
/kiro:2-requirements-clarification feature-name  # Enhanced with ${domain-name} context
/kiro:3-design-document-creation feature-name    # Enhanced with ${domain-name} standards  
/kiro:4-implementation-planning feature-name     # Enhanced with ${domain-name} patterns
/kiro:5-task-execution feature-name              # Enhanced with ${domain-name} quality criteria
```

**Domain Steering Maintenance:**

- **Update when domain needs evolve**: Modify ${domain-name}.md as project requirements change
- **Extend with new patterns**: Add new guidelines as team learns and grows
- **Review regularly**: Keep domain guidance current with technology and practice evolution
- **Share with team**: Domain steering improves consistency across team members

### Next Steps

**Your ${domain-name} domain steering is now active and enhancing your Kiro workflow!**

**Optional Enhancements:**

- **Add more domains**: Use `/kiro:0-steering-custom other-domain` for additional specializations
- **Refine patterns**: Adjust file matching patterns as you learn optimal trigger conditions  
- **Extend standards**: Add new ${domain-name} guidance as project needs evolve

**Test Integration**: Try running workflow commands on ${domain-name}-related features to see enhanced guidance in action.

**Kiro Custom Steering Creation Complete - Your Workflow Now Has Enhanced ${domain-name} Intelligence!**

</domain_integration_setup>
