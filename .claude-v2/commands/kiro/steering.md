---
description: Enhanced steering document management with codebase analysis and intelligent updates
allowed-tools: Bash, Read, Write, Edit, MultiEdit, Update, Glob, Grep
---

# Enhanced Steering Document Management

Intelligently create, update, or refresh steering documents with codebase analysis integration.

## Steering Intelligence Assessment

### Existing Steering Analysis

!`ls -la .kiro/steering/ 2>/dev/null && echo "📁 Existing steering directory found" || echo "📁 No steering directory - will create"`

### Current Steering Files Check

!`if [ -d ".kiro/steering" ]; then echo "📋 Current steering files:"; ls -la .kiro/steering/ | grep "\.md$" | awk '{print "- " $9}' || echo "- No steering files found"; else echo "- No steering directory exists"; fi`

### Codebase Analysis for Context

!`echo "🔍 Codebase Analysis:"; find . -maxdepth 3 -name "*.json" -o -name "*.toml" -o -name "*.yaml" -o -name "*.yml" | grep -E "(package\.json|requirements\.txt|Cargo\.toml|composer\.json|pom\.xml|build\.gradle|pyproject\.toml|docker-compose\.yml)" | head -5`

### Project Structure Detection

!`echo "🏗️ Project Structure Analysis:"; if [ -d "src" ]; then echo "- src/ directory detected"; fi; if [ -d "app" ]; then echo "- app/ directory detected"; fi; if [ -d "lib" ]; then echo "- lib/ directory detected"; fi; if [ -d "components" ]; then echo "- components/ directory detected"; fi; if [ -d "pages" ]; then echo "- pages/ directory detected"; fi; if [ -d "api" ]; then echo "- api/ directory detected"; fi; if [ -d "tests" ] || [ -d "test" ]; then echo "- test directory detected"; fi; if [ -d ".github" ]; then echo "- GitHub workflows detected"; fi; if [ -d "docs" ]; then echo "- docs/ directory detected"; fi`

### Technology Stack Detection

!`echo "⚙️ Technology Stack Detection:"; if [ -f "package.json" ]; then echo "- Node.js/JavaScript project"; if grep -q "react" package.json 2>/dev/null; then echo "  - React framework"; fi; if grep -q "next" package.json 2>/dev/null; then echo "  - Next.js framework"; fi; if grep -q "vue" package.json 2>/dev/null; then echo "  - Vue.js framework"; fi; if grep -q "typescript" package.json 2>/dev/null; then echo "  - TypeScript"; fi; fi; if [ -f "requirements.txt" ] || [ -f "pyproject.toml" ]; then echo "- Python project"; if grep -q "fastapi\|django\|flask" requirements.txt pyproject.toml 2>/dev/null; then echo "  - Web framework detected"; fi; fi; if [ -f "Cargo.toml" ]; then echo "- Rust project"; fi; if [ -f "go.mod" ]; then echo "- Go project"; fi; if [ -f "pom.xml" ] || [ -f "build.gradle" ]; then echo "- Java project"; fi`

## Steering Strategy Selection

### Intelligent Steering Mode

Determine the appropriate steering approach based on project state:

#### New Project Steering (No existing steering)

- Create comprehensive steering from codebase analysis
- Establish foundational project knowledge
- Set up initial architectural documentation

#### Update Existing Steering (Steering exists but may be outdated)

- Preserve existing user customizations
- Refresh technical information based on current codebase
- Add missing elements without overwriting custom content

#### Refresh Steering (Steering exists and is current)

- Light refresh of technical details
- Validate consistency with current codebase
- Minimal changes to preserve user work

### Steering Mode Detection

!`if [ -d ".kiro/steering" ]; then STEERING_COUNT=$(ls .kiro/steering/*.md 2>/dev/null | wc -l); if [ $STEERING_COUNT -eq 0 ]; then echo "🆕 Mode: New Project Steering"; STEERING_MODE="new"; elif [ $STEERING_COUNT -lt 3 ]; then echo "🔄 Mode: Update Existing Steering"; STEERING_MODE="update"; else echo "♻️ Mode: Refresh Steering"; STEERING_MODE="refresh"; fi; else echo "🆕 Mode: New Project Steering"; STEERING_MODE="new"; fi`

## Enhanced Steering Document Generation

### 1. Product Steering (product.md)

#### Codebase-Informed Product Analysis

