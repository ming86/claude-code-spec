---
description: Create or update project steering documents for spec-driven development
mode: agent
tools: ['codebase', 'search', 'editFiles']
---

# Project Steering Management

Intelligently create or update steering documents in `.spec-workflow/steering/` to maintain accurate project knowledge for spec-driven development.

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

### 2. Technology Stack (`tech.md`)

**Content to generate or update**:

- **Architecture**: High-level system design and patterns
- **Frontend Technologies**: Frameworks, libraries, build tools (if applicable)
- **Backend Technologies**: Languages, frameworks, databases (if applicable)
- **Development Environment**: Required tools, dependencies, setup
- **Common Commands**: Frequently used development commands
- **Environment Variables**: Key configuration variables
- **Port Configuration**: Standard ports used by services

### 3. Project Structure (`structure.md`)

**Content to generate or update**:

- **Root Directory Organization**: Top-level structure with descriptions
- **Key Directories**: Detailed breakdown of important directories
- **Code Organization Patterns**: How code is structured and organized
- **File Naming Conventions**: Standards for naming files and directories
- **Import Organization**: How dependencies and imports are managed
- **Architectural Principles**: Core design decisions and patterns

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

Ensure `.spec-workflow/steering/` directory exists

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
