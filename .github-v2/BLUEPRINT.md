# Transformation Blueprint: Claude Code Commands → GitHub Copilot Prompts

## Executive Summary

This blueprint documents the systematic transformation of Kiro-style Spec-Driven Development from Claude Code's `.claude/commands/` system to GitHub Copilot's `.github/prompts/` system. The goal is to preserve the original's elegant simplicity and expert efficiency while properly adapting to GitHub Copilot's platform capabilities.

**Result**: 7 clean, functional GitHub Copilot prompts optimized for GPT-4o that maintain the original's value proposition without feature creep.

---

## 🤖 Model Considerations (CRITICAL)

### GitHub Copilot Pro Plan Model Usage

**Base Model (Unlimited)**:

- **GPT-4o**: Unlimited usage, optimized for these prompts
- **Recommendation**: Use GPT-4o for all spec-driven development workflows

**Premium Models (Limited)**:

- **Other models**: 300 iterations per month limit for Pro plan
- **Risk**: Premium models will quickly exhaust limits during spec creation
- **Recommendation**: Avoid premium models for spec workflows

**Tested and Rejected**:

- **GPT-4.1**: Base model but unsuitable for these prompts (tested and confirmed)
- **Issue**: Poor performance on structured prompt execution
- **Recommendation**: Skip GPT-4.1 entirely

### Design Implications

1. **Optimize for GPT-4o**: All prompts designed for GPT-4o's capabilities and limitations
2. **Efficiency Focus**: Minimize token usage to respect context limits
3. **Clear Instructions**: GPT-4o performs best with explicit, structured guidance
4. **Iteration Friendly**: Support refinement without excessive token consumption

---

## 🎯 Strategic Learnings

### Critical Principles

1. **Preserve Elegant Simplicity**
   - Original Claude Code commands are expertly designed with minimal bloat
   - Expert developers need automation guidance, not hand-holding explanations
   - Clean, focused prompts outperform verbose mega-templates
   - **Concrete Example**: A 137-line requirements prompt is more effective than a 268-line bloated version

2. **Exact Content Preservation**
   - Original content structure must be preserved with zero modifications
   - No subtle differences, word changes, or additions are acceptable
   - Any deviation introduces unnecessary complexity
   - **Concrete Example**: Changing "Target Use Case" to "Target Use Cases" is unacceptable

3. **Platform Adaptation Precision**
   - GitHub Copilot has specific syntax requirements that must be followed exactly
   - Wrong file references or tool usage breaks functionality
   - Interactive input systems work well when implemented correctly
   - **Concrete Example**: `@filename.md` must become `[description](path)`, not `#filename`

4. **Resist Feature Creep Temptation**
   - Adding "helpful" explanations actually hurts expert efficiency
   - Template expansions create noise without value
   - Maintain laser focus on original functionality
   - **Warning Signs**: Adding sections like "Quality Guidelines", "Best Practices", or verbose examples

---

## ⚖️ Strategic Decisions for Transformation

### Architecture Decisions

| Aspect | Claude Code Original | GitHub Copilot Target | Rationale |
|--------|---------------------|----------------------|-----------|
| **Directory** | `.kiro/` | `.spec-workflow/` | Remove Kiro references, use generic naming |
| **File Format** | JSON | YAML | Better for GitHub Copilot, more readable |
| **Language Default** | Japanese | English | Broader accessibility while preserving i18n capability |
| **Target Model** | Claude | GPT-4o | Optimized for unlimited base model |
| **Target Audience** | Expert Developers | Expert Developers | Maintain efficiency over hand-holding |

### Technical Decisions

| Component | Claude Code Syntax | GitHub Copilot Syntax | Example |
|-----------|-------------------|----------------------|---------|
| **File References** | `@filename.md` | `[description](path)` | `[structure.md](../../.spec-workflow/steering/structure.md)` |
| **Parameters** | `$ARGUMENTS` | `${input:variable:placeholder}` | `${input:feature:Enter feature name}` |
| **Slash Commands** | `/spec-requirements feature` | `/spec-2-requirements: feature=name` | Proper GitHub Copilot syntax |
| **Automation** | `!command` | Tool guidance | `Use search tool to check directory` |
| **Language Field** | `"language": "japanese"` | `language: "english"` | Default English, preserve i18n |

