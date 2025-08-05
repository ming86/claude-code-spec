---
description: 'Generate comprehensive project steering documents from codebase analysis'
argument-hint: '[updateType: full|incremental]'
---

# Role and Objective

Generate comprehensive project steering documents that provide persistent, accurate project context for spec-driven development through systematic codebase analysis.

# Instructions

## Analysis Strategy

- **Accuracy-First**: Document information must reflect actual codebase state, not assumptions
- **Completeness**: Cover all relevant aspects for each steering domain thoroughly  
- **Currency**: Include latest technology versions and patterns found in project
- **Project-Specific**: Avoid generic templates, create content based on actual analysis

## Anti-Shortcut Quality Patterns

- Analyze existing codebase using systematic tool-based investigation rather than making assumptions
- Create project-specific content based on actual patterns found, not generic best practices
- Use comprehensive analysis to understand project structure, technology stack, and patterns
- Generate factual documentation that reflects current project state

# Execution Steps

## 1. Comprehensive Project Discovery

**Objective**: Build complete understanding of project structure, technology stack, and development patterns

**Process**:

- Detect project type indicators and locate package management files
- Examine code patterns, implementation examples, and architectural approaches
- Analyze configuration files for technology stack and build processes
- Review documentation files (README.md, docs/, etc.) for project context
- Understand development workflows from discovered scripts and configurations
- Identify testing frameworks, deployment configurations, and development tools

## 2. Existing Documentation Assessment

**Objective**: Understand current steering state and determine preservation vs. update strategy

**Process**:

- Check for existing steering documents in `.spec-workflow/steering/` directory
- Identify user customizations, manual additions, and editorial content to preserve
- Assess currency of existing information against current codebase state
- Determine appropriate update strategy (full regeneration vs. targeted updates)
- Plan preservation strategy for custom content and user modifications

## 3. Domain-Specific Content Generation

**Objective**: Create comprehensive, accurate steering documents for each core domain

### Product Overview (.spec-workflow/steering/product.md)

- Extract product purpose and description from codebase analysis and documentation
- Identify core features and capabilities from component and functionality analysis
- Derive target use cases from application architecture and user interaction patterns
- Document key value proposition and architectural decision rationale

### Technology Stack (.spec-workflow/steering/tech.md)

- Compile comprehensive technology inventory from dependency analysis
- Document development environment setup with specific commands and requirements
- Map architecture patterns and design decisions found in codebase structure  
- Record port configurations, environment variables, and service dependencies
- Include build processes, testing frameworks, and deployment configurations

### Project Structure (.spec-workflow/steering/structure.md)

- Map detailed directory organization based on actual project layout
- Document code organization patterns and architectural boundaries observed
- Record file naming conventions and import management patterns discovered
- Describe module separation and dependency management strategies in use
- Include examples of typical file structures and organization principles

## 4. Integration and Workflow Configuration

**Objective**: Properly integrate steering documents into development workflow and tooling

**Process**:

- Update `.github/copilot-instructions.md` with complete steering configuration
- Verify steering documents are accessible and properly formatted for consumption
- Ensure integration doesn't conflict with existing custom steering or configuration
- Test document accessibility and validate workflow integration points
- Configure appropriate inclusion modes for different steering documents

# Output Requirements

## Directory Structure

```
.spec-workflow/
├── steering/
│   ├── product.md        (Always included - Generated/Updated)
│   ├── tech.md           (Always included - Generated/Updated)
│   ├── structure.md      (Always included - Generated/Updated)
│   └── [custom files]    (Preserved - Created via spec-0-steering-custom)
```

## Document Standards

Each steering document must be:

- **Accurate**: Reflects actual codebase state, not assumptions
- **Complete**: Covers all relevant aspects for the domain
- **Current**: Uses latest technology versions and patterns found
- **Actionable**: Provides specific, usable development information
- **Consistent**: Aligns with other steering documents

## Update Strategy Types

### Full Steering Update

- Regenerate all three core steering documents completely
- Preserve existing custom steering files (created via spec-0-steering-custom)
- Update copilot-instructions.md configuration completely
- Use when major project changes or initial setup

### Incremental Steering Update

- Update specific sections based on detected codebase changes
- Preserve manual customizations and user additions
- Focus updates on changed areas while maintaining existing content
- Use when making targeted updates to existing steering

# Quality Validation

## Completion Criteria Checklist

- [ ] Comprehensive codebase analysis completed using all available tools
- [ ] All three core steering documents generated with project-specific content
- [ ] User customizations preserved in existing documents where applicable
- [ ] .github/copilot-instructions.md updated with complete steering configuration
- [ ] Integration verified to work with existing workflow and custom steering
- [ ] No sensitive information included in any generated documentation
- [ ] All documents follow consistent formatting and provide actionable information

## Content Accuracy Validation

- [ ] All technical information reflects actual codebase state, not assumptions
- [ ] Development commands and configurations are accurate and tested
- [ ] Directory structures and naming conventions match actual project patterns
- [ ] Architecture descriptions align with observed implementation patterns
- [ ] Product descriptions accurately reflect application purpose and capabilities

