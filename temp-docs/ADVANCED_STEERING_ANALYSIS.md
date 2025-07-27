# Advanced Steering System: Missing Features Analysis

## Documentation Sources and Methodology

This analysis compares GitHub v3 and Claude v2 implementations against the original Kiro system based on:

**Primary Sources**:
- `/amazon-kiro.kiro-agent-source-code-analysis/kiro-spec-driven-development-system/03-steering-system.md`
- `/amazon-kiro.kiro-agent-source-code-analysis/kiro-spec-driven-development-system/06-integration-architecture.md`
- `/amazon-kiro.kiro-agent-source-code-analysis/kiro-spec-driven-development-system/02-workflow-stages.md`

**Supporting Sources**:
- `/amazon-kiro.kiro-agent-source-code-analysis/kiro-spec-driven-development-system/01-system-overview.md`
- `/amazon-kiro.kiro-agent-source-code-analysis/kiro-spec-driven-development-system/README.md`
- `/amazon-kiro.kiro-agent-source-code-analysis/kiro-spec-driven-development-system/02-workflow-stages/stage-4-spec-task-execution.md`

**Analysis Method**: Direct extraction from source documentation vs. elaborated examples

**Legend:**

- **[FROM ORIGINAL]**: Direct concepts, structures, or quotes from Kiro documentation
- **[ELABORATED]**: Technical extrapolations based on documented architecture
- **[EXAMPLE]**: Implementation examples based on documented templates

---

## Current Implementation Status

### What Both Implementations Have

```yaml
Basic Steering (Always Included):
- product.md: Product context and business objectives
- tech.md: Technology stack and architectural decisions  
- structure.md: File organization and code patterns
```

### Missing Elements **[FROM ORIGINAL]**

```yaml
Advanced Features from 03-steering-system.md:
- Conditional loading based on file patterns
- Manual reference system (@filename.md syntax)
- Custom steering domains
- Dynamic context updates
- Pattern configuration management
- /kiro:steering-custom command

Integration Features from 06-integration-architecture.md:
- VS Code extension custom file schemes (kiro-spec, kiro-meta, kiro-diff)
- Webview components (Spec Explorer, Hook Editor, Steering Explorer)
- Hook system integration (FileEditedHook, FileCreatedHook, etc.)
- MCP server configuration (.kiro/settings/mcp.json)

Behavioral Constraints from 02-workflow-stages.md:
- Single-task execution focus ("MUST focus on ONE task at a time")
- Explicit approval gates with userInput tool integration
```

---

## Missing Feature 1: Three-Mode Inclusion Architecture **[FROM ORIGINAL]**

### Architecture Overview **[FROM ORIGINAL]**

Original documentation defines three inclusion modes:

1. **Always Included Mode**: "Universal Context - Loaded in every interaction without exception"
2. **Conditional Inclusion Mode**: "Pattern-Based Loading - Documents loaded when file patterns match"  
3. **Manual Inclusion Mode**: "Explicit Reference System - Documents loaded only when explicitly referenced"

### Mode 1: Always Included (Current Implementation)

**[FROM ORIGINAL]**: Core documents automatically loaded:

- product.md: Product overview, features, use cases, value proposition
- tech.md: Architecture, tech stack, development environment, commands, ports
- structure.md: Directory organization, code patterns, naming conventions

### Mode 2: Conditional Inclusion **[FROM ORIGINAL]**

**Original Documentation Quote**:
> "Pattern-Based Loading: Documents loaded when file patterns match"
> "Context Activation: Relevant steering activated by current work context"

**Configuration Structure** **[FROM ORIGINAL]**:

```javascript
{
  "api-standards.md": {
    "patterns": ["src/api/**/*", "**/*api*"],
    "description": "API design guidelines"
  },
  "testing-approach.md": {
    "patterns": ["**/*.test.*", "**/spec/**/*"],
    "description": "Testing conventions"
  }
}
```

### Mode 3: Manual Inclusion **[FROM ORIGINAL]**

**Original Documentation Quote**:
> "Explicit Reference System: Documents loaded only when explicitly referenced"
> "Syntax-Based Activation: @filename.md syntax triggers loading"

**Use Cases** **[FROM ORIGINAL]**:

- Security Reviews: Load security policies only during security work
- Performance Optimization: Load performance standards during optimization tasks
- Specialized Workflows: Load domain-specific guidance for specialized work

---

## Missing Feature 2: Custom Steering Domains **[FROM ORIGINAL]**

### Original Kiro Custom Steering Categories **[FROM ORIGINAL]**

From `03-steering-system.md`, Section "Specialized Steering Categories":

```
Specialized Steering Categories:
├── API Standards: API design guidelines and conventions
├── Testing Approaches: Testing strategies and framework standards
├── Code Style Guidelines: Coding standards and style enforcement
├── Security Policies: Security implementation requirements and practices
├── Database Conventions: Data modeling and database interaction patterns
├── Performance Standards: Performance requirements and optimization guidelines
├── Deployment Workflows: Deployment processes and environment management
```

