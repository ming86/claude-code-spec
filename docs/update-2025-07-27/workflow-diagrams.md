# Claude Code v1 vs v2 Workflow Diagrams

## Overview

This document provides detailed mermaid diagrams illustrating the key workflow differences between Claude Code v1 and v2 implementations.

## 1. High-Level Architecture Comparison

### v1 Architecture (Interactive Approval)

```mermaid
graph TB
    subgraph "Claude Code v1"
        A[User Input] --> B[spec-init]
        B --> C[spec-requirements]
        C --> D[Interactive Approval<br/>Japanese Prompts]
        D --> E[spec-design]
        E --> F[Interactive Approval<br/>Japanese Prompts]
        F --> G[spec-tasks]
        G --> H[Interactive Approval<br/>Japanese Prompts]
        H --> I[Manual Implementation]
    end
    
    style D fill:#FFE5CC
    style F fill:#FFE5CC
    style H fill:#FFE5CC
    style I fill:#FFCCCC
```

### v2 Architecture (EARS + Research + Multi-Task)

```mermaid
graph TB
    subgraph "Claude Code v2"
        A[User Input] --> B[Enhanced spec-init<br/>Codebase Analysis]
        B --> C[EARS spec-requirements<br/>+ Optional Research]
        C --> D[Manual Review<br/>spec.json Edit]
        D --> E[Research-Informed<br/>spec-design]
        E --> F[Manual Review<br/>spec.json Edit]
        F --> G[Multi-Task<br/>spec-tasks]
        G --> H[Manual Review<br/>spec.json Edit]
        H --> I[execute-tasks<br/>AI Validation Loops]
        I --> J[Self-Correcting<br/>Implementation]
    end
    
    style B fill:#E5F3FF
    style C fill:#E5F3FF
    style E fill:#E5F3FF
    style G fill:#E5F3FF
    style I fill:#CCE5FF
    style J fill:#CCE5FF
```

## 2. Detailed Phase Flow Comparison

### v1 Phase Flow

```mermaid
sequenceDiagram
    participant U as User
    participant SI as spec-init
    participant SR as spec-requirements
    participant SD as spec-design
    participant ST as spec-tasks
    participant I as Implementation
    
    U->>SI: Project description
    SI->>SI: Basic feature name generation
    SI-->>U: Template files created
    
    U->>SR: Generate requirements
    SR->>SR: Basic requirements
    SR-->>U: requirements.md
    
    U->>SD: Generate design
    SD->>U: "requirements.mdをレビューしましたか？ [y/N]"
    U->>SD: y
    SD->>SD: Auto-approve requirements
    SD->>SD: Generate design
    SD-->>U: design.md
    
    U->>ST: Generate tasks
    ST->>U: Interactive prompts for approval
    U->>ST: y
    ST->>ST: Auto-approve phases
    ST->>ST: Generate tasks
    ST-->>U: tasks.md
    
    U->>I: Manual implementation
    I-->>U: Completed feature
```

### v2 Phase Flow

```mermaid
sequenceDiagram
    participant U as User
    participant SI as Enhanced spec-init
    participant SR as EARS Requirements
    participant R as Research Engine
    participant SD as Research Design
    participant ST as Multi-Task Tasks
    participant ET as execute-tasks
    participant V as AI Validator
    
    U->>SI: Project description
    SI->>SI: Codebase analysis
    SI->>SI: Technology detection
    SI->>SI: Pattern recognition
    SI-->>U: Enhanced templates
    
    U->>SR: Generate EARS requirements
    SR->>R: Optional research
    R-->>SR: Research findings
    SR->>SR: EARS format generation
    SR-->>U: EARS requirements.md
    
    U->>U: Manual review & spec.json edit
    
    U->>SD: Generate design
    SD->>R: Research integration
    R-->>SD: Technical documentation
    SD->>SD: Research-informed design
    SD-->>U: Enhanced design.md
    
    U->>U: Manual review & spec.json edit
    
    U->>ST: Generate tasks
    ST->>ST: Multi-task structure
    ST->>ST: EARS traceability
    ST-->>U: Multi-task tasks.md
    
    U->>U: Manual review & spec.json edit
    
    U->>ET: Execute implementation
    loop Task Execution
        ET->>ET: Execute task
        ET->>V: Validate implementation
        V-->>ET: Validation result
        alt Validation fails
            ET->>ET: Self-correcting fixes
        else Validation passes
            ET->>ET: Next task
        end
    end
    ET-->>U: Completed feature
```

## 3. Approval Workflow Comparison

### v1 Interactive Approval

