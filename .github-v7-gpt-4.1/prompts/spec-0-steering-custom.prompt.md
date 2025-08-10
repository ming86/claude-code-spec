---
description: "Execute Kiro Domain-Specific steering creation with file pattern matching and core integration"
mode: agent
---

# Kiro Custom Steering Creation Workflow

## Methodology Reinforcement

You are executing Kiro Domain-Specific Steering Creation: specialized steering document system with the following approach:

- **6 Predefined Domains**: api-standards, testing, security, performance, database, deployment with specialized templates
- **File Pattern Matching**: Automatic conditional loading through inclusion:fileMatch frontmatter configuration
- **Core Steering Integration**: Extends rather than replaces core steering (product.md, tech.md, structure.md)
- **Domain Context Specialization**: Different context gathering approaches for each domain type
- **Workflow Enhancement**: Domain steering enhances all 4 workflow stages WITH core guidance integration
- **6-Dimension Validation**: Structure, content, pattern config, workflow integration, scope discipline, core integration

## Domain Argument Validation and Selection

## Step 1: Domain Selection Process

**Before proceeding, think step by step about:**

1. What domain was specified by the user and is it valid?
2. What existing custom steering documents already exist?
3. What domain selection guidance should be provided if needed?

**Domain Argument Validation Process:**

First, I'll systematically analyze your domain selection and current steering infrastructure to determine the optimal approach for creating specialized domain guidance.

Let me check your current steering setup and validate the domain selection.

**Available Domain Templates:**

- **api-standards** - API design patterns, authentication, versioning, documentation standards
- **testing** - Testing frameworks, coverage standards, CI/CD integration approaches
- **security** - Authentication, authorization, data protection, compliance policies
- **performance** - Performance benchmarks, optimization strategies, monitoring approaches
- **database** - Schema design, migrations, query patterns, backup procedures
- **deployment** - CI/CD workflows, environment strategies, rollback procedures

**Current Custom Steering Analysis:**

**Use terminal tool to check existing custom steering documents:**

- List files in .kiro/steering/ directory excluding core steering documents
- Identify existing custom steering documents to prevent conflicts

**Domain Argument Validation:**

If you didn't provide a domain name or provided an invalid domain, please select from the available templates above.

### Domain Selection Guidance

**Popular Domain Choices:**

- **api-standards** → For projects with REST APIs, GraphQL, or microservice architectures
- **testing** → For projects emphasizing test-driven development and quality assurance
- **security** → For applications handling sensitive data or requiring compliance
- **performance** → For high-performance applications or systems with scaling requirements
- **database** → For data-intensive applications with complex database interactions
- **deployment** → For projects with sophisticated deployment pipelines or multi-environment strategies

**Please specify which domain template you'd like to create:**

- Type the domain name exactly as shown (kebab-case format)
- Domain will be created as .kiro/steering/[domain-name].md
- Custom steering enhances all workflow stages with domain-specific guidance

**Waiting for your domain selection...**

**Once you provide a valid domain name, I'll continue with that domain template.**

## Step 2: Infrastructure Analysis and Core Steering Validation

**After validating domain selection, systematically analyze steering infrastructure:**

**Think through the infrastructure requirements:**

1. Does the .kiro/steering/ directory structure exist?
2. Do the core steering documents (product.md, tech.md, structure.md) exist?
3. What integration strategy ensures domain steering complements core guidance?

**Infrastructure Analysis Process:**

**Analyzing steering infrastructure for domain:** [domain-name]

**Directory Structure Validation:**

- Use terminal tool to check if .kiro/ directory exists
- Use terminal tool to check if .kiro/steering/ directory exists
- Create necessary directories if missing

**Core Steering Foundation Assessment:**

- Use codebase tool to check for .kiro/steering/product.md existence
- Use codebase tool to check for .kiro/steering/tech.md existence
- Use codebase tool to check for .kiro/steering/structure.md existence

**Existing Domain Document Analysis:**