**File Organization** **[FROM ORIGINAL]** (from `README.md`):
```
.kiro/
├── specs/{feature_name}/
│   ├── requirements.md      # EARS format requirements with user stories
│   ├── design.md           # Architecture and component specifications
│   └── tasks.md            # Numbered checkbox implementation tasks
├── steering/
│   ├── product.md          # Product context and business objectives
│   ├── tech.md             # Technology stack and architecture
│   ├── structure.md        # Code organization and patterns
│   └── {custom}.md         # Specialized steering documents
└── settings/
    └── mcp.json            # MCP server configuration
```

### Custom Document Structure Template **[FROM ORIGINAL]**

Original documentation provides this template:

```markdown
# {Domain} Steering Document

## Overview
Domain-specific context and objectives

## Standards  
Specific standards and requirements

## Guidelines
Implementation guidelines and best practices

## Examples
Concrete examples and reference implementations

## Validation
Quality criteria and validation methods
```

### Domain-Specific Examples **[EXAMPLE]**

**Note**: The following are implementation examples based on the documented template structure, not direct content from original documentation.

#### API Standards Document **[EXAMPLE]**

```markdown
# API Standards Steering

## Overview
RESTful API design standards for consistent, maintainable APIs

## Standards
- Use HTTP status codes correctly (200, 201, 400, 401, 404, 500)
- Implement consistent error response format
- Use semantic versioning for API versions
- Follow REST resource naming conventions

## Guidelines
- Use plural nouns for resource endpoints (/users, /orders)
- Implement proper authentication and authorization
- Include rate limiting and throttling
- Provide comprehensive API documentation

## Examples
```javascript
// RESTful resource naming
GET /api/v1/users
POST /api/v1/users  
PUT /api/v1/users/{id}
DELETE /api/v1/users/{id}

// Error response format
{
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Invalid input data",
    "details": [...]
  }
}
```

## Validation

- All endpoints must have OpenAPI documentation
- Error responses must follow standard format
- Rate limiting must be implemented
- Authentication required for all protected endpoints

```

#### Testing Approach Document **[EXAMPLE]**
```markdown
# Testing Approach Steering

## Overview
Comprehensive testing strategy ensuring code quality and reliability

## Standards
- Minimum 80% code coverage for new code
- Unit tests for all business logic
- Integration tests for API endpoints
- E2E tests for critical user flows

## Guidelines
- Follow AAA pattern (Arrange, Act, Assert)
- Use descriptive test names that explain behavior
- Mock external dependencies in unit tests
- Use test data factories for consistent test setup

## Examples
```javascript
// Descriptive test name and AAA pattern
describe('UserService', () => {
  it('should create user with valid email and return user object', async () => {
    // Arrange
    const userData = { email: 'test@example.com', name: 'Test User' };
    
    // Act
    const result = await userService.createUser(userData);
    
    // Assert
    expect(result).toHaveProperty('id');
    expect(result.email).toBe(userData.email);
  });
});
```

## Validation

- All tests must pass before deployment
- Coverage reports generated for each PR
- Integration tests run in CI/CD pipeline
- Performance tests for critical endpoints

```

---

## Missing Feature 3: Dynamic Context Management **[FROM ORIGINAL]**

### Pattern-Based Loading Configuration **[ELABORATED]**

Based on documented pattern matching system:
```yaml
# Front-matter configuration in steering documents
---
applyTo: 
  - "src/api/**/*"
  - "**/*api*"
  - "**/routes/**/*"
  - "**/controllers/**/*"
description: "API design guidelines and conventions"
mode: "conditional"
priority: "high"
tags: ["api", "backend", "rest"]
---

# API Standards Document
[Document content follows...]
```

### Dynamic Context Updates **[FROM ORIGINAL]**

Original documentation describes (from `03-steering-system.md`, Section "Dynamic Context Updates"):
> "File Change Detection: System detects file context changes"
> "Pattern Re-evaluation: File patterns re-analyzed for steering requirements"
> "Context Adjustment: Steering context updated based on new patterns"
> "Knowledge Synchronization: Project knowledge synchronized with current context"

**Technical Implementation** **[ELABORATED]**:

```
1. File Change Detection
   → System detects when user switches files or creates new files

2. Pattern Re-evaluation  
   → File patterns analyzed against all conditional steering documents

3. Context Adjustment
   → Steering context updated to include/exclude relevant documents

4. Knowledge Synchronization
   → Project knowledge synchronized with current work context
```

---

## Missing Feature 4: Advanced Management Commands **[FROM ORIGINAL]**

### `/kiro:steering-custom` Command **[FROM ORIGINAL]**

