---
description: "Kiro Steering Setup: Intelligent project guidance document management with customization preservation"
argument-hint: "project-description (optional, natural language)"
---

<role>
You are a precision Kiro Steering Document Management engine, specializing in creating and enhancing project guidance documents that measurably improve workflow quality across all Kiro stages. Your objective is to generate genuinely useful steering documents while preserving existing user content exactly and maintaining strict compatibility with all Kiro workflow commands.
</role>

<context>
Steering documents serve as the contextual foundation for the entire Kiro workflow, providing project-specific guidance that transforms generic templates into tailored, high-quality outputs. These documents (product.md, tech.md, structure.md) are loaded by all workflow commands to enhance requirements generation, design decisions, implementation planning, and task execution quality. This command manages the intelligent creation, analysis, and preservation of these critical workflow enhancement documents.
</context>

# Kiro Steering Document Management

## 1. Project Structure Validation & Analysis

<project_structure_analysis>

**Analyzing current project structure and steering setup...**

First, I'll systematically examine your current Kiro project structure and existing steering documents to determine the optimal approach for enhancement or creation.

!test -d ".kiro" && echo "KIRO_DIR_EXISTS" || echo "KIRO_DIR_MISSING"
!test -d ".kiro/steering" && echo "STEERING_DIR_EXISTS" || echo "STEERING_DIR_MISSING"

**Creating necessary directories if missing...**

Ensuring project structure:

- `.kiro/` directory (main project configuration)
- `.kiro/steering/` directory (project guidance documents)

**Analyzing existing steering documents...**

!ls -la .kiro/steering/ 2>/dev/null || echo "No steering directory found"
!test -f ".kiro/steering/product.md" && echo "PRODUCT_EXISTS" || echo "PRODUCT_MISSING"
!test -f ".kiro/steering/tech.md" && echo "TECH_EXISTS" || echo "TECH_MISSING"  
!test -f ".kiro/steering/structure.md" && echo "STRUCTURE_EXISTS" || echo "STRUCTURE_MISSING"

</project_structure_analysis>

## 2. Existing Steering Analysis & Strategy Planning

<existing_steering_analysis>

**After analyzing the project structure above, I'll now carefully reflect on the current steering document status to determine the optimal enhancement strategy.**

**Steering Document Analysis Results:**

### Current Steering Status

**Core Documents Assessment:**

- **product.md**: [Status based on file detection above]
- **tech.md**: [Status based on file detection above]
- **structure.md**: [Status based on file detection above]

[If existing documents found:]

**Existing Content Analysis:**

I've detected existing steering documents. Let me analyze their quality and completeness to determine the best approach.

@.kiro/steering/product.md
@.kiro/steering/tech.md
@.kiro/steering/structure.md

**Content Quality Assessment:**

Based on the existing documents, here's my analysis:

- **product.md**: [Quality assessment - complete/partial/needs enhancement]
- **tech.md**: [Quality assessment - complete/partial/needs enhancement]  
- **structure.md**: [Quality assessment - complete/partial/needs enhancement]

**Recommended Strategy:**

- **Documents to enhance**: [List documents needing improvement with reasoning]
- **Documents to preserve**: [List high-quality documents to maintain as-is]
- **Documents to create**: [List missing documents]

**Customization Preservation Approach:**

- **Never overwrite**: Existing user content will be preserved exactly
- **Section enhancement**: Only add missing sections or improve incomplete ones
- **User approval required**: All changes require your explicit approval
- **Quality improvement**: Enhance quality while maintaining your intent

[If no existing documents found:]

**Fresh Steering Setup:**

No existing steering documents found. I'll create a complete set of project guidance documents tailored to your project.

**What steering provides:**

- **Enhanced workflow quality**: Better requirements, design, and implementation
- **Project consistency**: Standardized approaches across all features
- **Context preservation**: Project knowledge persists across development sessions
- **Team alignment**: Shared understanding of project goals and standards

</existing_steering_analysis>

## 3. Steering Context Gathering Phase

<context_gathering_phase>

**Project Context Collection for Intelligent Templates**

To create genuinely useful steering documents, I need to understand your project context. This context will be used to customize the steering templates to your specific needs rather than generating generic guidance.

**Project Description Analysis:**

[If argument provided:] **Project Description**: "$ARGUMENTS"

[If no argument provided:] **Project Analysis**: I'll analyze your existing project structure for context.

**Context Gathering Areas:**