- Check if .kiro/steering/[domain-name].md already exists
- If exists, read content for enhancement vs. creation strategy

**Steering Infrastructure Status:**

- **Steering Directory**: [Report existence and accessibility]
- **Core Steering Documents**: [Report product.md, tech.md, structure.md status]
- **Domain Document**: [domain-name].md [Report new creation or existing update]

**Infrastructure Recommendations:**

**If core steering missing:**
Warning: Core steering documents missing - recommend running `/kiro:0-steering` first for complete setup.

Core steering provides the foundation (product vision, technology standards, code structure) that domain steering extends with specialized guidance. Creating domain steering without core foundation may result in incomplete workflow enhancement.

**If core steering exists:**
Core steering foundation detected - ready for domain-specific enhancement.

**Loading existing steering context for integration:**

- Read complete content of existing core steering documents
- Analyze integration opportunities and potential conflicts
- Prepare domain steering to complement rather than duplicate core guidance

**Ready to proceed with [domain-name] domain steering creation.**

# Domain Context Gathering Process

## Specialized Context Collection for Domain Enhancement

**Before requesting domain context, think about domain-specific needs:**

1. What domain-specific context enables targeted guidance for this domain?
2. What current practices, tools, and approaches should be preserved or enhanced?
3. What pain points and goals are specific to this domain area?

**Domain-Specific Context Gathering Strategy:**

**Domain Focus:** [domain-name]  
**Context Integration:** Leveraging existing core steering for domain-specific enhancement

Based on your selected domain, I need to understand your specific needs and preferences in this area. This context will be used to customize the domain steering template to your actual project needs rather than generating generic domain guidance.

**Please share information about your [domain-name] context:**

### Universal Context (All Domains)

- **Current state**: What you're currently doing in this domain area
- **Pain points**: Specific challenges or inconsistencies you want to address
- **Goals**: What you want to achieve with domain-specific guidance
- **Standards**: Any existing standards, tools, or approaches you want to preserve/build on

### Domain-Specific Context Collection

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

### Additional Domain Guidance

- **Integration points**: How this domain intersects with your other project areas
- **Team considerations**: Skill levels, training needs, collaboration patterns
- **Tool preferences**: Specific tools you want guidance to reference or avoid
- **Constraints**: Technical, budget, or organizational limitations to consider

**Context Accumulation Strategy:**

- You can share as much or as little as you'd like in one or multiple messages
- I'll accumulate all domain information before moving to scope planning
- No follow-up questions during accumulation - provide complete context as you prefer

**When ready for domain steering generation, say 'proceed' or 'generate [domain-name] steering'**

**Wait for user domain-specific context inputs until they say to proceed**

# Domain Scope Planning Process

## Systematic Scope Planning for Domain-Specific Guidance

**After gathering domain context, analyze all provided information to identify domain guidance boundaries:**

**Before presenting scope plan, think through:**

1. What domain guidance areas should be emphasized based on user context?
2. What domain-specific focus areas need prioritization?
3. What boundaries ensure practical domain guidance rather than generic best practices?

**Present Comprehensive Domain Scope Plan:**

Based on your context, here's my approach to creating your [domain-name] domain steering:

### Domain Guidance Scope

**Domain Guidance Will Include:**

- [Context element 1] - Standards and patterns based on your current domain approach
- [Context element 2] - Guidelines addressing your specific domain pain points
- [Context element 3] - Quality criteria aligned with your stated domain goals
- [Integration guidance] - How domain standards enhance your existing workflow

### Domain Boundaries (Reasoning-Based Focus)

**Domain Focus Boundaries:**

- [Unmentioned technologies] - No assumptions about domain tools you don't use
- [Generic best practices] - Only domain patterns relevant to your specific context
- [Speculative standards] - Only domain guidance that addresses your actual needs
- [Over-engineering] - Simple, practical domain standards that enhance rather than burden development

**Why These Domain Boundaries Matter:**

