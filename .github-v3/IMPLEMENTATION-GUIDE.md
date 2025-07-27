# Implementation Guide: Enhanced Spec-Driven Development v3

Complete implementation guide for deploying GitHub Copilot enhanced spec-driven development system.

## Prerequisites Setup

### Required Software

- **Visual Studio Code** 1.99 or later
- **GitHub Copilot Pro** subscription (for GPT-4o unlimited usage)
- **GitHub Copilot Chat** extension (latest version)

### Configuration Requirements

```json
// settings.json
{
  "chat.agent.enabled": true,
  "chat.promptFiles": true,
  "github.copilot.chat.codeGeneration.useInstructionFiles": true
}
```

### Optional Configuration

```json
// Additional settings for enhanced experience
{
  "chat.agent.maxRequests": 250,
  "github.copilot.chat.agent.autoFix": true
}
```

## Installation Steps

### Step 1: Directory Structure Setup

```bash
# In your project root
mkdir -p .github/chatmodes
mkdir -p .github/instructions  
mkdir -p .github/prompts
mkdir -p .spec-workflow/steering
mkdir -p .spec-workflow/specs
```

### Step 2: File Installation

Copy the following files to your project:

#### Chat Modes

```
.github/chatmodes/
├── spec-requirements.chatmode.md
├── spec-design.chatmode.md
├── spec-implementation.chatmode.md
└── spec-status.chatmode.md
```

#### Instructions Files

```
.github/instructions/
└── spec-driven-standards.instructions.md
```

#### Prompt Files (Optional)

```
.github/prompts/
├── spec-0-steering.prompt.md
├── spec-0-steering-custom.prompt.md
├── spec-1-init.prompt.md
├── spec-2-requirements.prompt.md
├── spec-3-design.prompt.md
├── spec-4-tasks.prompt.md
└── spec-5-status.prompt.md
```

### Step 3: VS Code Configuration

1. Open VS Code settings (`Cmd/Ctrl + ,`)
2. Search for "chat agent"
3. Enable "Chat: Agent Enabled"
4. Search for "prompt files"
5. Enable "Chat: Prompt Files"
6. Restart VS Code

## Usage Workflow

### Phase 1: Project Setup (Optional)

```
1. Open Chat view (Cmd/Ctrl + Shift + I)
2. Switch to any chat mode or use prompt: /spec-0-steering
3. Let AI analyze your project and create steering documents
4. Review generated steering documents in .spec-workflow/steering/
```

### Phase 2: Feature Initialization

```
1. Switch to any chat mode or use prompt: /spec-1-init
2. Provide detailed description: "Create user authentication with JWT..."
3. Review generated spec structure in .spec-workflow/specs/{feature}/
4. Verify feature name and project description
```

### Phase 3: Requirements Generation

```
Method 1 (Chat Mode - Recommended):
1. Switch to "spec-requirements" chat mode
2. Enter feature name
3. AI generates EARS-format requirements with optional research

Method 2 (Prompt File):
1. Use prompt: /spec-2-requirements feature=your-feature-name
2. AI generates requirements based on project context
```

**Post-Generation**:

- Review `requirements.md` for completeness
- Edit requirements as needed
- Update `spec.yaml`: set `approvals.requirements.approved: true`

### Phase 4: Technical Design

```
Method 1 (Chat Mode - Recommended):
1. Switch to "spec-design" chat mode
2. Enter feature name (requirements must be approved)
3. AI creates research-driven technical design

Method 2 (Prompt File):
1. Use prompt: /spec-3-design feature=your-feature-name
2. AI generates design based on approved requirements
```

**Post-Generation**:

- Review `design.md` for technical accuracy
- Validate architecture alignment
- Update `spec.yaml`: set `approvals.design.approved: true`

### Phase 5: Implementation Planning

```
Method 1 (Chat Mode - Recommended):
1. Switch to any chat mode
2. Use prompt: /spec-4-tasks feature=your-feature-name executionMode=multiple
3. AI generates hierarchical task plan

Method 2 (Chat Mode Variable):
1. Switch to any chat mode
2. Enter feature name and select execution mode
3. AI creates implementation tasks with requirement traceability
```

**Post-Generation**:

- Review `tasks.md` for completeness and sizing
- Validate requirement coverage
- Update `spec.yaml`: set `approvals.tasks.approved: true`

### Phase 6: Autonomous Implementation

```
Method 1 (Agent Mode - Recommended):
1. Switch to "spec-implementation" chat mode
2. Select execution mode (single/multiple tasks)
3. Enter feature name
4. AI executes tasks autonomously with validation loops

Method 2 (Manual Task Execution):
1. Use individual task commands for specific tasks
2. Monitor progress and validate manually
```

**During Implementation**:

- Monitor context usage (stay under 90k tokens)
- Let AI resolve issues automatically
- Review progress periodically

### Phase 7: Progress Tracking

```
1. Switch to "spec-status" chat mode
2. Enter feature name
3. Review comprehensive progress analysis
4. Address any identified blockers or issues
```

## Configuration Customization