---

## 🔧 Transformation Methodology

### Phase 1: Analysis & Understanding

1. **Read Original Command** - Understand exact structure, sections, and functionality
2. **Document Intent** - Capture the purpose and workflow of each section
3. **Identify Core Elements** - Extract essential logic and workflow requirements
4. **Map Automation Features** - Understand what the `!` commands and `@` references do
5. **Document Original Size** - Baseline for preventing feature creep (critical metric)

### Phase 2: Platform Mapping

1. **Syntax Conversion** - Map Claude Code syntax to GitHub Copilot equivalents
2. **Tool Identification** - Determine which GitHub Copilot tools replace shell commands
3. **Reference Adaptation** - Convert file references to proper GitHub Copilot format
4. **Interactive Elements** - Add appropriate input variables and refinement options
5. **Model Optimization** - Ensure prompts work well with GPT-4o

### Phase 3: Content Transformation

1. **Preserve Exact Structure** - Keep original section names and organization
2. **Adapt Technical Elements** - Convert syntax while preserving functionality
3. **Add Platform Features** - Include GitHub Copilot-specific enhancements
4. **Avoid Feature Creep** - Resist adding explanations or verbose templates
5. **Language Handling** - Set appropriate language field and maintain i18n capability

### Phase 4: Validation & Testing

1. **Size Verification** - Ensure target file sizes close to original (within 15%)
2. **Functionality Check** - Verify all original capabilities preserved
3. **Syntax Validation** - Confirm proper GitHub Copilot syntax throughout
4. **GPT-4o Testing** - Test prompts work correctly with GPT-4o model
5. **Expert Efficiency Test** - Ensure workflow remains streamlined

---

## 📋 Technical Implementation Guide

### File Structure Template

```yaml
---
description: [Original description adapted to GitHub Copilot context]
mode: agent
tools: ['search', 'codebase', 'editFiles']  # See tool selection guide below
---

# [Original Title]

[Core functionality from original - NO additions]

## [Original Section 1]
[Exact original content adapted to GitHub Copilot syntax]

## [Original Section 2]  
[Exact original content adapted to GitHub Copilot syntax]

## Refinement Options
[Interactive iteration menu - standardized addition for GitHub Copilot]

## Instructions
[Streamlined version of original instructions]
```

### GitHub Copilot Tool Selection Guide

| Tool | When to Use | Example Use Case | Always Include? |
|------|-------------|------------------|-----------------|
| `search` | Finding/checking files and directories | Directory analysis, file existence checks | ✅ Yes |
| `codebase` | Analyzing project structure and code | Understanding architecture, dependencies | ✅ Yes |
| `editFiles` | Creating or modifying files | Generating documents, updating metadata | ✅ Yes |
| `changes` | Analyzing recent changes | Status checking, change detection | ❌ Only for status prompts |
| `problems` | Error detection and diagnostics | Debugging, issue identification | ❌ Rarely needed |
| `runCommands` | Terminal command execution | Build, test, deployment tasks | ❌ Only if specifically needed |

**Standard Tool Array**: `['search', 'codebase', 'editFiles']` covers 90% of use cases.

### Critical Syntax Transformations

#### ✅ Correct GitHub Copilot Adaptations

```markdown
# File references (Claude Code → GitHub Copilot)
@.kiro/steering/tech.md → [tech.md](../../.spec-workflow/steering/tech.md)

# Interactive inputs (Claude Code → GitHub Copilot)  
$ARGUMENTS → ${input:feature:Enter feature name}

# Automation commands (Claude Code → GitHub Copilot)
!`ls -la .kiro/specs/` → Use `search` tool to check .spec-workflow/specs/ directory

# Directory paths (Claude Code → GitHub Copilot)
.kiro/specs/ → .spec-workflow/specs/

# Metadata format (Claude Code → GitHub Copilot)
spec.json → spec.yaml

# Language field (Claude Code → GitHub Copilot)
"language": "japanese" → language: "english"
```

#### ❌ Common Transformation Mistakes