Original documentation describes:
> "Specialized steering document creation"
> "Domain-Specific Creation: Creates steering for specialized contexts"
> "Pattern Configuration: Sets up conditional loading patterns"

**Current Implementation**:

```bash
# Both implementations only have:
/kiro:steering  # Basic steering management
```

**Missing Command** **[FROM ORIGINAL]**:

```bash
/kiro:steering-custom <domain>  # Create domain-specific steering
```

**Command Workflow** **[FROM ORIGINAL]** (from `03-steering-system.md`, Section "Custom Steering Workflow"):

1. Domain Identification: Identify specific domain requiring steering
2. Template Selection: Choose appropriate template for domain
3. Pattern Configuration: Set up file pattern matching for automatic loading
4. Integration Validation: Ensure custom steering integrates with core system

---

## Missing Feature 5: Context Integration Analysis **[ELABORATED]**

### Workflow Comparison Analysis

#### API Development Workflow **[ELABORATED]**

**Current Behavior (Both Implementations)**:

```
1. Developer works on src/api/users.js
2. Loads: product.md + tech.md + structure.md (generic context)
3. No API-specific guidance provided
4. Developer must manually reference API conventions
```

**Advanced Steering Behavior (Based on documented patterns)**:

```
1. Developer works on src/api/users.js  
2. Pattern "src/api/**/*" detected
3. Loads: product.md + tech.md + structure.md + api-standards.md
4. Provides: API conventions, error handling patterns, validation rules
5. Context optimized for API development decisions
```

#### Security Review Workflow **[ELABORATED]**

**Current Behavior (Both Implementations)**:

```
1. Security review of authentication code
2. Generic steering provides no security-specific guidance
3. Security expert must manually provide security context
```

**Advanced Steering Behavior (Based on manual reference system)**:

```
1. Security review: @security-policies.md referenced
2. Loads: security checklist, vulnerability patterns, compliance requirements
3. Provides: specific security validation criteria
4. Context optimized for security analysis and recommendations
```

---

## Implementation Gap Analysis

### GitHub v3 Current Implementation

```
✅ Basic steering: product.md, tech.md, structure.md (Always Included mode)
❌ Pattern-based conditional loading
❌ Manual reference system (@filename.md)
❌ Custom steering domains
❌ Dynamic context updates
❌ Pattern configuration in front-matter
❌ /kiro:steering-custom command
```

### Claude v2 Current Implementation  

```
✅ Basic steering: product.md, tech.md, structure.md (Always Included mode)
❌ Pattern-based conditional loading
❌ Manual reference system (@filename.md)  
❌ Custom steering domains
❌ Dynamic context updates
❌ /kiro:steering-custom command
❌ Steering configuration management
```

---

## Technical Implementation Requirements

### Phase 1: Pattern-Based Loading **[ELABORATED]**

```yaml
Priority: High
Effort: Medium

Technical Requirements:
1. Add front-matter parsing to steering documents
2. Implement pattern matching against current file context
3. Load conditional steering documents based on patterns
4. Integrate with existing steering loading mechanism

Implementation Notes:
- Requires file system monitoring for current work context
- Pattern matching against glob patterns
- Dynamic document loading and unloading
```

### Phase 2: Manual Reference System **[ELABORATED]**

```yaml
Priority: Medium  
Effort: Low

Technical Requirements:
1. Add @filename.md syntax recognition in prompts
2. Implement on-demand document loading
3. Integrate with existing steering loading mechanism
4. Maintain reference tracking for loaded documents

Implementation Notes:
- Syntax parsing in chat input
- Dynamic document resolution
- Memory management for loaded references
```

### Phase 3: Custom Steering Management **[ELABORATED]**

```yaml
Priority: Medium
Effort: High

Technical Requirements:
1. Create /kiro:steering-custom command implementation
2. Implement domain template system
3. Add pattern configuration management
4. Integrate with existing steering system
5. Provide template selection interface

Implementation Notes:
- Command infrastructure extension
- Template system for domain types
- Configuration file management
- Integration testing with existing commands
```

---

## Conclusion

The Advanced Steering System represents a documented architecture from the original Kiro system that both GitHub v3 and Claude v2 implementations currently lack. The missing features include:

**Documented Missing Features** **[FROM ORIGINAL]**:

- Three-mode inclusion architecture (Always/Conditional/Manual)
- Pattern-based conditional loading
- Manual reference system with @filename.md syntax
- Custom steering domains for specialized contexts
- Dynamic context management
- Advanced steering management commands

**Implementation Impact** **[ELABORATED]**:

- Context loading limited to basic always-included documents
- No domain-specific guidance automation
- Manual context management required for specialized work
- Reduced efficiency in context utilization

The gap represents missing functionality that would provide context-aware project guidance at the level of sophistication present in the original Kiro system documentation.