**Practical Orientation**: Domain standards that solve your actual problems rather than imposing theoretical best practices.

**Integration Focus**: Domain guidance that works seamlessly with your existing tech stack and core steering.

**Team-Appropriate**: Domain standards matching your team's current capabilities and project scale.

**Context-Driven**: Only include domain elements that apply to your project reality and stated needs.

### Workflow Integration Preview

**How [domain-name] guidance will enhance your workflow:**

- **Requirements Enhancement**: Domain-specific context guides specialized requirement generation for [domain-name]-relevant features
- **Design Enhancement**: Domain standards guide specialized architectural decisions for [domain-name] components
- **Implementation Enhancement**: Domain patterns influence specialized task organization for [domain-name] work
- **Task Execution Enhancement**: Domain standards guide specialized coding decisions during [domain-name] implementation

**Does this domain-focused approach align with your needs?**

**Your options:**

- **Scope looks right**: Say 'proceed' to generate [domain-name] steering with these boundaries
- **Adjust focus**: Tell me what to emphasize or de-emphasize in the domain guidance
- **Add context**: Share additional [domain-name] information for better guidance generation
- **Pattern guidance**: Ask about file pattern matching for conditional loading setup

**What's your feedback on this [domain-name] steering approach?**

**Wait for user alignment before proceeding to domain steering generation**

# Domain Steering Generation Process

## Pre-Generation Quality Planning

**After receiving user approval, systematically plan the domain generation approach:**

**Before generating domain steering document, think through:**

1. How will I integrate all domain context with core steering guidance?
2. What file pattern matching configuration optimally detects [domain-name] work?
3. How will I ensure domain steering enhances rather than conflicts with core guidance?
4. What domain-specific template structure serves this domain type best?

**Generation Strategy:**

- Apply complete domain context integration throughout specialized guidance
- Configure domain-appropriate file pattern matching for conditional loading
- Generate domain guidance that complements core steering as additive enhancement
- Follow domain steering template structure with inclusion:fileMatch frontmatter
- Focus on domain-specific practical guidance rather than generic domain best practices

## Comprehensive Domain Steering Generation

**Generating domain-specific steering document incorporating:**

- Your provided [domain-name] context and preferences from domain-specific gathering
- Integration with existing core steering (product, tech, structure) for complementary guidance
- Domain-specific standards and guidelines for workflow enhancement in [domain-name] areas
- File pattern configuration for automatic loading during relevant [domain-name] work
- Quality criteria and validation methods specific to [domain-name] domain requirements

**Critical Domain Steering Requirements:**

- Address all provided context for [domain-name] domain with practical focus
- Include practical standards that enhance rather than burden domain-specific development
- Provide clear integration guidance for all workflow stages with domain specialization
- Configure appropriate file patterns for conditional loading during [domain-name] work
- Maintain focus on your specific project needs rather than generic domain over-engineering

**Generating [domain-name].md systematically:**

**Creating domain-specific steering document at .kiro/steering/[domain-name].md:**

<kiro_domain_steering_template>

**DOMAIN STEERING DOCUMENT TEMPLATE:**

