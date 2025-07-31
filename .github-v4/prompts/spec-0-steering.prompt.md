---
description: Create or update project steering documents for spec-driven development
mode: agent
tools: ['codebase', 'search', 'editFiles']
---

# Project Steering Management

Generate comprehensive project steering documents for: **${input:updateType:full|incremental} steering update**

Intelligently create or update steering documents in `.kiro/steering/` to maintain accurate project knowledge for spec-driven development.

## Current Project Analysis

### Codebase Structure Analysis

Use the codebase tool to understand:

- Current project structure and organization
- Technology stack and frameworks in use
- Existing architectural patterns
- Configuration files and build processes
- Testing approaches and conventions

### Project State Assessment

Analyze existing files to understand:

- Package management files (package.json, requirements.txt, etc.)
- Configuration files (tsconfig.json, webpack.config.js, etc.)
- Documentation structure and content
- Directory organization and naming conventions

## Steering Documents to Manage

### 1. Product Overview (`product.md`)

**Content to generate or update**:

- **Product Description**: Brief overview of what the product/system does
- **Core Features**: Main capabilities and functionality
- **Target Use Cases**: Primary scenarios and user types
- **Key Value Proposition**: Unique benefits and differentiators

**Template Structure**:

```markdown
# Product Overview

## Description

[Clear product description based on codebase analysis]

## Core Features

- [List primary features identified from codebase]
- [Include user-facing capabilities]
- [Reference major functional areas]

## Use Cases

- [Primary use cases based on functionality analysis]
- [Target user scenarios]
- [Business value delivered]

## Architecture Overview

- [High-level architectural approach]
- [Key design decisions]
- [Technology choice rationale]
```

### 2. Technology Stack (`tech.md`)

**Content to generate or update**:

- **Architecture**: High-level system design and patterns
- **Frontend Technologies**: Frameworks, libraries, build tools (if applicable)
- **Backend Technologies**: Languages, frameworks, databases (if applicable)
- **Development Environment**: Required tools, dependencies, setup
- **Common Commands**: Frequently used development commands
- **Environment Variables**: Key configuration variables
- **Port Configuration**: Standard ports used by services

**Template Structure**:

```markdown
# Technology Stack

## Languages and Frameworks

- **Primary Language**: [Detected language and version]
- **Framework**: [Main framework in use]
- **Additional Libraries**: [Key dependencies]

## Development Environment

- **Package Manager**: [npm, pip, cargo, etc.]
- **Build System**: [webpack, rollup, make, etc.]
- **Testing Framework**: [jest, pytest, etc.]

## Architecture

- **Pattern**: [MVC, microservices, etc.]
- **Database**: [Database technology if applicable]
- **API Design**: [REST, GraphQL, etc.]

## Development Commands

- **Install**: [package manager install command]
- **Dev Server**: [development server command]
- **Build**: [production build command]
- **Test**: [test execution command]

## Ports and Services

- **Development**: [dev server port]
- **API**: [API server port if different]
- **Database**: [database port if applicable]
```

### 3. Project Structure (`structure.md`)

**Content to generate or update**:

- **Root Directory Organization**: Top-level structure with descriptions
- **Key Directories**: Detailed breakdown of important directories
- **Code Organization Patterns**: How code is structured and organized
- **File Naming Conventions**: Standards for naming files and directories
- **Import Organization**: How dependencies and imports are managed
- **Architectural Principles**: Core design decisions and patterns

**Template Structure**:

```markdown
# Project Structure

## Directory Organization

[Generated directory tree based on codebase analysis]

## Code Organization Patterns

- **Components**: [How components are organized]
- **Utilities**: [Common utility organization]
- **Configuration**: [Config file locations and patterns]
- **Tests**: [Test file organization and naming]

## Naming Conventions

- **Files**: [File naming patterns observed]
- **Functions**: [Function naming conventions]
- **Variables**: [Variable naming patterns]
- **Components**: [Component naming if applicable]

## Architectural Boundaries

- **Modules**: [How modules are separated]
- **Layers**: [Application layer organization]
- **Dependencies**: [Dependency management patterns]
```

## Smart Update Strategy

### For New Projects

- Generate comprehensive initial documentation
- Analyze codebase thoroughly to understand patterns
- Create detailed steering documents covering all aspects

### For Existing Projects

- **Preserve user customizations**: Maintain any manual edits or custom sections
- **Update factual information**: Refresh dependencies, commands, structure
- **Add new sections**: Only if significant new capabilities exist
- **Mark deprecated content**: Rather than deleting outdated information

## Implementation Process

### 1. Directory Setup

Ensure `.kiro/steering/` directory exists

### 2. Codebase Analysis

Use codebase tool to gather information about:

- Project dependencies and configuration
- Directory structure and organization
- Architectural patterns and conventions
- Documentation and README files

### 3. Document Generation/Updates

For each steering document:

- Generate comprehensive content based on analysis
- Use clear markdown formatting
- Include concrete examples where helpful
- Focus on facts over assumptions

### 4. Quality Standards

Ensure all documents:

- Provide actionable information
- Use clear, descriptive language
- Include specific examples and details
- Are well-organized and easy to navigate

## CLAUDE.md Integration

**Update steering configuration**:

```markdown
## Active Steering Files

- `product.md`: Always included - Product context and business objectives
- `tech.md`: Always included - Technology stack and architectural decisions
- `structure.md`: Always included - File organization and code patterns

## Custom Steering Files

<!-- Space for custom steering files added via spec-0-steering-custom -->
```

## Security Guidelines

**Never include sensitive information**:

- No API keys, passwords, or credentials
- No personal or confidential information
- Review content before committing to version control
- Consider team sharing implications

## Output Format

Generate or update steering documents that provide:

- Clear project context and overview
- Detailed technical information
- Practical development guidance
- Consistent formatting and structure

Create living documentation that stays current and provides valuable context for spec-driven development without requiring users to worry about losing customizations.
