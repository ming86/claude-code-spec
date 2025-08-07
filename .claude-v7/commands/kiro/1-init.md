---
description: "Kiro Feature Initialization: Generate feature name from description and create project structure"
argument-hint: "feature-description (natural language)"
---

# Kiro Feature Initialization

## 1. Feature Description Input & Validation

**Please provide a description of the feature you want to develop:**

**Examples:**

- "User authentication system" → `user-auth`
- "Payment processing dashboard" → `payments-processing`  
- "Real-time chat messaging" → `real-time-chat`
- "File upload service" → `file-uploads`
- "Customer relationship management" → `crm`

**What feature would you like to create?**

If you didn't provide a description, please describe your feature now.

[Wait for user to provide feature description]

---

Once you provide a feature description, I'll continue with name generation and setup.

## 2. Feature Name Generation & Validation

**Analyzing your feature description:** "$ARGUMENTS"

**Generating SHORT kebab-case feature name...**

Based on your description, I'm generating the feature name: **`${generated-feature-name}`**

**Name Generation Logic:**

- Extract 2-3 key concepts maximum
- Keep under 25 characters when possible  
- Prioritize memorability and typing ease
- Follow pattern: `^[a-z0-9-]+$`

**Checking if this name is available...**

!ls .kiro/specs/ 2>/dev/null | grep -E "^${generated-feature-name}$" && echo "EXISTS" || echo "AVAILABLE"

**Name Availability Check:**

[If name exists, generate alternative with `-v2` or `-alt` suffix]

**Final feature name:** `${final-feature-name}`

## 3. Project Structure & Steering Validation

**Checking project structure and steering setup...**

!test -d ".kiro" && echo "KIRO_DIR_EXISTS" || echo "KIRO_DIR_MISSING"
!test -d ".kiro/specs" && echo "SPECS_DIR_EXISTS" || echo "SPECS_DIR_MISSING"  
!ls .kiro/steering/ 2>/dev/null | grep -E "(product|tech|structure)\.md" | wc -l

## Project Structure & Steering Check

**Project Structure:** [Creating .kiro structure if needed]

**Steering Documents Check:**

[If steering documents found:]
✅ **Steering documents detected** - Great! These will enhance your workflow quality.

[If no steering documents found:]
⚠️  **No steering documents found**

**Recommendation**: Set up steering documents for better results:

- `/kiro:0-steering` - Create core steering (product.md, tech.md, structure.md)  
- `/kiro:0-steering-custom` - Add domain-specific guidance

**Steering provides:**

- Project context and standards
- Technical constraints and patterns  
- Better requirement generation quality

**You can proceed without steering, but results will be more generic.**

**Options:**

- **Continue without steering**: Say "proceed" to continue
- **Set up steering first**: Run `/kiro:0-steering` then come back

**What would you like to do?**

[Wait for user decision - "proceed" or steering setup]

---

## 4. Feature Initialization

**Creating feature:** `${final-feature-name}`  
**Description:** `${feature-description}`

**Creating directory structure and initial state...**

**Creating project structure:**

- Ensuring `.kiro/` directory exists
- Creating `.kiro/specs/` if needed  
- Creating `.kiro/specs/${final-feature-name}/` directory
- Generating initial spec.yaml file

**Generating spec.yaml with initial state...**

**SPEC.YAML TEMPLATE:**

```yaml
feature_name: "${final-feature-name}"
feature_description: "${feature-description}"
created_at: "${current-timestamp}"
updated_at: "${current-timestamp}"
approvals:
  requirements:
    generated: false
    approved: false
  design:
    generated: false
    approved: false
  tasks:
    generated: false
    approved: false
```

[Create the actual spec.yaml file with generated content]

## 5. Structure Validation Framework

**Executing initialization validation checkpoints...**

### Directory Structure Validation

- Check: `.kiro/` directory exists and is accessible
- Check: `.kiro/specs/` directory exists and is writable  
- Check: `.kiro/specs/${final-feature-name}/` directory created successfully
- Check: Directory has proper permissions

### File Creation Validation

- Check: `spec.yaml` created at `.kiro/specs/${final-feature-name}/spec.yaml`
- Check: YAML file is valid and parseable
- Check: All required fields present with correct data types
- Check: Timestamps in proper ISO 8601 format
- Check: Feature name matches kebab-case pattern
- Check: Description preserved accurately

### State Initialization Validation

- Check: All approval states initialized to `false`
- Check: Generated/approved flags consistent  
- Check: YAML structure matches expected schema
- Check: File is readable for future workflow stages

**Structure Validation Results:**

**Kiro Feature Initialization Validation:**

- **Directory Creation**: `.kiro/specs/${final-feature-name}/` created successfully
- **State File Creation**: `spec.yaml` generated with proper structure
- **YAML Format Validation**: All fields present and properly formatted
- **Permissions Check**: Files accessible for workflow progression
- **Schema Compliance**: Structure matches Kiro requirements
- **Timestamp Validation**: Creation timestamps properly formatted

**Overall Initialization Status: Complete and Ready for Workflow**

## 6. Setup Review & Confirmation

## Feature Initialization Complete

**Created Structure:**

- **Feature Name**: `${final-feature-name}`
- **Feature Directory**: `.kiro/specs/${final-feature-name}/`
- **State File**: `.kiro/specs/${final-feature-name}/spec.yaml`

**Initial Configuration:**

```yaml
feature_name: "${final-feature-name}"
feature_description: "$ARGUMENTS"
created_at: "${current-timestamp}"
updated_at: "${current-timestamp}"
approvals:
  requirements:
    generated: false
    approved: false
  design:
    generated: false
    approved: false
  tasks:
    generated: false
    approved: false
```

**Project Status:**

- **Feature**: `${final-feature-name}`
- **Description**: [Your original description]
- **Status**: Initialized and ready for requirements clarification
- **All Approval Gates**: Ready for workflow progression
- **Steering Context**: [Available/Recommended - based on setup]

**Setup Quality**: All validation checkpoints passed successfully

## 7. Final Confirmation & Next Steps

## Setup Successful

**Feature "`${final-feature-name}`" has been initialized successfully!**

**Final Deliverables:**

- **Feature Directory**: `.kiro/specs/${final-feature-name}/` (created)
- **State Tracking**: `spec.yaml` (initialized with proper structure)  
- **Workflow Status**: Ready for Stage 1 (Requirements Clarification)

### Next Steps

Ready to start **Stage 1: Requirements Clarification**? Run:

```
/kiro:2-requirements-clarification ${final-feature-name}
```

**Important**: Remember to use `${final-feature-name}` for all future commands with this feature.

**Available Workflow Commands:**

- `/kiro:2-requirements-clarification ${final-feature-name}` - Generate comprehensive requirements
- `/kiro:6-status ${final-feature-name}` - Check feature progress and status

**Kiro Feature Initialization Complete!**