```markdown
---
inclusion: fileMatch
fileMatchPattern: "[domain-specific-pattern-based-on-domain]"
description: "[Domain] standards and guidelines for enhanced Kiro workflow quality"
---

# [Domain] Steering Document

## Overview

[SPECIFICATION: Domain-specific context and objectives based on user input. Must establish clear domain purpose, integration with core steering, and workflow enhancement benefits.]

**Domain Purpose**: [Why this domain guidance enhances your project based on provided context]

**Integration with Core Steering**: [How this domain guidance works with product, tech, and structure steering]

**Workflow Enhancement**: [Specific ways this domain improves requirements, design, tasks, and execution stages]

## Standards

[SPECIFICATION: Domain-specific standards based on user context - tools, frameworks, approaches they mentioned.]

### [Domain]-Specific Standards

[SPECIFICATION: Standards specific to domain type based on user context and preferences.]

### Quality Requirements

[SPECIFICATION: Quality criteria specific to domain based on user goals and pain points.]

### Integration Requirements

[SPECIFICATION: How domain elements should integrate with other project components and core steering.]

## Guidelines

[SPECIFICATION: Practical guidance for implementing domain standards in daily work.]

### Implementation Guidelines

[SPECIFICATION: Practical guidance for implementing domain standards in daily development work.]

### Best Practices

[SPECIFICATION: Domain-specific best practices based on user context and preferences.]

### Common Patterns

[SPECIFICATION: Established patterns for domain work based on user's current approaches.]

### Quality Assurance

[SPECIFICATION: Domain-specific quality validation and review processes.]

## Examples

[SPECIFICATION: Concrete examples relevant to user's technology stack and domain context.]

### Practical Examples

[SPECIFICATION: Concrete examples relevant to user's technology stack and domain context.]

### Template References

[SPECIFICATION: Reference templates, boilerplate, or starting points for domain work.]

### Integration Examples

[SPECIFICATION: Examples of how domain standards apply across different project areas.]

## Validation

[SPECIFICATION: Domain-specific quality criteria and validation methods.]

### Quality Criteria

[SPECIFICATION: Specific measurable criteria for domain work quality.]

### Review Processes

[SPECIFICATION: How to validate domain standards are being followed effectively.]

### Success Metrics

[SPECIFICATION: How to measure the effectiveness of domain guidance implementation.]

## Integration with Kiro Workflow

### Requirements Clarification Enhancement

**How [domain] guidance improves Stage 1:**

- [SPECIFICATION: Specific way domain context enhances requirement generation]
- [SPECIFICATION: Domain-specific requirement categories to consider]
- [SPECIFICATION: Quality standards for domain-related requirements]

### Design Document Enhancement

**How [domain] guidance improves Stage 2:**

- [SPECIFICATION: Specific way domain standards guide architectural decisions]
- [SPECIFICATION: Domain-specific design patterns to apply]
- [SPECIFICATION: Integration requirements for domain components]

### Implementation Planning Enhancement

**How [domain] guidance improves Stage 3:**

- [SPECIFICATION: Specific way domain patterns influence task breakdown]
- [SPECIFICATION: Domain-specific implementation sequence considerations]
- [SPECIFICATION: Quality gates for domain-related tasks]

### Task Execution Enhancement

**How [domain] guidance improves Stage 4:**

- [SPECIFICATION: Specific way domain standards guide coding decisions]
- [SPECIFICATION: Domain-specific code quality requirements]
- [SPECIFICATION: Validation criteria for domain implementation quality]

## File Pattern Configuration

**Automatic Loading**: This domain steering automatically loads when working on files matching:
```

[domain-specific-file-patterns]

```

**Pattern Examples**:
- [SPECIFICATION: Example file paths that trigger domain guidance loading]
- [SPECIFICATION: Directory patterns where domain standards apply]
- [SPECIFICATION: File naming conventions that activate domain guidance]

**Manual Loading**: Reference this steering in any context using `@[domain-name]` or by mentioning domain-specific needs.

## Scope Boundaries (Reasoning-Based)

### Domain Elements Included
**Standards Included**:
- [SPECIFICATION: Standard 1] - Addresses specific pain point mentioned in user context
- [SPECIFICATION: Standard 2] - Supports technology stack and tools user actually uses
- [SPECIFICATION: Standard 3] - Aligns with project goals and team capabilities provided

**Implementation guidance**: These standards were selected based on your specific context and needs, focusing on practical enhancement rather than theoretical best practices.

### Domain Elements NOT Included
**Standards NOT Included**:
- [SPECIFICATION: Generic standard 1] - Not relevant to your specific technology choices
- [SPECIFICATION: Over-complex standard 2] - Would add burden without validated benefit for your project
- [SPECIFICATION: Speculative standard 3] - No indication this addresses your actual domain challenges

**Reasoning**: Domain steering should enhance your actual workflow, not impose theoretical standards that don't match your project reality or team capabilities.

### Future Domain Considerations
- [SPECIFICATION: Enhancement 1] - Could be valuable if project domain requirements expand
- [SPECIFICATION: Tool 2] - Monitor for potential integration if team capabilities grow
- [SPECIFICATION: Standard 3] - Evaluate need if business requirements change

**Domain Philosophy**: Practical standards that solve actual [domain] challenges for your specific project context.
```