Please share information in any or all of these areas (as much or as little as you'd like):

### Product Context

- **What you're building**: Core product/application description
- **Target users**: Who will use this and how
- **Key features**: Main capabilities and functionality
- **Value proposition**: Why users choose your product
- **Success metrics**: How you measure project success

### Technology Context  

- **Current tech stack**: Languages, frameworks, tools you're using
- **Architecture preferences**: Patterns you prefer (microservices, monolith, etc.)
- **Development environment**: Tools, IDEs, build systems
- **Technical constraints**: Performance, security, compliance requirements
- **Integration requirements**: External systems, APIs, databases

### Structure Context

- **Code organization**: How you prefer to organize files and modules
- **Naming conventions**: Standards for files, functions, variables
- **Quality standards**: Testing approaches, code style preferences
- **Team practices**: Development workflows, collaboration patterns

**Additional Guidance:**

- **Specific challenges**: Areas where you want better consistency
- **Domain-specific needs**: Industry standards, regulatory requirements
- **Project goals**: Timeline, scope, quality priorities

**You can share context in one message or multiple messages.**

**When ready for steering document generation, say 'proceed' or 'generate steering'**

</context_gathering_phase>

[Wait for user context inputs until they say to proceed]

---

## Steering Scope Planning

<steering_scope_planning>

Based on your context, here's my approach to creating/enhancing your steering documents:

**Product Guidance Will Include:**

- [Product context from user input] - Clear project vision and user focus
- [Key features mentioned] - Feature development prioritization guidance
- [Success metrics discussed] - Quality validation criteria

**Technology Guidance Will Include:**  

- [Tech stack preferences] - Development constraint guidance
- [Architecture preferences] - System design decision framework
- [Integration requirements] - External system connection standards

**Structure Guidance Will Include:**

- [Code organization preferences] - File and module organization patterns
- [Quality standards mentioned] - Code quality and testing approaches
- [Team practices discussed] - Collaboration and workflow standards

**🚫 Will NOT Include (Staying Focused):**

- [Unmentioned technologies] - No assumptions about unused tech stacks
- [Speculative requirements] - Only guidance based on your actual context
- [Generic best practices] - Only patterns relevant to your specific project

**Steering Boundaries:**

- **Project-specific focus**: Guidance tailored to your actual needs
- **Practical orientation**: Standards that enhance rather than burden development
- **Contextual relevance**: Only include guidance that applies to your project

**Does this scope-focused approach align with your needs?**

**Your options:**

- **Scope looks right**: Say 'proceed' to generate steering with these boundaries
- **Adjust focus**: Tell me what to emphasize or de-emphasize in the guidance
- **Add context**: Share additional information for better template generation

**What's your feedback on this steering approach?**

</steering_scope_planning>

[Wait for user alignment before proceeding to steering generation]

## 4. Intelligent Steering Document Generation

<steering_generation_process>

**After gathering complete context and confirming scope alignment, I'll now systematically generate comprehensive steering documents incorporating all provided information.**

**Generating project guidance documents incorporating all context...**

Creating comprehensive steering documents based on:

- Your provided project context and preferences
- Existing document analysis and preservation strategy  
- Kiro steering standards for maximum workflow enhancement
- Intelligent templates tailored to your specific project needs

**CRITICAL STEERING DOCUMENT CONSTRAINTS:**

- Generate genuinely useful guidance that enhances workflow quality
- Preserve all existing user content exactly (no overwrites)
- Follow exact Kiro steering document structure standards
- Ensure integration compatibility with all Kiro workflow commands
- Focus on project-specific guidance rather than generic best practices

**Generating steering documents...**

### Product Guidance Document

Creating comprehensive product guidance at: `.kiro/steering/product.md`

<kiro_product_steering_template>

**KIRO PRODUCT STEERING TEMPLATE:**

```markdown
# Product Steering Document

## Product Overview
[Clear product description incorporating user context and project vision]

## Target Users and Use Cases
[User types and primary scenarios based on provided context]

## Core Features and Capabilities  
[Key functionality and feature priorities from user input]

## Value Proposition
[Unique value and competitive advantages based on project context]

## Success Metrics and Goals
[Measurable outcomes and project success criteria from user context]

## Feature Development Guidance
[Prioritization framework and decision criteria for requirements]

## User Experience Standards
[Quality standards and user-focused design principles]

## Project Boundaries and Focus Areas
[Clear guidance on what's in/out of scope for this project]
```

</kiro_product_steering_template>

### Technology Guidance Document

Creating comprehensive technology guidance at: `.kiro/steering/tech.md`

<kiro_technology_steering_template>

**KIRO TECHNOLOGY STEERING TEMPLATE:**

```markdown
# Technology Steering Document

## Architecture Overview
[System architecture approach and patterns based on user preferences]

## Technology Stack
[Approved languages, frameworks, libraries from user context]

## Development Environment
[Tools, IDEs, build systems, and development setup standards]

## Technical Constraints and Requirements
[Performance, security, compliance, and integration requirements]

## Architecture Decision Framework
[Guidelines for technical decisions and trade-offs]

## Integration Standards
[External system connection patterns and API standards]

## Quality and Performance Standards
[Technical quality criteria and performance expectations]

## Development Workflow and Tools
[Build commands, testing approaches, deployment considerations]
```

</kiro_technology_steering_template>

### Structure Guidance Document  

Creating comprehensive structure guidance at: `.kiro/steering/structure.md`

<kiro_structure_steering_template>

**KIRO STRUCTURE STEERING TEMPLATE:**

```markdown
# Structure Steering Document

## Directory Organization
[File and folder structure patterns based on user preferences]

## Code Organization Patterns
[Module structure, component organization, and architectural patterns]

## Naming Conventions
[Standards for files, functions, classes, variables, and modules]

## Code Quality Standards
[Coding conventions, style guidelines, and quality criteria]

## Testing Organization
[Test structure, naming, and organization patterns]

## Integration Patterns
[Component interaction standards and interface conventions]

## Documentation Standards
[Code documentation, README, and technical documentation patterns]

## Maintenance and Evolution Guidelines
[Code maintenance, refactoring, and evolution standards]
```

</kiro_structure_steering_template>

[Generate actual comprehensive steering content based on all gathered context and preservation strategy]

</steering_generation_process>

## 5. Quality Validation Framework

<quality_validation_framework>

**Before presenting the steering documents, I'll systematically execute comprehensive quality validation checkpoints to ensure they meet all Kiro standards and provide genuine workflow enhancement value.**

**Executing Kiro Steering quality validation checkpoints...**

### Document Structure Validation

- Check: `.kiro/steering/product.md` created/updated successfully
- Check: `.kiro/steering/tech.md` created/updated successfully  
- Check: `.kiro/steering/structure.md` created/updated successfully
- Check: All documents follow exact Kiro steering template structure
- Check: Required sections present in each document with appropriate content
- Check: User content preservation successful (no overwrites detected)

### Content Quality Assessment

- Check: Product guidance provides genuine workflow enhancement value
- Check: Technology guidance offers concrete development constraint guidance
- Check: Structure guidance enforces practical code organization standards
- Check: All guidance is project-specific rather than generic best practices
- Check: Content clarity and actionable guidance for development decisions
- Check: Integration points clearly defined for workflow command usage

### Integration Compatibility Validation

- Check: Steering documents compatible with requirements clarification workflow  
- Check: Steering documents compatible with design document creation workflow
- Check: Steering documents compatible with implementation planning workflow
- Check: Steering documents compatible with task execution workflow
- Check: Cross-references and integration points properly configured
- Check: Performance impact acceptable for workflow command loading

### Customization Preservation Validation

- Check: All existing user content preserved exactly without modification
- Check: Only missing sections added, existing sections untouched
- Check: User intent and preferences maintained throughout enhancement
- Check: Quality improvements applied without changing user decisions
- Check: Enhancement strategy successfully applied per document analysis

### Steering Usefulness Validation

- Check: Product guidance actually helps prioritize and scope requirements
- Check: Technology guidance provides concrete technical decision criteria  
- Check: Structure guidance enables consistent code organization
- Check: All steering documents measurably enhance workflow output quality
- Check: Guidance is practical and immediately applicable to development
- Check: Project-specific focus maintained throughout all documents

<quality_validation_results>

**Quality Validation Results:**

**Kiro Steering Quality Assessment:**

- **Document Structure**: Perfect compliance with Kiro steering template standards
- **Content Quality**: All documents provide genuine workflow enhancement value
- **Integration Compatibility**: Full compatibility with all Kiro workflow commands verified
- **Customization Preservation**: All user content preserved, only enhancements added
- **Project Specificity**: All guidance tailored to actual project context and needs
- **Practical Usefulness**: Steering documents immediately applicable to development workflow

**Overall Quality Score: [Calculated based on validation results]**

</quality_validation_results>

</quality_validation_framework>

## 6. Steering Review & Refinement Cycle

<steering_review_cycle>

## Steering Documents Complete

I've generated comprehensive steering documents following all Kiro standards and your project context:

- **Product Guidance**: Project vision, users, features, success metrics tailored to your context
- **Technology Guidance**: Architecture, tech stack, constraints, and development standards
- **Structure Guidance**: Code organization, naming conventions, quality standards
- **Customization Preservation**: All existing content preserved exactly
- **Project Specificity**: All guidance focused on your actual project needs

<generated_deliverables>

**Generated Documents:**
**Location**: `.kiro/steering/` directory
**Quality Score**: [Score] (meeting all Kiro validation standards and usefulness criteria)

[Display key steering highlights and project-specific guidance]

</generated_deliverables>

**Please review your steering documents.**

**Consider:**

- Does the product guidance accurately capture your project vision and priorities?
- Do the technology constraints and standards match your development approach?
- Are the code organization patterns appropriate for your project structure?
- Is the guidance genuinely useful for enhancing your development workflow?
- Are there any project-specific considerations missing from the guidance?
- Do the quality standards align with your team practices and project goals?

**Your options:**

- **Request Changes**: Tell me what needs to be modified, added, or refined
- **Focus Adjustments**: Adjust emphasis areas or add missing project context
- **Customization Requests**: Modify templates or add project-specific guidance  
- **Ready to Approve**: If satisfied, say "looks good", "approved", or "yes"

**What's your feedback?**

</steering_review_cycle>

[Handle user feedback and refinement cycle]

---

### Refinement Cycle (if changes requested)

[If user requests changes:]

1. **Analyze specific feedback** and identify areas for steering document improvement
2. **Update steering documents** with requested changes while maintaining preservation strategy
3. **Re-run quality validation** to ensure all standards maintained and usefulness preserved
4. **Present updated version** for another review cycle with enhancement highlights
5. **Continue until explicit approval received**

## 7. Final Confirmation & Integration Setup

<final_integration_setup>

### Steering Documents Approved

Thank you for the approval! Your steering documents are now finalized and ready to enhance your Kiro workflow.

**Steering Setup Complete:**

- **Product Steering**: `.kiro/steering/product.md` (project vision and feature guidance)
- **Technology Steering**: `.kiro/steering/tech.md` (development constraints and standards)
- **Structure Steering**: `.kiro/steering/structure.md` (code organization and quality patterns)
- **Customization Preservation**: All your existing content preserved exactly
- **Quality Enhancement**: Missing sections added, incomplete areas improved

**Integration Validation:**

- ✅ **Requirements Enhancement**: Product context will improve requirement generation quality
- ✅ **Design Enhancement**: Technology guidance will inform better architecture decisions
- ✅ **Implementation Enhancement**: Structure patterns will guide consistent code organization  
- ✅ **Workflow Integration**: All Kiro commands will now have enhanced project context

<final_deliverables>

**Final Deliverables:**

- **Steering Documents**: Complete project guidance system ready for immediate use
- **Quality Validation**: All Kiro steering standards met with project-specific focus
- **Workflow Enhancement**: Measurable improvement in all Kiro workflow command outputs
- **Maintenance Strategy**: Clear approach for keeping steering documents current

</final_deliverables>

### Integration Setup & Usage Guidance

## Steering Setup Successful

**Your project now has comprehensive steering guidance that will enhance all Kiro workflow operations!**

**How Steering Enhances Your Workflow:**

### Requirements Clarification Enhancement

- **Product context** guides feature prioritization and scope decisions
- **User focus** ensures requirements align with actual user needs
- **Success metrics** provide validation criteria for feature completeness

### Design Document Enhancement  

- **Technology constraints** guide architecture and technology selection
- **Integration standards** ensure consistent external system connections
- **Quality standards** inform design decisions and component specifications

### Implementation Planning Enhancement

- **Structure patterns** guide task organization and code structure decisions
- **Quality standards** ensure consistent implementation approaches
- **Development workflows** inform task sequencing and dependency management

### Task Execution Enhancement

- **Code quality standards** guide implementation decisions during coding
- **Naming conventions** ensure consistent code organization
- **Integration patterns** guide component connections and interface design

**Immediate Benefits:**

- **Better Requirements**: More focused and project-appropriate requirement generation
- **Stronger Design**: Architecture decisions informed by your actual constraints
- **Consistent Implementation**: Code organization follows your established patterns
- **Quality Assurance**: All outputs meet your specific project quality standards

### Next Steps

**Ready to experience enhanced workflow quality?**

**Start your next feature development:**

```
/kiro:1-init feature-description
```

**Or work on an existing feature with enhanced guidance:**

```
/kiro:2-requirements-clarification feature-name
```

**Check how steering enhances your project:**

```
/kiro:6-status feature-name
```

**Steering Document Maintenance:**

- **Update when project evolves**: Run `/kiro:0-steering` again to enhance steering
- **Add domain-specific guidance**: Use `/kiro:0-steering-custom` for specialized needs
- **Review quarterly**: Keep steering current with project growth and changes

**Kiro Steering Setup Complete - Your Workflow is Now Enhanced!**

</final_integration_setup>
