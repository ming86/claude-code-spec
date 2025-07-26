---
description: Generate and update project steering documents from codebase analysis
tools: ['codebase', 'search', 'editFiles']
---

# Project Steering Generation Mode

Generate comprehensive project steering documents for: **${input:updateType:full|incremental} steering update**

## Purpose and Scope

**Primary Function**: Analyze existing project and generate/update core steering documents that provide persistent project context for all subsequent development phases.

**Steering Documents Generated**:

- **product.md**: Product overview, features, use cases, value proposition
- **tech.md**: Architecture, tech stack, dev environment, commands, ports
- **structure.md**: Directory organization, code patterns, naming conventions

## Prerequisites Validation

### Project Analysis Required

Before generating steering documents:

- Analyze project structure using codebase tool
- Review existing code patterns and conventions
- Identify technology stack and frameworks in use
- Understand architectural decisions and constraints

### Existing Steering Assessment

Check for existing steering documents:

- Review `.kiro/steering/` directory contents
- Assess current steering document quality and completeness
- Identify gaps or outdated information
- Determine update strategy (full regeneration vs incremental updates)

## Steering Document Generation Process

### 1. Comprehensive Project Analysis

**Codebase Structure Analysis**:

- Use codebase tool to examine directory organization
- Identify main application entry points
- Analyze module organization and boundaries
- Review configuration files and build systems

**Technology Stack Discovery**:

- Identify programming languages and versions
- Discover frameworks and libraries in use
- Analyze package management files (package.json, requirements.txt, etc.)
- Review build and deployment configurations

**Architectural Pattern Recognition**:

- Identify architectural patterns (MVC, microservices, etc.)
- Analyze data flow and component relationships
- Review API design patterns and conventions
- Understand testing frameworks and approaches

### 2. Product Context Generation

**Create/Update product.md**:

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

### 3. Technical Context Generation

**Create/Update tech.md**:

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

### 4. Structure Context Generation

**Create/Update structure.md**:

```markdown
# Project Structure

## Directory Organization
```

[Generated directory tree based on codebase analysis]

```

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

## Context Integration and Validation

### Steering Document Quality Checks

**Completeness Validation**:

- [ ] Product overview accurately reflects codebase capabilities
- [ ] Technology stack completely documented with versions
- [ ] Directory structure accurately represents project organization
- [ ] Development commands tested and verified
- [ ] Naming conventions consistently documented

**Accuracy Verification**:

- [ ] All documented technologies actually present in codebase
- [ ] Development commands functional and current
- [ ] Architecture description matches actual implementation
- [ ] Port numbers accurate for local development

### Steering Metadata Configuration

**Update steering configuration**:

```markdown
## Active Steering Files

- `product.md`: Always included - Product context and business objectives
- `tech.md`: Always included - Technology stack and architectural decisions
- `structure.md`: Always included - File organization and code patterns

## Custom Steering Files

<!-- Space for custom steering files added via spec-0-steering-custom -->
```

## File Management and Updates

### Steering Directory Structure

**Ensure proper structure**:

```
.kiro/
├── steering/
│   ├── product.md        (Always included)
│   ├── tech.md           (Always included)
│   ├── structure.md      (Always included)
│   └── [custom files]    (Created via spec-0-steering-custom)
```

### Update Strategy

**Full Steering Update**:

- Regenerate all three core steering documents
- Preserve any custom steering files
- Update CLAUDE.md steering configuration section
- Validate all documents for accuracy and completeness

**Incremental Steering Update**:

- Update specific sections based on codebase changes
- Preserve manual customizations where possible
- Focus on areas that have changed since last update
- Maintain consistency across all steering documents

## Quality Standards

### Documentation Requirements

**Each steering document must**:

- **Accurate**: Reflect actual codebase state
- **Complete**: Cover all relevant aspects for its domain
- **Current**: Include latest technology versions and patterns
- **Actionable**: Provide specific, usable information
- **Consistent**: Align with other steering documents

### Integration Requirements

**Steering documents should**:

- **Complement each other** without duplication
- **Reference actual codebase** elements and patterns
- **Support development workflow** with accurate commands
- **Enable context preservation** for future development
- **Facilitate onboarding** for new team members

## Boundaries and Constraints

### What This Phase DOES

- ✅ Analyze existing project structure and technology
- ✅ Generate/update core steering documents (product.md, tech.md, structure.md)
- ✅ Create accurate development environment documentation
- ✅ Document architectural patterns and conventions
- ✅ Update CLAUDE.md steering configuration

### What This Phase DOES NOT DO

- ❌ Create custom specialized steering documents (use spec-0-steering-custom)
- ❌ Generate feature specifications or requirements
- ❌ Create implementation plans or tasks
- ❌ Modify application code or configuration
- ❌ Create spec workflow directories (use spec-1-init)

## Completion Process

After generating steering documents:

1. **Validate accuracy** against actual codebase
2. **Test documented commands** to ensure they work
3. **Review document completeness** for all required sections
4. **Update CLAUDE.md** steering configuration section
5. **Provide steering summary** with key project insights

Generate comprehensive, accurate steering documents that serve as the foundation for all subsequent spec-driven development work.