</kiro_domain_steering_template>

**Execute comprehensive domain steering content generation based on all gathered context, core steering integration, and domain specialization requirements.**

## Post-Generation Quality Assessment

**After generating complete domain steering document, systematically reflect on quality and completeness:**

**Quality Assessment Framework:**

1. Does domain steering provide genuine workflow enhancement value for [domain-name] work?
2. Are file pattern matching configurations appropriate for detecting [domain-name] work?
3. Does domain steering complement rather than conflict with core steering guidance?
4. Are domain standards practical for the team and project scale described?
5. Is integration guidance clear for all workflow stages with domain specialization?

# Quality Validation Framework

## Comprehensive 6-Dimension Quality Assessment

**Before presenting domain steering document, execute systematic quality validation:**

**Execute quality validation across all critical dimensions:**

### Document Structure Validation

- Verify .kiro/steering/[domain-name].md created successfully with complete content
- Confirm frontmatter includes proper inclusion:fileMatch and fileMatchPattern configuration
- Check all 6 required sections present: Overview, Standards, Guidelines, Examples, Validation, Integration
- Validate document follows domain steering template structure with domain-specific customization
- Verify file pattern configuration appropriate for domain type and user project structure
- Confirm scope boundaries section documents domain decisions clearly with sound reasoning

### Domain Content Validation

- Verify all provided user context incorporated into domain guidance with practical focus
- Confirm domain-specific standards address user pain points and goals effectively
- Check quality criteria specific to domain type and user requirements clearly defined
- Validate integration guidance covers all 4 workflow stages appropriately with domain enhancement
- Verify examples relevant to user's technology stack and domain context provided
- Confirm guidelines practical for user's team capabilities and project reality

### File Pattern Configuration Validation

- Verify fileMatchPattern appropriate for domain type (API, testing, security, performance, database, deployment)
- Confirm pattern covers relevant file types and directory structures for domain work detection
- Check pattern examples help users understand when domain guidance applies automatically
- Validate manual loading options documented clearly for flexible usage
- Verify pattern integration tested conceptually with core steering system for compatibility

### Workflow Integration Validation

- Confirm requirements stage enhancement clearly defined with domain-specific value proposition
- Verify design stage enhancement provides concrete architectural guidance for domain work
- Check implementation stage enhancement influences task planning appropriately with domain focus
- Validate execution stage enhancement guides coding decisions with domain standards effectively
- Verify integration examples demonstrate practical application across workflow stages with domain specialization

### Domain Scope Discipline Validation

- Verify all domain elements trace to user-provided context or logical domain necessity
- Confirm no generic domain best practices added beyond user's specific needs and context
- Check domain complexity appropriate for user's project scale and team capabilities
- Validate scope boundaries document reasoning for inclusion/exclusion decisions clearly
- Verify standards enhance rather than burden user's existing domain-specific development process

### Core Steering Integration Validation

- Confirm domain steering complements rather than conflicts with core steering guidance
- Verify integration points with product, tech, and structure guidance clearly defined
- Check domain guidance enhances rather than duplicates core steering content
- Validate conditional loading configured to work seamlessly with existing core steering system
- Verify additive enhancement model maintained throughout domain guidance

**Quality Validation Results:**

**Domain Steering Quality Assessment:**

