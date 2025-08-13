# AI Agent Task Repository Workflow

This diagram illustrates the workflow for using the AI Agent Task Repository Pattern with MCP.

```mermaid
flowchart TD
    A[Human creates new task repository] --> B[Define task specification]
    B --> C{Collaborative workflow?}
    C -->|Yes| D[Stakeholder review & approval]
    C -->|No| E[Version control task definition]
    D --> E[Version control task definition - V1]
    
    E --> F[Optional: Add to organizational task library]
    F --> G[AI Agent receives 'go' instruction]
    G --> H[Agent reads task repository]
    
    H --> I[Agent validates MCP servers]
    I --> J{MCP servers available?}
    J -->|No| K[Request setup assistance]
    J -->|Yes| L[Begin task execution]
    
    K --> J
    L --> M[Agent logs progress in logs/]
    M --> N[Execute task components]
    N --> O{Task complete per success criteria?}
    
    O -->|No| P[Continue execution & logging]
    P --> M
    O -->|Yes| Q[Final validation with human]
    Q --> R{Human satisfied?}
    
    R -->|No| S[Document feedback & iterate]
    S --> P
    R -->|Yes| T[Task completed successfully]
    
    T --> U[Update organizational library with lessons learned]
    
    style A fill:#e1f5fe
    style T fill:#c8e6c9
    style K fill:#ffecb3
    style S fill:#ffecb3
    
    classDef humanAction fill:#e1f5fe,stroke:#01579b,stroke-width:2px
    classDef agentAction fill:#f3e5f5,stroke:#4a148c,stroke-width:2px
    classDef decision fill:#fff3e0,stroke:#e65100,stroke-width:2px
    classDef success fill:#c8e6c9,stroke:#1b5e20,stroke-width:2px
    classDef warning fill:#ffecb3,stroke:#f57f17,stroke-width:2px
    
    class A,D,Q,R,U humanAction
    class G,H,I,L,M,N agentAction
    class C,J,O decision
    class T success
    class K,S warning
```

## Workflow Steps Explained

### 1. Task Definition Phase
- **Human creates repository**: Initialize new task repo from template
- **Define specification**: Populate all template components (outline, details, remote, secrets, MCP, success criteria)
- **Collaborative review**: Optional stakeholder approval process
- **Version control**: Commit V1 of task definition

### 2. Preparation Phase
- **Library integration**: Optionally add to organizational task library
- **Agent instruction**: Simple prompt directing agent to task repository
- **Repository reading**: Agent parses all task components
- **MCP validation**: Verify required MCP servers are available

### 3. Execution Phase
- **Task execution**: Agent works through defined components
- **Progress logging**: Continuous documentation in logs/ directory
- **Iterative progress**: Execute → log → validate → continue cycle

### 4. Validation Phase
- **Success criteria check**: Validate against defined completion criteria
- **Human validation**: Final approval from task owner
- **Feedback integration**: Document lessons learned and improvements

### 5. Knowledge Management
- **Library updates**: Feed learnings back to organizational knowledge base
- **Continuous improvement**: Refine template and processes

## Key Benefits Highlighted

- **Modular approach**: Each step has clear inputs/outputs
- **Version control**: All task definitions are tracked
- **Collaborative support**: Built-in review and approval processes
- **Agent handoff**: Logging enables easy transitions between different LLMs
- **Organizational learning**: Knowledge accumulation and reuse