```markdown
# Wrong file references (don't work in GitHub Copilot prompts)
#filename.md
#file:path (this is for workspace files, not prompt references)

# Wrong automation replacement (won't execute)
!`command` → Keep as shell command

# Wrong slash command format
/spec-requirements feature-name → /spec-2-requirements: feature=feature-name

# Inconsistent directory references
Mixing .kiro/ and .spec-workflow/ paths
```

### Language and Internationalization Handling

#### Language Field Configuration

```yaml
# Default (recommended)
language: "english"

# International projects
language: "japanese"  # or other supported language

# Template checking
# Always check spec.yaml for language field in prompts:
# "Generate [content] in the language specified in spec.yaml (check language field)"
```

#### Internationalization Patterns

```markdown
# Language-aware content generation
Create [document] in the language specified in spec.yaml (check language field):

# Language-specific progress tracking
## Progress Status (English default)
## 進捗状況 (Japanese when language: "japanese")

# Requirements mapping
_Requirements: 1.1, 1.2_ (English)
_要件: 1.1, 1.2_ (Japanese)
```

### Automation Adaptation Pattern

#### Claude Code Original

```bash
# Real-time execution capabilities
- Project files: !`find . -name "*.js"`
- File existence: !`[ -f "file.md" ] && echo "exists" || echo "missing"`
- Directory listing: !`ls -la .kiro/specs/`
- Spec status: !`grep -l "implementation_ready.*true" .kiro/specs/*/spec.json`
```

#### GitHub Copilot Adaptation

```markdown
# Tool-based guidance (maintains automation intent)
Use `search` tool to find JavaScript files (*.js)
Use `search` tool to check if file.md exists in directory
Use `search` tool to analyze .spec-workflow/specs/ directory structure
Use `search` tool to find specifications with ready_for_implementation: true
```

---

## 🚫 Feature Creep Prevention Guide

### Danger Signs During Transformation

1. **Template Expansion Temptation**
   - ❌ Adding verbose examples "to help users understand"
   - ❌ Creating detailed template documentation sections
   - ❌ Including best practices explanations
   - **Example**: 84-line "USER STORY TEMPLATE REFERENCE" sections are pure bloat

2. **Hand-Holding Language**
   - ❌ "I can iterate on this until you're satisfied" (already in refinement section)
   - ❌ Verbose explanations of concepts experts already know
   - ❌ Marketing language ("enterprise-grade", "robust", "production-ready")
   - **Example**: "This ensures quality requirements that serve as a solid foundation" is unnecessary

3. **Unnecessary Sections**
   - ❌ "Quality Guidelines" beyond original scope
   - ❌ "Implementation Instructions" when original has simple instructions
   - ❌ "Best Practices" sections not in original
   - **Example**: "Cross-Reference Navigation" sections are feature creep

### Size Control Guidelines

- **Target**: Stay within 15% of original file size
- **Warning**: 25% increase indicates potential feature creep
- **Danger**: 50%+ increase means major bloat has occurred
- **Red Alert**: 100%+ increase means complete transformation failure

### Acceptable vs Unacceptable Additions

#### ✅ Acceptable Additions (Platform Adaptation)

```markdown
# Interactive inputs for GitHub Copilot
${input:feature:Enter feature name}

# Standardized refinement options
## Refinement Options
What would you like me to refine...

# Tool usage guidance
Use `search` tool to check directory

# YAML metadata format
language: "english"
```

#### ❌ Unacceptable Additions (Feature Creep)

```markdown
# Verbose template documentation
## 📋 USER STORY TEMPLATE REFERENCE
_Use this template structure when generating requirements..._

# Hand-holding explanations
This approach ensures comprehensive coverage...

# Marketing language
enterprise-grade, production-ready, robust

# Unnecessary instruction sections
### Implementation Instructions
### Quality Guidelines
### Best Practices
```

---

## 📊 Quality Standards for Transformation

### Functionality Preservation Requirements

- **100% feature parity**: All original capabilities must be preserved
- **Zero feature loss**: No automation or analysis capabilities removed
- **Enhanced platform usage**: GitHub Copilot features used appropriately
- **Expert efficiency maintained**: Workflow remains streamlined
- **GPT-4o optimization**: Prompts work effectively with base model

### Content Standards

- **Exact structure**: Same section names and organization
- **Same quality level**: Maintain original's quality standards without additions
- **Expert focus**: Preserve efficiency over explanation
- **Language consistency**: Use specified language (English default, preserve i18n capability)
- **Token efficiency**: Minimize unnecessary content for GPT-4o

### Technical Standards

- **Correct syntax**: All GitHub Copilot references must work
- **Proper tool usage**: Use appropriate GitHub Copilot agent tools
- **File reference accuracy**: All paths must resolve correctly
- **Interactive elements**: Input variables implemented properly
- **Model compatibility**: Optimized for GPT-4o capabilities

---

## 🔬 Testing and Validation Guide

### Syntax Validation Checklist

- [ ] **File references**: All `[description](path)` links resolve correctly
- [ ] **Interactive inputs**: All `${input:variable}` syntax is proper
- [ ] **Tool references**: All tools in front matter are available
- [ ] **Slash commands**: All references use `/prompt: param=value` format
- [ ] **YAML syntax**: All metadata blocks are valid YAML

### Functional Testing Process

1. **GitHub Copilot Environment Test**
   - Create test workspace with prompt files
   - Verify prompts appear in GitHub Copilot
   - Test prompt execution with GPT-4o model

2. **File Reference Test**
   - Verify all linked files resolve
   - Check relative path accuracy
   - Test cross-references between prompts

3. **Interactive Input Test**
   - Verify input prompts appear correctly
   - Test with various input values
   - Check placeholder text displays

4. **Tool Functionality Test**
   - Verify `search` tool works for file checking
   - Test `codebase` tool for project analysis
   - Confirm `editFiles` tool for document creation

### Common Issues and Solutions

| Issue | Symptom | Solution |
|-------|---------|----------|
| **Broken file references** | Links don't resolve | Check relative paths from prompt location |
| **Tool not available** | Tool not found error | Verify tool name in GitHub Copilot |
| **Input syntax error** | Input prompt doesn't appear | Check `${input:variable:placeholder}` format |
| **YAML syntax error** | Front matter fails to parse | Validate YAML syntax |
| **Model incompatibility** | Poor prompt performance | Verify optimization for GPT-4o |

---

## 🔄 Step-by-Step Transformation Process

### For Each Claude Code Command File

1. **Analyze Original Structure**

   ```bash
   # Read the .claude/commands/kiro/[command].md file
   # Document: sections, size, automation features, file references, approval gates
   # Example: spec-requirements.md - 137 lines, 5 sections, 3 automation commands
   ```

2. **Create Front Matter**

   ```yaml
   ---
   description: [Adapt original description - keep concise]
   mode: agent
   tools: ['search', 'codebase', 'editFiles']  # Standard set for most prompts
   ---
   ```

3. **Transform Content Sections**
   - **Keep exact section names** and organization from original
   - **Adapt syntax** without changing content or intent
   - **Convert automation commands** to tool guidance
   - **Update file references** to proper GitHub Copilot format
   - **Add language field handling** for internationalization

4. **Add GitHub Copilot Enhancements**
   - **Interactive input variables** where original used `$ARGUMENTS`
   - **Standardized refinement options** section
   - **Tool usage guidance** replacing shell commands

5. **Validate Transformation**
   - **Size check**: Within 15% of original (137 lines → target ~140-155 lines)
   - **Syntax check**: All GitHub Copilot references work
   - **Functionality check**: All original capabilities preserved
   - **GPT-4o test**: Verify prompt works with base model

### Standardized Refinement Section Template

```markdown
## Refinement Options

What would you like me to refine about this [output type]?

- **Adjust [specific aspect]**: [Concrete modification option]?
- **Change [specific element]**: [Concrete modification option]?
- **Update [specific component]**: [Concrete modification option]?
- **Proceed if satisfied** with current [output type]?

I can iterate on this [output type] in our conversation until you're satisfied.
```

**Examples of Specific Refinement Options**:

- Requirements: "Adjust scope", "Modify detail level", "Change user focus"
- Design: "Update architecture", "Change technology choices", "Refine API design"
- Tasks: "Adjust phase breakdown", "Change task granularity", "Update time estimates"

---

## 📝 Complete Transformation Example: spec-requirements.md

### Original Claude Code Command (137 lines)

```markdown
---
description: Generate comprehensive requirements for a specification
allowed-tools: Bash, Read, Write, Edit, MultiEdit, Update, WebSearch, WebFetch
---

# Requirements Generation

Generate comprehensive requirements for feature: **$ARGUMENTS**

## Context Validation

### Steering Context
- Architecture context: @.kiro/steering/structure.md
- Technical constraints: @.kiro/steering/tech.md
- Product context: @.kiro/steering/product.md

### Existing Spec Context
- Current spec directory: !`ls -la .kiro/specs/$ARGUMENTS/`
- Current requirements: @.kiro/specs/$ARGUMENTS/requirements.md
- Spec metadata: @.kiro/specs/$ARGUMENTS/spec.json

## Task: Generate Detailed Requirements

Create comprehensive requirements document in the language specified in spec.json:

### 1. Requirements Structure
Generate requirements.md in the language specified in spec.json:

```markdown
# Requirements Specification

## Overview
[Clear overview of the feature and its purpose]

## Requirements

### Requirement 1
**User Story:** As a [user type], I want to [do something], so that I can [achieve some goal]

#### Acceptance Criteria
1. WHEN [specific condition] THEN [specific expected outcome]
2. WHEN [specific condition] THEN [specific expected outcome]
3. IF [exception condition] THEN [expected error handling]

### Requirement 2
[Additional requirements following same pattern]
```

### 2. Requirements Quality Guidelines

- **User-Centric**: Write from user perspective
- **Testable**: Each acceptance criterion should be verifiable
- **Specific**: Use concrete conditions and outcomes
- **Complete**: Cover all major user scenarios
- **Contextual**: Consider existing system integration

### 3. Integration Considerations

Based on steering context, consider:

- How this feature fits with existing architecture
- Technical constraints that affect requirements
- Existing user workflows that need integration
- Performance and scalability requirements

### 4. Update Metadata

Update spec.json with:

```json
{
  "phase": "requirements-generated",
  "progress": {
    "requirements": 100,
    "design": 0,
    "tasks": 0
  },
  "approvals": {
    "requirements": {
      "generated": true,
      "approved": false
    }
  },
  "updated_at": "current_timestamp"
}
```

[... rest of original continues for total 137 lines]

```

### Transformation Process Steps

1. **Front Matter Conversion**
   ```yaml
   # Original
   allowed-tools: Bash, Read, Write, Edit, MultiEdit, Update, WebSearch, WebFetch
   
   # GitHub Copilot
   mode: agent
   tools: ['search', 'codebase', 'editFiles']
   ```

2. **Parameter Conversion**

   ```markdown
   # Original
   Generate comprehensive requirements for feature: **$ARGUMENTS**
   
   # GitHub Copilot
   Generate comprehensive requirements for feature: **${input:feature:Enter feature name}**
   ```

3. **File Reference Conversion**

   ```markdown
   # Original
   - Architecture context: @.kiro/steering/structure.md
   
   # GitHub Copilot
   - Architecture context: [structure.md](../../.spec-workflow/steering/structure.md)
   ```

4. **Automation Command Conversion**

   ```markdown
   # Original
   - Current spec directory: !`ls -la .kiro/specs/$ARGUMENTS/`
   
   # GitHub Copilot
   - Current spec directory: Use `search` tool to check `.spec-workflow/specs/${input:feature}/`
   ```

5. **Metadata Format Conversion**

   ```yaml
   # Original (JSON)
   "phase": "requirements-generated"
   
   # GitHub Copilot (YAML)
   phase: "requirements-generated"
   ```

### Final GitHub Copilot Prompt (140 lines)

```markdown
---
description: Generate comprehensive requirements for a specification
mode: agent
tools: ['search', 'codebase', 'editFiles']
---

# Requirements Generation

Generate comprehensive requirements for feature: **${input:feature:Enter feature name}**

## Context Validation

### Steering Context
Reference steering documents if available:
- Architecture context: [structure.md](../../.spec-workflow/steering/structure.md)
- Technical constraints: [tech.md](../../.spec-workflow/steering/tech.md)
- Product context: [product.md](../../.spec-workflow/steering/product.md)

### Existing Spec Context
Verify the specification exists and is ready for requirements generation:
- Current spec directory: Use `search` tool to check `.spec-workflow/specs/${input:feature}/`
- Current requirements: [requirements.md](../../.spec-workflow/specs/${input:feature}/requirements.md)
- Spec metadata: [spec.yaml](../../.spec-workflow/specs/${input:feature}/spec.yaml)

## Task: Generate Detailed Requirements

Create comprehensive requirements document in the language specified in spec.yaml:

### 1. Requirements Structure
Generate requirements.md in the language specified in spec.yaml (check language field):

```markdown
# Requirements Specification

## Overview
[Clear overview of the feature and its purpose]

## Requirements

### Requirement 1
**User Story:** As a [user type], I want to [do something], so that I can [achieve some goal]

#### Acceptance Criteria
1. WHEN [specific condition] THEN [specific expected outcome]
2. WHEN [specific condition] THEN [specific expected outcome]
3. IF [exception condition] THEN [expected error handling]

### Requirement 2
**User Story:** As a [user type], I want to [do something], so that I can [achieve some goal]

#### Acceptance Criteria
1. WHEN [specific condition] THEN [specific expected outcome]
2. WHEN [specific condition] THEN [specific expected outcome]
3. IF [exception condition] THEN [expected error handling]

### Requirement 3
[Additional requirements following same pattern]
```

### 2. Requirements Quality Guidelines

- **User-Centric**: Write from user perspective
- **Testable**: Each acceptance criterion should be verifiable
- **Specific**: Use concrete conditions and outcomes
- **Complete**: Cover all major user scenarios
- **Contextual**: Consider existing system integration

### 3. Integration Considerations

Based on steering context, consider:

- How this feature fits with existing architecture
- Technical constraints that affect requirements
- Existing user workflows that need integration
- Performance and scalability requirements

### 4. Update Metadata

Update spec.yaml with:

```yaml
phase: "requirements-generated"
progress:
  requirements: 100
  design: 0
  tasks: 0
approvals:
  requirements:
    generated: true
    approved: false
updated_at: "{current_timestamp}"
```

### 5. Document Generation Only

Generate the requirements document content ONLY. Do not include any review or approval instructions in the actual document file.

## Refinement Options

What would you like me to refine about these requirements?

- **Adjust scope**: Add or remove requirement areas?
- **Modify detail level**: More detailed acceptance criteria or simpler stories?
- **Change user focus**: Different user types or personas?
- **Refine acceptance criteria**: More specific conditions or edge cases?
- **Update integration points**: Better alignment with existing systems?
- **Proceed if satisfied** with requirements?

I can iterate on the requirements in our conversation until you're satisfied.

## Human Review Process

After generation, the requirements must be reviewed and approved before proceeding to design:

1. **Human reviews** the generated requirements.md
2. **Manual edits** can be made directly to the file if needed
3. **Approval** is granted by manually updating spec.yaml:

   ```yaml
   approvals:
     requirements:
       generated: true
       approved: true
   phase: "requirements-approved"
   ```

4. **Only after approval** can /spec-3-design: feature={feature-name} be used

## Instructions

1. **Check spec.yaml for language** - Use the language specified in the metadata
2. **Analyze existing product context** to understand user needs
3. **Create user-focused requirements** with clear acceptance criteria
4. **Consider technical constraints** from steering documents
5. **Ensure requirements are testable** and specific
6. **Update tracking metadata** upon completion

Generate requirements that provide clear foundation for design phase.

```

### Key Changes Made
- **Size**: 137 → 140 lines (+2% - within target)
- **Syntax**: All GitHub Copilot syntax corrections
- **Tools**: Replaced shell commands with tool guidance
- **Format**: JSON → YAML metadata
- **Interactivity**: Added input variables and refinement options
- **Functionality**: 100% preserved, enhanced with platform features

---

## 📈 Expected Transformation Results

### File Size Targets by Prompt
| Original Command | Lines | Expected GitHub Copilot | Target Range | Rationale |
|------------------|-------|------------------------|--------------|-----------|
| `steering.md` | 171 | 140 | 135-155 | GitHub Copilot tools replace shell commands |
| `steering-custom.md` | 154 | 154 | 150-165 | Minimal changes needed |
| `spec-init.md` | 156 | 141 | 140-160 | Add interactive inputs |
| `spec-requirements.md` | 137 | 140 | 135-155 | Preserve template, add refinement |
| `spec-design.md` | 229 | 242 | 230-250 | Maintain all sections, correct syntax |
| `spec-tasks.md` | 277 | 290 | 275-295 | Complex approval gates preserved |
| `spec-status.md` | 96 | 112 | 95-115 | Simple status logic adaptation |

### Functionality Mapping Summary
- **Automation commands** (`!`) → GitHub Copilot tool guidance
- **File references** (`@`) → Markdown links with relative paths
- **Parameters** (`$ARGUMENTS`) → Interactive input variables
- **Workflow logic** → Preserved exactly with approval gates
- **Quality standards** → Maintained without additions
- **Language support** → Enhanced with proper i18n handling

---

## 🎯 Success Criteria Checklist

### Must Have ✅
- [ ] **Exact functionality parity** with original Claude Code command
- [ ] **Correct GitHub Copilot syntax** throughout file
- [ ] **File size within 15%** of original
- [ ] **Zero feature additions** not in original
- [ ] **All automation adapted** to GitHub Copilot tools
- [ ] **Expert workflow preserved** without hand-holding
- [ ] **GPT-4o optimization** for unlimited base model usage
- [ ] **Language field handling** for internationalization

### Must Avoid ❌
- [ ] **Template expansion** beyond original scope
- [ ] **Verbose explanations** for expert users
- [ ] **Broken file references** or syntax
- [ ] **Feature creep** of any kind
- [ ] **Hand-holding language** inappropriate for experts
- [ ] **Premium model dependencies** that exhaust usage limits

### Quality Gates ✔️
- [ ] **Side-by-side comparison** with original completed
- [ ] **All syntax validated** for GitHub Copilot compatibility
- [ ] **File references tested** and confirmed working
- [ ] **Size target achieved** (within 15% of original)
- [ ] **GPT-4o testing** completed successfully
- [ ] **Refinement options** tested for iteration capability

---

## 📚 Reference Implementation

The complete transformation results are available in `.github-v2/prompts/`:

| Original Command | GitHub Copilot Prompt | Key Transformations | Size Change |
|------------------|----------------------|--------------------|-----------| 
| `steering.md` (171) | `spec-0-steering.prompt.md` (139) | Shell commands → tool guidance | -19% |
| `steering-custom.md` (154) | `spec-0-steering-custom.prompt.md` (154) | File references → Markdown links | 0% |
| `spec-init.md` (156) | `spec-1-init.prompt.md` (141) | Parameters → interactive inputs | -10% |
| `spec-requirements.md` (137) | `spec-2-requirements.prompt.md` (140) | Template preserved, syntax corrected | +2% |
| `spec-design.md` (229) | `spec-3-design.prompt.md` (242) | Approval gates maintained | +6% |
| `spec-tasks.md` (277) | `spec-4-tasks.prompt.md` (290) | Task format preserved exactly | +5% |
| `spec-status.md` (96) | `spec-5-status.prompt.md` (112) | Status logic adapted to tools | +17% |

**Overall Result**: 7 clean prompts optimized for GPT-4o with original functionality preserved and expert efficiency maintained.

---

## 🏁 Conclusion

This blueprint provides a complete methodology for transforming Claude Code commands to GitHub Copilot prompts while maintaining their elegant simplicity and expert focus. The key principles:

1. **Preserve original value** while adapting to new platform capabilities
2. **Optimize for GPT-4o** to avoid premium model usage limits
3. **Resist feature creep** at every stage of transformation
4. **Maintain expert efficiency** without hand-holding explanations

Success requires discipline to resist feature additions and focus on correct platform adaptation. The result is a GitHub Copilot implementation that serves expert developers effectively while leveraging GPT-4o's unlimited availability in the Pro plan.

**Follow this blueprint to create clean, functional GitHub Copilot prompts that honor the original Claude Code design while maximizing GitHub Copilot's capabilities appropriately.**