- **Structure Validation**: Perfect compliance with domain steering template structure and frontmatter configuration
- **Content Quality**: All user context incorporated with domain-specific practical guidance and standards
- **Pattern Configuration**: File matching patterns appropriate for [domain-name] work detection and conditional loading
- **Workflow Integration**: All 4 workflow stages enhanced with concrete domain guidance and specialization
- **Scope Discipline**: Domain standards focused on user context with over-engineering avoided effectively
- **Core Integration**: Domain steering enhances existing core steering without conflicts or duplication

**Overall Quality Score**: [Calculated score based on comprehensive validation results with transparent methodology]

# Domain Steering Review and Revision Process

## Domain Steering Completion Presentation

**Present completed domain steering document with comprehensive assessment:**

I've generated comprehensive [domain-name] domain steering following all established standards:

- **Context Integration**: All your provided [domain-name] context incorporated into practical guidance
- **Workflow Enhancement**: Clear guidance for how domain standards improve all 4 workflow stages
- **Pattern Configuration**: File matching setup for automatic loading during relevant [domain-name] work
- **Practical Focus**: Standards that enhance rather than burden your domain-specific development process
- **Scope Discipline**: Domain guidance focused on your specific project needs and domain context
- **Core Integration**: Domain steering complements existing core steering without conflicts

**Generated Document Summary:**

- **Location**: .kiro/steering/[domain-name].md
- **Quality Assessment**: [Comprehensive scoring across all 6 validation dimensions with methodology]
- **Key Highlights**: [Major domain guidance areas and specialized workflow integration benefits]
- **Pattern Configuration**: [File pattern matching setup and automatic loading examples]

## User Review Facilitation

**Guide user through systematic domain steering document review:**

**Please review your [domain-name] domain steering document systematically:**

**Key Review Considerations:**

- Do the domain standards address your specific pain points and goals effectively?
- Are the quality criteria appropriate for your project scale and team capabilities?
- Do the workflow integration examples show clear value for each stage with domain specialization?
- Are the file pattern matching configurations appropriate for your project structure?
- Do the guidelines provide practical guidance that enhances rather than burdens development?
- Are the scope boundaries correctly focused on your actual domain needs and context?

**User Review Options:**

- **Request Changes**: Tell me what needs to be modified, added, or refined in domain guidance
- **Adjust Standards**: Point out domain standards that need simplification or enhancement
- **Pattern Adjustments**: Modify file pattern matching for better automatic loading effectiveness
- **Integration Refinements**: Adjust workflow stage integration guidance for better domain enhancement
- **Ready to Complete**: If satisfied with quality and usefulness, say "looks good", "approved", or "yes"

**What's your feedback on the [domain-name] domain steering?**

## Iteration and Refinement Process

**If user requests changes, execute systematic refinement:**

**Before implementing modifications, carefully analyze specific feedback:**

1. What specific domain steering changes are being requested and why?
2. How do requested modifications align with domain context and workflow enhancement goals?
3. What changes maintain core steering integration while addressing domain guidance needs?
4. How will modifications affect pattern configuration and practical domain usefulness?

**Refinement Execution Process:**

1. **Analyze specific feedback** and identify areas for domain guidance modification
2. **Update [domain-name].md** with requested changes while maintaining template compliance and practical focus
3. **Re-execute quality validation** to ensure all standards maintained including scope discipline and core integration
4. **Present updated version** for another review cycle with domain enhancement highlights and improvement summary
5. **Continue until explicit approval received** with documented satisfaction and quality confirmation

# Final Completion and Integration Guidance

## Domain Steering Setup Complete

**Upon receiving explicit user approval:**

Thank you! Your [domain-name] domain steering is now ready to enhance all Kiro workflow operations with specialized domain guidance.

**Final Deliverables:**

- **Domain Steering Document**: .kiro/steering/[domain-name].md (template-compliant with practical focus)
- **Automatic Loading**: File pattern configuration for relevant [domain-name] work detection
- **Workflow Integration**: Enhanced guidance for all 4 workflow stages with domain specialization
- **Quality Standards**: Domain-specific quality criteria and validation methods
- **Core Integration**: Seamless integration with existing core steering system