```mermaid
flowchart TD
    A[Generate Document] --> B{Interactive Prompt<br/>Japanese Text}
    B -->|User: 'y'| C[Auto-Approve in spec.json]
    B -->|User: 'N'| D[Stop Execution]
    C --> E[Proceed to Next Phase]
    D --> F[User Manual Review]
    F --> G[User Edit spec.json]
    G --> E
    
    style B fill:#FFE5CC
    style C fill:#E5FFCC
    style D fill:#FFCCCC
```

### v2 Manual Approval

```mermaid
flowchart TD
    A[Generate Document] --> B[Document Ready]
    B --> C[User Reviews Document]
    C --> D{User Decision}
    D -->|Approve| E[User Edits spec.json<br/>approved: true]
    D -->|Needs Changes| F[User Edits Document]
    F --> C
    E --> G[Proceed to Next Phase]
    
    style C fill:#E5F3FF
    style E fill:#CCE5FF
    style F fill:#FFE5CC
```

## 4. Requirements Methodology Comparison

### v1 Requirements Format

```mermaid
graph LR
    A[User Input] --> B[Basic Processing]
    B --> C[User Story Format]
    C --> D[Simple Structure]
    D --> E[Manual Testing]
    
    subgraph "Example Output"
        F["As a user, I want to...<br/>So that I can..."]
    end
    
    D --> F
    
    style C fill:#FFE5CC
    style E fill:#FFCCCC
```

### v2 EARS Requirements Format

```mermaid
graph LR
    A[User Input] --> B[EARS Processing]
    B --> C[WHEN/THEN Format]
    C --> D[IF/THEN Exceptions]
    D --> E[GIVEN/WHEN/THEN Context]
    E --> F[Direct Test Mapping]
    
    subgraph "Example Output"
        G["WHEN user clicks login<br/>THEN system authenticates<br/>IF credentials invalid<br/>THEN show error"]
    end
    
    E --> G
    
    style B fill:#E5F3FF
    style C fill:#CCE5FF
    style F fill:#E5FFCC
```

## 5. Implementation Execution Comparison

### v1 Manual Implementation

```mermaid
graph TD
    A[tasks.md Generated] --> B[Human Developer]
    B --> C[Manual Coding]
    C --> D[Manual Testing]
    D --> E[Manual Debugging]
    E --> F{Issues Found?}
    F -->|Yes| C
    F -->|No| G[Feature Complete]
    
    style B fill:#FFE5CC
    style C fill:#FFE5CC
    style D fill:#FFE5CC
    style E fill:#FFCCCC
```

### v2 Automated Multi-Task Execution

```mermaid
graph TD
    A[tasks.md Generated] --> B[execute-tasks Command]
    B --> C[Parse Next Task]
    C --> D[Execute Implementation]
    D --> E[Task Tool Validation]
    E --> F{Validation Pass?}
    F -->|No| G[Analyze Feedback]
    G --> H[Self-Correcting Fixes]
    H --> E
    F -->|Yes| I[Mark Task Complete]
    I --> J{More Tasks?}
    J -->|Yes| C
    J -->|No| K[All Tasks Complete]
    K --> L{Final Validation}
    L -->|Pass| M[Feature Complete]
    L -->|Fail| N[Manual Intervention]
    
    style D fill:#E5F3FF
    style E fill:#CCE5FF
    style G fill:#E5FFCC
    style H fill:#E5FFCC
    style M fill:#E5FFCC
```

## 6. Research Integration Flow (v2 Only)

```mermaid
graph TB
    subgraph "Research Integration in v2"
        A[Feature Complexity Analysis] --> B{Research Needed?}
        B -->|Yes| C[WebSearch: Best Practices]
        B -->|No| D[Standard Generation]
        C --> E[WebFetch: Documentation]
        E --> F[Research Findings Analysis]
        F --> G[Integrate with Requirements/Design]
        G --> H[Cite Sources]
        H --> I[Enhanced Document Output]
        D --> I
    end
    
    style C fill:#E5F3FF
    style E fill:#E5F3FF
    style F fill:#CCE5FF
    style G fill:#CCE5FF
    style I fill:#E5FFCC
```

## 7. Quality Assurance Comparison

### v1 Quality Assurance

```mermaid
graph LR
    A[Human Review] --> B[Manual Testing]
    B --> C[Issue Detection]
    C --> D[Manual Fixes]
    D --> E[Re-testing]
    E --> F{Quality OK?}
    F -->|No| C
    F -->|Yes| G[Complete]
    
    style A fill:#FFE5CC
    style B fill:#FFE5CC
    style C fill:#FFCCCC
    style D fill:#FFCCCC
```

### v2 Quality Assurance