## Analysis Validation

- [ ] All documented technologies are actually present in the project
- [ ] All commands and configurations are verified from actual project files
- [ ] Directory structures accurately reflect actual project layout
- [ ] No generic examples or placeholder content remains

# Examples

## Argument Handling

```bash
/spec:0-steering full        # Complete regeneration of all steering documents
/spec:0-steering incremental # Targeted updates based on detected changes
/spec:0-steering            # Default to full update
```

## Multi-Language Detection Process

- **Python Project**: "Detected *.py files and requirements.txt, analyzing Python package structure..."
- **JavaScript/Node.js**: "Found *.js files and package.json, examining npm/yarn dependencies..."
- **C# Project**: "Identified *.cs files and *.csproj/*.sln, analyzing .NET project structure..."
- **Generic Pattern**: "Using systematic detection to identify project type indicators, then applying appropriate analysis patterns..."

## Complete Analysis Workflow

1. **Detection**: "Using detection tools to identify project indicators... Found Python project with Flask framework"
2. **Pattern Analysis**: "Analyzing code organization patterns and architectural approaches..."
3. **Content Generation**: "Creating tech.md with Python-specific development environment and pip commands based on analysis..."
4. **Integration**: "Updating copilot-instructions.md with steering configuration for all three documents..."

# Template Structures

## Product Overview Template Structure

```markdown
# Product Overview

## Description
[Clear product description based on codebase analysis and documentation review]

## Core Features
- [Primary features identified from codebase functionality analysis]
- [User-facing capabilities derived from component structure]
- [Major functional areas based on application architecture]

## Use Cases
- [Primary use cases based on application design and user flow analysis]
- [Target user scenarios derived from interface and interaction patterns]
- [Project value delivered based on feature set and architecture]

## Architecture Overview
- [High-level architectural approach based on codebase structure]
- [Key design decisions identified from implementation patterns]
- [Technology choice rationale derived from stack analysis]

## Integration Points
- [External service integrations found in configuration]
- [API endpoints and data flow patterns]
- [Third-party dependencies and their purposes]
```

## Technology Stack Template Structure

```markdown
# Technology Stack

## Languages and Frameworks
- **Primary Language**: [Detected language and version from project files]
- **Main Framework**: [Primary framework identified from dependencies]
- **Additional Libraries**: [Key dependencies and their purposes]
- **Runtime**: [Runtime environment and version requirements]

## Development Environment
- **Package Manager**: [Detected package manager with version from project analysis]
- **Build System**: [Detected build system and configuration from project files]
- **Testing Framework**: [Detected testing framework and setup from project structure]
- **Development Tools**: [Detected linters, formatters, type checkers from configuration]

## Architecture and Patterns
- **Architectural Pattern**: [MVC, microservices, component-based, etc.]
- **Database**: [Database technology and configuration if applicable]
- **API Design**: [REST, GraphQL, RPC patterns observed]
- **State Management**: [Redux, Context, Pinia, etc. if applicable]

## Development Commands
- **Install Dependencies**: [actual package manager install command]
- **Development Server**: [dev server command with ports and options]
- **Production Build**: [build command with output configuration]
- **Test Execution**: [test command with coverage and options]
- **Linting and Formatting**: [code quality commands available]

## Ports and Services
- **Development Server**: [dev server port and host configuration]
- **API Services**: [API server ports and endpoints if different]
- **Database**: [database connection details if applicable]
- **External Services**: [service ports and configurations]

## Environment Variables
- [Key environment variables and their purposes]
- [Configuration patterns and file locations]
- [Development vs production variable differences]
```

## Project Structure Template Structure

```markdown
# Project Structure

## Directory Organization

[Generated directory tree based on actual codebase analysis]

## Code Organization Patterns
- **Components/Modules**: [How primary code units are organized and structured]
- **Utilities and Helpers**: [Common utility organization and accessibility patterns]
- **Configuration Management**: [Config file locations, patterns, and hierarchy]
- **Test Organization**: [Test file organization, naming, and co-location patterns]
- **Asset Management**: [Static assets, images, styles organization]

## Naming Conventions
- **Files and Directories**: [File naming patterns observed across project]
- **Functions and Methods**: [Function naming conventions discovered]
- **Variables and Constants**: [Variable naming patterns and standards]
- **Components**: [Component naming conventions if applicable]
- **Modules and Packages**: [Module naming and export patterns]

## Architectural Boundaries
- **Module Separation**: [How different concerns are separated into modules]
- **Layer Organization**: [Application layer organization and dependencies]
- **Dependency Management**: [How internal and external dependencies are managed]
- **API Boundaries**: [How different parts of the system communicate]

## Import and Export Patterns
- [How modules import and export functionality]
- [Relative vs absolute import patterns]
- [Index file usage and re-export strategies]
```

Create comprehensive, living documentation that provides valuable project context for spec-driven development while preserving user customizations and maintaining accuracy through systematic codebase analysis.
