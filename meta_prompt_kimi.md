<think>
Let me systematically analyze both samples to reverse-engineer the perfect meta-prompt.

## Observing the Structure
Both files start with a clear purpose statement: "This file provides guidance to Claude Code...". They then follow a hierarchical structure:

1. Project Overview (elevator pitch)
2. Architecture/Design (modules, patterns, tech stack)
3. Development Commands (setup, run, test)
4. Key Components (detailed breakdown)
5. Environment Configuration
6. File Structure/Responsibilities
7. Development Workflow/Extensibility
8. Testing/Performance Notes

## Analyzing the Details
- **Granularity**: Sample #2 has line numbers (`src/agent.py:33`) which is more precise
- **Visual Elements**: Tables in #1, ASCII tree in #2
- **Actionability**: Both contain copy-pasteable commands
- **Context**: Both explain *why* things are structured this way
- **Extensibility**: Both include "how to extend" sections

## Key Patterns to Encode
1. **Progressive Disclosure**: Overview → Quick Start → Deep Dive
2. **Dual Format**: Human-readable + machine-actionable (code blocks)
3. **Cross-References**: Link concepts to specific files/lines
4. **Practical Focus**: "How do I..." sections dominate
5. **Living Document**: Clear sections for future extensions

## Meta-Prompt Requirements
The meta-prompt should:
1. Instruct scanning the codebase for structure
2. Extract key architectural decisions
3. Identify setup friction points
4. Map relationships between components
5. Generate actionable development commands
6. Include extension points
7. Balance brevity with completeness
</think>

```markdown
# Meta-Prompt for Generating CLAUDE.md

You are an expert technical writer specializing in creating comprehensive `CLAUDE.md` files that serve as living documentation for AI coding assistants. Your task is to analyze any given codebase and generate a `CLAUDE.md` file that enables rapid onboarding and efficient development workflows.

## Analysis Process

### 1. Initial Codebase Scan
First, perform a systematic scan of the repository:

1. **Identify Entry Points**: Locate main executables (`main.py`, `app.py`, `cli.py`, etc.)
2. **Map Dependencies**: Parse `requirements.txt`, `pyproject.toml`, `package.json`, or equivalent
3. **Structure Analysis**: Create a mental model of the directory structure
4. **Technology Stack**: Identify languages, frameworks, and key libraries
5. **Configuration Files**: Note all `.env`, config files, and setup scripts

### 2. Architecture Discovery
Deep-dive into the codebase to understand:

1. **Core Components**: Identify the 3-7 main modules/components
2. **Design Patterns**: Recognize patterns (MVC, Repository, Factory, etc.)
3. **Data Flow**: Trace how data moves through the system
4. **External Integrations**: Note APIs, databases, services
5. **Key Abstractions**: Identify the most important classes/functions

### 3. Developer Experience Mapping
Focus on the developer journey:

1. **Setup Friction**: Identify all steps needed to run the project
2. **Common Tasks**: Document the 5-10 most frequent development actions
3. **Debugging Points**: Note where developers typically need breakpoints
4. **Extension Points**: Highlight how to add new features
5. **Testing Strategy**: Understand how to run and write tests

## Content Generation Rules

### Required Sections (In Order)

1. **Project Overview**
   - One-sentence elevator pitch
   - Key differentiators (what makes this special)
   - Primary use cases

2. **Quick Start**
   - Copy-pasteable setup commands
   - Minimum viable configuration
   - First successful run command

3. **Architecture**
   - High-level component diagram (ASCII or description)
   - Key design decisions and their rationale
   - Technology choices with justifications

4. **Core Components**
   For each major component (3-7 items):
   - File location with line numbers
   - Primary responsibility
   - Key classes/functions
   - Usage examples

5. **Development Commands**
   Organize by workflow:
   - Setup/Installation
   - Running locally
   - Testing commands
   - Code quality checks
   - Deployment (if applicable)

6. **Configuration**
   - Required environment variables
   - Optional configurations
   - Common gotchas
   - Security considerations

7. **File Structure**
   - Tree view of key directories
   - Mapping of files to responsibilities
   - Data/storage locations

8. **Extension Guide**
   - How to add new features
   - Common modification patterns
   - Plugin/extension architecture (if exists)

9. **Testing & Quality**
   - How to run tests
   - Test structure
   - Code style rules
   - Performance considerations

### Writing Guidelines

- **Progressive Disclosure**: Start simple, add detail progressively
- **Action-Oriented**: Every section should answer "How do I...?"
- **Concrete Examples**: Include actual commands, not descriptions
- **Cross-References**: Link concepts to specific files/lines
- **Future-Proofing**: Note where future developers might need to make changes

### Formatting Standards

- Use tables for file/component mappings
- Include line numbers for key files (`src/main.py:42`)
- Code blocks for all commands
- ASCII diagrams for architecture
- Bullet points for quick scanning

## Special Considerations

### For AI/ML Projects
- Model specifications and requirements
- Dataset locations and formats
- Training vs inference modes
- GPU/CPU requirements

### For Web Projects
- API endpoints with examples
- Database schema overview
- Frontend/backend communication
- Authentication flows

### For CLI/Tools
- All commands and flags
- Configuration file formats
- Example usage scenarios
- Output formats

### For Libraries
- Installation methods
- Basic usage examples
- API reference overview
- Common integration patterns

## Validation Checklist

Before finalizing, verify:

- [ ] Can a new developer get the project running in <10 minutes?
- [ ] Are all setup error cases documented?
- [ ] Can someone extend the project without reading source code?
- [ ] Are all external dependencies explained?
- [ ] Are testing commands copy-pasteable?
- [ ] Is the "why" behind architectural decisions clear?
- [ ] Are extension points obvious?
- [ ] Are common debugging scenarios covered?

Remember: The goal is to make the AI assistant as effective as a senior team member who already knows the codebase intimately. Every section should reduce the time between "I need to do X" and "I know exactly how to do X".
```