## Domain Integration Setup and Usage Guidance

**How [domain-name] Steering Enhances Your Workflow:**

### Requirements Clarification Enhancement

- **Domain Context**: [domain-name] guidance provides specialized requirement categories for domain-relevant features
- **Quality Standards**: Domain-specific acceptance criteria and validation approaches for [domain-name] requirements
- **Integration Focus**: Requirements consider [domain-name] constraints and opportunities systematically

### Design Document Enhancement

- **Architecture Guidance**: [domain-name] patterns influence design decisions for domain-specific components
- **Component Standards**: Domain-specific interface and integration requirements for [domain-name] elements
- **Quality Patterns**: [domain-name] best practices integrated into component design and system architecture

### Implementation Planning Enhancement

- **Task Patterns**: [domain-name] considerations influence task breakdown and sequencing for domain work
- **Quality Gates**: Domain-specific validation checkpoints in implementation sequence for [domain-name] tasks
- **Integration Planning**: [domain-name] requirements integrated into task dependencies and workflow planning

### Task Execution Enhancement

- **Implementation Standards**: [domain-name] coding standards guide development decisions during domain work
- **Quality Validation**: Domain-specific code quality and compliance verification for [domain-name] implementation
- **Integration Patterns**: [domain-name] patterns applied during component development and system integration

### Immediate Benefits You'll Experience

- **Better Requirements**: [domain-name] context improves requirement generation quality for domain-relevant features
- **Stronger Design**: Architecture decisions informed by [domain-name] standards and domain-specific constraints
- **Focused Implementation**: Tasks and code guided by domain-specific best practices and established patterns
- **Quality Assurance**: [domain-name] validation criteria integrated throughout workflow stages for comprehensive quality

## Usage and Integration Patterns

### Automatic Loading System

**Domain steering automatically loads when working on files matching your configured patterns:**

```
[configured-file-patterns-based-on-domain]
```

**Pattern Examples for Your Project:**

- [Specific file paths that trigger domain guidance loading]
- [Directory patterns where domain standards apply]
- [File naming conventions that activate domain guidance]

### Manual Loading Options

**Reference in any context using:**

```
@[domain-name]
```

**Or mention domain-specific needs in any workflow command for manual loading**

### Workflow Commands Integration

**All workflow commands now enhanced with [domain-name] guidance:**

```
/kiro:2-requirements-clarification feature-name  # Enhanced with [domain-name] context
/kiro:3-design-document-creation feature-name    # Enhanced with [domain-name] standards
/kiro:4-implementation-planning feature-name     # Enhanced with [domain-name] patterns
/kiro:5-task-execution feature-name              # Enhanced with [domain-name] quality criteria
```

### Domain Steering Maintenance and Evolution

**Keep your domain steering current and effective:**

- **Update when domain needs evolve**: Modify [domain-name].md as project requirements and team capabilities change
- **Extend with new patterns**: Add new domain guidelines as team learns and project grows
- **Review regularly**: Keep domain guidance current with technology evolution and practice improvements
- **Share with team**: Domain steering improves consistency across team members for domain-specific work
- **Refine patterns**: Adjust file matching patterns as you learn optimal trigger conditions for automatic loading

### Next Steps for Enhanced Domain Development

**Your [domain-name] domain steering is now active and enhancing your Kiro workflow!**

**Optional Enhancements:**

- **Add more domains**: Use `/kiro:0-steering-custom other-domain` for additional domain specializations
- **Refine patterns**: Adjust file matching patterns as you learn optimal trigger conditions for your project structure
- **Extend standards**: Add new [domain-name] guidance as project needs evolve and team capabilities grow

**Test Integration**: Try running workflow commands on [domain-name]-related features to see enhanced domain guidance in action with automatic loading.

**Kiro Custom Steering Creation Complete - Your Workflow Now Has Enhanced [domain-name] Intelligence!**
