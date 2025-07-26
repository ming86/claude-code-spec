---
description: Spec-Driven Development Step 0 - Create or update project steering documents for spec-driven development workflow
mode: agent
tools: ['changes', 'codebase', 'editFiles', 'extensions', 'problems', 'runCommands', 'runTasks', 'search', 'searchResults', 'terminalLastCommand', 'terminalSelection', 'testFailure', 'usages', 'get_syntax_docs', 'mermaid-diagram-preview', 'mermaid-diagram-validator']
---

# Project Steering Management

Create or update steering documents in `.spec-workflow/steering/` to maintain accurate project knowledge for spec-driven development. This prompt intelligently detects existing documents and handles them appropriately.

## Existing Files Status

First, check the current state of steering documents:

### Core Steering Documents

- Product overview: Check if `.spec-workflow/steering/product.md` exists
- Technology stack: Check if `.spec-workflow/steering/tech.md` exists
- Project structure: Check if `.spec-workflow/steering/structure.md` exists
- Custom steering files: Check for additional `.md` files in `.spec-workflow/steering/`

### Project Analysis

Analyze the current project state:

- Source code files: Look for implementation files in common languages
- Configuration files: Check for package.json, requirements.txt, etc.
- Documentation: Look for README files and other documentation
- Recent changes: Review git history if available

### Existing Documentation Context

Reference existing project documentation:

- Main README file
- Package configuration files
- Existing documentation directories

## Smart Update Strategy

Based on existing files:

### For NEW files (not found):

Generate comprehensive initial content covering all aspects of the project.

### For EXISTING files (found):

1. **Preserve user customizations** - Any manual edits or custom sections
2. **Update factual information** - Dependencies, file structures, commands
3. **Add new sections** - Only if significant new capabilities exist
4. **Mark deprecated content** - Rather than deleting
5. **Maintain formatting** - Keep consistent with existing style

## Core Steering Files Strategy

The three core steering files are designed to be **Always Included** - loaded in every AI interaction to provide consistent project context:

- `product.md`: Always - Business context needed for all development decisions
- `tech.md`: Always - Technical constraints affect all code generation
- `structure.md`: Always - Architectural decisions impact all file organization

## Implementation Tasks

### 1. Product Overview (`product.md`)

#### For NEW file:

Generate comprehensive product overview including:

- **Product Overview**: Brief description of what the product is
- **Core Features**: Bulleted list of main capabilities
- **Target Use Case**: Specific scenarios the product addresses
- **Key Value Proposition**: Unique benefits and differentiators

#### For EXISTING file:

Update only if there are:

- **New features** added to the product
- **Removed features** or deprecated functionality
- **Changed use cases** or target audience
- **Updated value propositions** or benefits

### 2. Technology Stack (`tech.md`)

#### For NEW file:

Document the complete technology landscape:

- **Architecture**: High-level system design
- **Frontend**: Frameworks, libraries, build tools (if applicable)
- **Backend**: Language, framework, server technology (if applicable)
- **Development Environment**: Required tools and setup
- **Common Commands**: Frequently used development commands
- **Environment Variables**: Key configuration variables
- **Port Configuration**: Standard ports used by services

#### For EXISTING file:

Check for changes in:

- **New dependencies** added via package managers
- **Removed libraries** or frameworks
- **Version upgrades** of major dependencies
- **New development tools** or build processes
- **Changed environment variables** or configuration
- **Modified port assignments** or service architecture

### 3. Project Structure (`structure.md`)

#### For NEW file:

Outline the codebase organization:

- **Root Directory Organization**: Top-level structure with descriptions
- **Subdirectory Structures**: Detailed breakdown of key directories
- **Code Organization Patterns**: How code is structured
- **File Naming Conventions**: Standards for naming files and directories
- **Import Organization**: How imports/dependencies are organized
- **Key Architectural Principles**: Core design decisions and patterns

#### For EXISTING file:

Look for changes in:

- **New directories** or major reorganization
- **Changed file organization** patterns
- **New or modified naming conventions**
- **Updated architectural patterns** or principles
- **Refactored code structure** or module boundaries

### 4. Custom Steering Files

If custom steering files exist:

- **Preserve them** - Do not modify unless specifically outdated
- **Check relevance** - Note if they reference removed features
- **Suggest new custom files** - If new specialized areas emerge

## Quality Guidelines

### Security Guidelines

- **Never include sensitive data**: No API keys, passwords, database credentials, or personal information
- **Review before commit**: Always review steering content before version control
- **Team sharing consideration**: Remember steering files are shared with all project collaborators

### Content Quality Guidelines

- **Single domain focus**: Each steering file should cover one specific area
- **Clear, descriptive content**: Provide concrete examples and rationale for decisions
- **Regular maintenance**: Review and update steering files after major project changes
- **Actionable guidance**: Write specific, implementable guidelines rather than abstract principles

### Preservation Strategy

- **User sections**: Any section not in the standard template should be preserved
- **Custom examples**: User-added examples should be maintained
- **Comments**: Inline comments or notes should be kept
- **Formatting preferences**: Respect existing markdown style choices

### Update Philosophy

- **Additive by default**: Add new information rather than replacing
- **Mark deprecation**: Use strikethrough or [DEPRECATED] tags
- **Date significant changes**: Add update timestamps for major changes
- **Explain changes**: Brief notes on why something was updated

## Instructions

1. **Create `.spec-workflow/steering/` directory** if it doesn't exist
2. **Check existing files** to determine create vs update mode
3. **Analyze the codebase** using available tools
4. **For NEW files**: Generate comprehensive initial documentation
5. **For EXISTING files**:
   - Read current content first
   - Preserve user customizations and comments
   - Update only factual/technical information
   - Maintain existing structure and style
6. **Use clear markdown formatting** with proper headers and sections
7. **Include concrete examples** where helpful for understanding
8. **Focus on facts over assumptions** - document what exists
9. **Follow spec-driven development principles**

The goal is to maintain living documentation that stays current while respecting user customizations, supporting effective spec-driven development without requiring users to worry about losing their work.