### Instructions File Customization

Edit `.github/instructions/spec-driven-standards.instructions.md`:

```markdown
---
applyTo: ".spec-workflow/**/*"  # Apply to all spec files
description: "Your custom standards"
---

# Custom Standards
- Add your organization's specific requirements
- Include coding standards and conventions
- Define quality gates and validation criteria
```

### Chat Mode Customization

Modify chat modes in `.github/chatmodes/`:

#### Custom Tools Configuration

```markdown
---
tools: ['codebase', 'search', 'fetch', 'yourCustomTool']
model: Claude Sonnet 4
---
```

#### Custom Model Selection

```markdown
---
model: GPT-4o  # For implementation tasks
model: Claude Sonnet 4  # For analysis tasks
---
```

### Prompt File Customization

Edit prompt files in `.github/prompts/` for organization-specific needs:

- Add custom validation steps
- Include organization-specific templates
- Modify research requirements
- Adjust task generation rules

## Performance Optimization

### Context Management

```markdown
# Monitor token usage during agent mode
# Batch compatible tasks together
# Use incremental implementation approach
# Optimize for 90k token limit
```

### Interaction Efficiency

```markdown
# Use multiple task execution mode
# Group related tasks in single interaction
# Let agent mode iterate automatically
# Minimize manual intervention points
```

### Model Selection Strategy

```markdown
# Requirements & Design: Claude Sonnet 4 (analysis strength)
# Implementation: GPT-4o (unlimited usage, coding strength)
# Status & Review: Claude Sonnet 4 (analytical assessment)
```

## Quality Assurance

### Validation Checkpoints

1. **Requirements**: EARS format compliance, acceptance criteria coverage
2. **Design**: Architecture alignment, component completeness
3. **Tasks**: Requirement traceability, appropriate sizing
4. **Implementation**: Code quality, integration success

### Automatic Validation

The system includes automatic validation for:

- EARS format requirements
- Research citation format
- Task completion criteria
- Code integration quality

### Manual Review Points

- Requirements approval before design
- Design approval before tasks
- Tasks approval before implementation
- Progress validation during implementation

## Troubleshooting

### Common Issues and Solutions

#### Chat Mode Not Available

**Problem**: Chat modes don't appear in VS Code
**Solution**:

1. Verify files are in `.github/chatmodes/`
2. Restart VS Code
3. Check VS Code version (1.99+ required)

#### Instructions Not Applying

**Problem**: Automatic context injection not working
**Solution**:

1. Check `applyTo` glob patterns in instructions files
2. Verify `chat.promptFiles: true` in settings
3. Test with simple glob pattern first

#### Agent Mode Issues

**Problem**: Agent mode not executing autonomously
**Solution**:

1. Verify `chat.agent.enabled: true` in settings
2. Check tool availability in chat mode
3. Use appropriate model (GPT-4o for implementation)

#### Context Limit Exceeded

**Problem**: "Context too large" errors in agent mode
**Solution**:

1. Switch to single task execution mode
2. Reduce number of tasks in batch
3. Use incremental implementation approach

#### Research Tool Not Working

**Problem**: Fetch tool not finding information
**Solution**:

1. Check internet connectivity
2. Verify research query specificity
3. Use alternative research approaches

### Performance Issues

#### Slow Response Times

**Causes & Solutions**:

- Large context size → Reduce batch size
- Complex queries → Simplify task descriptions
- Network issues → Check connection stability

#### Quality Issues

**Causes & Solutions**:

- Vague requirements → Use more specific EARS format
- Missing context → Ensure steering documents exist
- Poor task sizing → Review and adjust task granularity

## Advanced Configuration

### Team Collaboration Setup

```markdown
# Shared workspace configuration
1. Commit .github/ directory to version control
2. Include .spec-workflow/ in project structure
3. Document team standards in steering documents
4. Train team members on workflow usage
```

### CI/CD Integration

```markdown
# Validation automation
1. Add spec validation to CI pipeline
2. Check EARS format compliance
3. Validate requirement coverage
4. Monitor implementation progress
```

### Custom Tool Integration

```markdown
# MCP server integration
1. Configure MCP servers for additional tools
2. Add tools to chat mode configurations
3. Update instructions for tool usage
4. Test tool integration with workflows
```

## Migration Guide

### From Previous Versions

1. **Backup existing configurations**
2. **Copy new chat modes and instructions**
3. **Update VS Code settings**
4. **Test workflow with sample feature**
5. **Train team on new capabilities**

### From Manual Processes

1. **Start with simple features**
2. **Gradually adopt full workflow**
3. **Customize for team needs**
4. **Measure productivity improvements**

## Support and Resources

### Documentation

- GitHub Copilot official documentation
- VS Code chat mode documentation
- Spec-driven development methodology

### Community

- GitHub discussions for Copilot
- VS Code community forums
- Internal team documentation

### Troubleshooting Resources

- VS Code developer tools
- Copilot status page
- Extension diagnostics

This implementation guide provides comprehensive setup and usage instructions for successful deployment of the enhanced spec-driven development system.