```mermaid
graph LR
    A[EARS Validation] --> B[Research Verification]
    B --> C[AI Task Validation]
    C --> D[Self-Correcting Loops]
    D --> E[Quality Metrics]
    E --> F[Comprehensive Testing]
    F --> G{Quality Standards Met?}
    G -->|No| H[Automated Fixes]
    H --> C
    G -->|Yes| I[Complete]
    
    style A fill:#E5F3FF
    style B fill:#E5F3FF
    style C fill:#CCE5FF
    style D fill:#CCE5FF
    style E fill:#E5FFCC
    style I fill:#E5FFCC
```

## 8. Data Flow Architecture

### v1 Data Flow

```mermaid
graph TB
    subgraph "v1 Data Structures"
        A[Project Description] --> B[Basic spec.json]
        B --> C[Simple Requirements]
        C --> D[Basic Design]
        D --> E[Task List]
        E --> F[Manual Implementation]
    end
    
    subgraph "Metadata"
        G[Feature Name]
        H[Timestamps]
        I[Basic Approvals]
    end
    
    B --> G
    B --> H
    B --> I
    
    style B fill:#FFE5CC
    style F fill:#FFCCCC
```

### v2 Data Flow

```mermaid
graph TB
    subgraph "v2 Enhanced Data Structures"
        A[Project Description] --> B[Enhanced spec.json]
        B --> C[EARS Requirements]
        C --> D[Research-Informed Design]
        D --> E[Multi-Task Structure]
        E --> F[Automated Implementation]
    end
    
    subgraph "Rich Metadata"
        G[Codebase Context]
        H[Complexity Assessment]
        I[Research Status]
        J[Progress Metrics]
        K[Quality Scores]
        L[Execution Status]
    end
    
    B --> G
    B --> H
    B --> I
    B --> J
    B --> K
    B --> L
    
    style B fill:#E5F3FF
    style C fill:#E5F3FF
    style D fill:#CCE5FF
    style E fill:#CCE5FF
    style F fill:#E5FFCC
```

## 9. Tool Integration Ecosystem

### v1 Tool Usage

```mermaid
graph TB
    subgraph "v1 Tool Ecosystem"
        A[spec-init] --> B[Basic Tools]
        C[spec-requirements] --> B
        D[spec-design] --> B
        E[spec-tasks] --> B
        F[spec-status] --> B
        G[steering] --> B
        
        B --> H[Bash]
        B --> I[Read/Write]
        B --> J[Edit]
        B --> K[Glob/Grep]
    end
    
    style B fill:#FFE5CC
```

### v2 Tool Usage

```mermaid
graph TB
    subgraph "v2 Enhanced Tool Ecosystem"
        A[Enhanced spec-init] --> B[Core Tools]
        C[EARS spec-requirements] --> B
        D[Research spec-design] --> B
        E[Multi-task spec-tasks] --> B
        F[Enhanced spec-status] --> B
        G[Intelligent steering] --> B
        H[execute-tasks] --> B
        
        B --> I[Bash]
        B --> J[Read/Write/Edit]
        B --> K[Glob/Grep]
        B --> L[WebSearch]
        B --> M[WebFetch]
        B --> N[Task Tool]
        
        L --> O[Research Engine]
        M --> O
        N --> P[AI Validation]
    end
    
    style B fill:#E5F3FF
    style O fill:#CCE5FF
    style P fill:#E5FFCC
```

## 10. Error Handling and Recovery

### v1 Error Handling

```mermaid
graph TD
    A[Error Detected] --> B[Stop Execution]
    B --> C[Display Error Message]
    C --> D[User Manual Intervention]
    D --> E[User Fixes Issue]
    E --> F[Restart Process]
    
    style B fill:#FFCCCC
    style D fill:#FFE5CC
    style E fill:#FFE5CC
```

### v2 Error Handling and Self-Correction

```mermaid
graph TD
    A[Error Detected] --> B[AI Analysis]
    B --> C[Generate Fix Strategy]
    C --> D[Implement Automatic Fix]
    D --> E[Re-validate]
    E --> F{Fix Successful?}
    F -->|Yes| G[Continue Execution]
    F -->|No| H[Retry Count < 3?]
    H -->|Yes| C
    H -->|No| I[Escalate to Human]
    I --> J[Manual Intervention]
    J --> K[Resume Execution]
    
    style B fill:#E5F3FF
    style C fill:#CCE5FF
    style D fill:#CCE5FF
    style G fill:#E5FFCC
    style I fill:#FFE5CC
```

## Summary

These diagrams illustrate the fundamental architectural differences between Claude Code v1 and v2:

- **v1**: Interactive, simple, human-guided workflow
- **v2**: EARS-driven, research-enhanced, AI-automated workflow with validation loops

The evolution represents a shift from manual, interactive development to structured, automated, quality-assured implementation with comprehensive validation and self-correction capabilities.