!`echo "📊 Product Context Analysis:"; if [ -f "README.md" ]; then echo "- README.md found for product description"; fi; if [ -f "package.json" ]; then PKG_DESC=$(cat package.json | jq -r '.description // "No description"' 2>/dev/null); echo "- Package description: $PKG_DESC"; fi; if [ -d "docs" ]; then DOC_COUNT=$(find docs -name "*.md" | wc -l); echo "- Documentation files: $DOC_COUNT"; fi`

#### Product.md Generation/Update

**Approach**: Create comprehensive product documentation based on codebase analysis

- **For NEW steering**: Create complete product.md from scratch using codebase insights
- **For UPDATE steering**: Enhance existing product.md with missing sections
- **For REFRESH steering**: Update technical details while preserving business context

Product.md content framework:

```markdown
# Product Overview

## Project Description
[Analysis-informed description based on README, package.json, and project structure]

## Core Features and Capabilities
[Derived from codebase analysis, API endpoints, component structure]

## Target Users and Use Cases
[Inferred from UI components, API design, and existing documentation]

## Value Proposition
[Business value based on feature analysis and architectural patterns]

## Technical Product Characteristics
[Performance, scalability, security considerations from codebase]

## Integration Points
[External services, APIs, databases detected in codebase]
```

### 2. Technical Steering (tech.md)

#### Comprehensive Technology Analysis

!`echo "🔧 Technical Stack Analysis:"; echo "Dependencies Analysis:"; if [ -f "package.json" ]; then echo "Frontend Dependencies:"; cat package.json | jq -r '.dependencies, .devDependencies | keys[]?' 2>/dev/null | head -10 | sed 's/^/  - /'; fi; if [ -f "requirements.txt" ]; then echo "Python Dependencies:"; head -10 requirements.txt | sed 's/^/  - /'; fi`

#### Development Environment Detection

!`echo "🛠️ Development Environment:"; if [ -f "docker-compose.yml" ] || [ -f "Dockerfile" ]; then echo "- Docker containerization"; fi; if [ -f ".env.example" ] || [ -f ".env.template" ]; then echo "- Environment configuration"; fi; if [ -f "Makefile" ]; then echo "- Make build system"; fi; if [ -d ".github/workflows" ]; then echo "- GitHub Actions CI/CD"; fi; if [ -f "netlify.toml" ] || [ -f "vercel.json" ]; then echo "- Cloud deployment config"; fi`

#### Tech.md Generation/Update

**Approach**: Create detailed technical documentation from codebase analysis

Tech.md content framework:

```markdown
# Technical Architecture

## Technology Stack
[Complete stack analysis from package files and codebase]

## Development Environment
[Setup instructions based on detected tooling and configs]

## Architecture Patterns
[Patterns detected from code structure and organization]

## Development Commands
[Scripts and commands from package.json, Makefile, etc.]

## Dependencies and Integrations
[External dependencies, APIs, services from codebase analysis]

## Testing Strategy
[Testing frameworks and patterns detected in codebase]

## Deployment and Infrastructure
[Deployment configs, Docker, CI/CD detected]

## Performance Considerations
[Performance patterns and optimizations in current code]
```

### 3. Structure Steering (structure.md)

#### Project Structure Analysis

!`echo "📁 Directory Structure Analysis:"; find . -maxdepth 3 -type d | grep -v "node_modules\|\.git\|__pycache__\|\.next\|build\|dist" | head -20 | sed 's/^/  /'`

#### Code Organization Patterns

!`echo "🎯 Code Organization:"; if [ -d "src/components" ]; then COMPONENT_COUNT=$(find src/components -name "*.tsx" -o -name "*.jsx" -o -name "*.vue" | wc -l); echo "- React/Vue components: $COMPONENT_COUNT"; fi; if [ -d "src/pages" ] || [ -d "pages" ]; then PAGE_COUNT=$(find src/pages pages -name "*.tsx" -o -name "*.jsx" -o -name "*.vue" 2>/dev/null | wc -l); echo "- Page components: $PAGE_COUNT"; fi; if [ -d "src/api" ] || [ -d "api" ]; then API_COUNT=$(find src/api api -name "*.js" -o -name "*.ts" -o -name "*.py" 2>/dev/null | wc -l); echo "- API endpoints: $API_COUNT"; fi`

#### Structure.md Generation/Update

**Approach**: Document actual project organization and coding patterns

Structure.md content framework:

```markdown
# Project Structure

## Directory Organization
[Actual directory structure with explanations]

## Code Organization Patterns
[Patterns detected in component structure, module organization]

## File Naming Conventions
[Conventions derived from existing codebase analysis]

## Import/Export Patterns
[Module import patterns detected in codebase]

## Configuration Files
[Config files and their purposes in project]

## Testing Organization
[Test file organization and naming patterns]

## Asset Organization
[Static assets, images, styles organization]

## Documentation Structure
[Documentation files and organization patterns]
```

## Enhanced Steering Generation Process

### 1. Create Steering Directory

!`mkdir -p .kiro/steering`

### 2. Analyze Existing Steering Content

For update/refresh modes, preserve user customizations:
!`if [ -f ".kiro/steering/product.md" ]; then echo "📋 Existing product.md - will preserve custom content"; fi; if [ -f ".kiro/steering/tech.md" ]; then echo "🔧 Existing tech.md - will preserve custom content"; fi; if [ -f ".kiro/steering/structure.md" ]; then echo "📁 Existing structure.md - will preserve custom content"; fi`

### 3. Generate Comprehensive Steering Content

#### Product.md Enhanced Generation

Create or update product.md with codebase-informed content that preserves existing customizations while refreshing technical details.

#### Tech.md Enhanced Generation  

Create or update tech.md with current technology stack analysis, development environment, and architectural patterns detected from codebase.

#### Structure.md Enhanced Generation

Create or update structure.md with actual project organization, coding patterns, and conventions derived from codebase analysis.

### 4. Steering Quality Validation

!`echo "✅ Steering Validation:"; if [ -f ".kiro/steering/product.md" ]; then PRODUCT_SIZE=$(wc -l < .kiro/steering/product.md); echo "- product.md: $PRODUCT_SIZE lines"; fi; if [ -f ".kiro/steering/tech.md" ]; then TECH_SIZE=$(wc -l < .kiro/steering/tech.md); echo "- tech.md: $TECH_SIZE lines"; fi; if [ -f ".kiro/steering/structure.md" ]; then STRUCT_SIZE=$(wc -l < .kiro/steering/structure.md); echo "- structure.md: $STRUCT_SIZE lines"; fi`

### 5. Integration with Spec Workflow

Ensure steering documents are optimized for spec-driven development:

- Product context informs requirements generation
- Technical constraints guide design decisions  
- Structure patterns influence implementation tasks

## Steering Update Intelligence

### Change Detection

!`echo "🔍 Change Detection:"; if [ -d ".git" ]; then RECENT_CHANGES=$(git log --since="1 week ago" --oneline | wc -l); echo "- Recent commits (1 week): $RECENT_CHANGES"; if [ $RECENT_CHANGES -gt 10 ]; then echo "  - High activity - consider steering refresh"; fi; fi`

### Technology Evolution Check

!`echo "📈 Technology Evolution:"; if [ -f "package.json" ]; then NODE_VERSION=$(node --version 2>/dev/null || echo "unknown"); echo "- Node.js version: $NODE_VERSION"; fi; if [ -f "requirements.txt" ]; then PYTHON_VERSION=$(python --version 2>/dev/null || echo "unknown"); echo "- Python version: $PYTHON_VERSION"; fi`

### Steering Freshness Assessment

!`if [ -f ".kiro/steering/tech.md" ]; then STEERING_AGE=$(find .kiro/steering/tech.md -mtime +30 2>/dev/null && echo "older than 30 days" || echo "recent"); echo "📅 Steering age: $STEERING_AGE"; if [ "$STEERING_AGE" = "older than 30 days" ]; then echo "💡 Consider refreshing steering documents"; fi; fi`

## Instructions

### Execution Strategy

1. **Analyze project state** - Understand current codebase and steering status
2. **Select appropriate mode** - New, update, or refresh based on existing content
3. **Perform codebase analysis** - Extract technical details, patterns, and structure
4. **Generate/update content** - Create comprehensive steering while preserving customizations
5. **Validate quality** - Ensure steering documents are complete and accurate
6. **Integrate with workflow** - Connect steering to spec-driven development process

### Preservation Strategy

- **ALWAYS preserve user customizations** in existing steering documents
- **NEVER overwrite business context** that users have manually added
- **UPDATE technical details** based on current codebase analysis
- **ADD missing sections** without removing existing content
- **REFRESH outdated information** while maintaining user intent

### Quality Assurance

- Steering documents should be comprehensive and actionable
- Technical information should be current and accurate
- Project structure should reflect actual codebase organization
- Content should support spec-driven development workflow

Generate intelligent, codebase-informed steering documents that enhance the spec-driven development process while preserving valuable user customizations.
