---
description: EARS format and requirements quality standards
applyTo: ".spec-workflow/**/requirements.md"
---

# Requirements Standards

Standards for generating requirements documents in the spec-driven development workflow.

## EARS Format Requirements

### Mandatory Format

- **MUST use EARS format**: WHEN [condition] THEN [response]
- **Alternative format**: GIVEN [context] WHEN [action] THEN [outcome]
- **MUST provide testable acceptance criteria** for each requirement
- **MUST reference existing system capabilities** when relevant

### Example EARS Formats

```
WHEN user clicks "Submit" button AND all required fields are filled THEN system processes the request
GIVEN user is authenticated WHEN user accesses protected resource THEN system grants access
WHEN invalid data is submitted THEN system displays specific error message and highlights problematic fields
```

## Requirements Quality

### Content Standards

- **Use specific, measurable conditions**
- **Avoid ambiguous language** ("user-friendly", "fast", "intuitive")
- **Include error conditions and edge cases**
- **Reference existing system behavior for consistency**
- **Write from user perspective**
- **Ensure each acceptance criterion is verifiable**

These standards ensure requirements use consistent, testable EARS format across all specifications.
