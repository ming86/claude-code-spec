---
description: Create or update project steering documents for spec-driven development
mode: agent
tools: ['search', 'codebase', 'editFiles']
---

# Project Steering Management

Create or update steering documents in `.spec-workflow/steering/` to maintain accurate project knowledge for spec-driven development.

## Primary Task

**You must generate these three steering files in `.spec-workflow/steering/`:**

1. `product.md`
2. `tech.md`
3. `structure.md`

## Execution Steps

### Step 1: Check Existing Files

Use `search` tool to check if `.spec-workflow/steering/` directory and files already exist.

### Step 2: Analyze Project Context

Use `codebase` tool to understand current project state.

### Step 3: Generate Required Files

Use `editFiles` tool to create files. For existing files: read current content first, preserve user customizations, update only factual information.

## File Generation Tasks

### 1. Product Overview (`product.md`)

Generate comprehensive product overview including:

- **Product Overview**: Brief description of what the product is
- **Core Features**: Bulleted list of main capabilities
- **Target Use Case**: Specific scenarios the product addresses
- **Key Value Proposition**: Unique benefits and differentiators

### 2. Technology Stack (`tech.md`)

Document the complete technology landscape:

- **Architecture**: High-level system design
- **Frontend**: Frameworks, libraries, build tools (if applicable)
- **Backend**: Language, framework, server technology (if applicable)
- **Development Environment**: Required tools and setup
- **Common Commands**: Frequently used development commands
- **Environment Variables**: Key configuration variables
- **Port Configuration**: Standard ports used by services

### 3. Project Structure (`structure.md`)

Outline the codebase organization:

- **Root Directory Organization**: Top-level structure with descriptions
- **Subdirectory Structures**: Detailed breakdown of key directories
- **Code Organization Patterns**: How code is structured
- **File Naming Conventions**: Standards for naming files and directories
- **Import Organization**: How imports/dependencies are organized
- **Key Architectural Principles**: Core design decisions and patterns

## Security Guidelines

- Never include sensitive data: No API keys, passwords, database credentials
- Review before commit: Always review steering content before version control

## Completion Requirements

After generating all three files, confirm:

1. ✅ `.spec-workflow/steering/product.md` created/updated
2. ✅ `.spec-workflow/steering/tech.md` created/updated
3. ✅ `.spec-workflow/steering/structure.md` created/updated

## Refinement Options

What would you like me to refine about the steering documents?

- **Update scope**: Add or modify steering document sections?
- **Technology focus**: Different technology stack emphasis?
- **Architecture details**: More architectural patterns or simpler structure?
- **Documentation depth**: More detailed examples or concise guidelines?
- **Custom steering**: Create specialized steering documents?
- **Proceed if satisfied** with current steering documents?

I can iterate on the steering documents in our conversation until you're satisfied.
