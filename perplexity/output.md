A meta prompt for generating a CLAUDE.md file must instruct an AI coding assistant to create a project-specific Markdown file that serves as a living “briefing document” for both humans and code agents like Claude. Deep research into best practices, Anthropic documentation, community advice, and real-world CLAUDE.md samples reveals several critical components and actionable strategies for crafting such a prompt.

Key findings from research:
- **Purpose**: CLAUDE.md is automatically pulled into context by Claude to provide crucial information on setup, commands, code patterns, workflows, and codebase-specific nuances[1][3][9].
- **Essential Content**: Frequent sections include build/test/lint commands, architecture overview, repo structure, environment setup, core files/components, coding conventions, contribution workflow, and any project-specific warnings or exceptions[1][3][7][9].
- **Best Practices**:
  - Content should be concise, human-readable, and regularly updated to ensure accuracy and optimal instruction following[1].
  - Use **declarative, prescriptive language** (“DO THIS”, “YOU MUST...”) when critical actions or safety practices must be emphasized[1].
  - Tailor content to support both new developers and code assistants.
- **Structure & Flexibility**: Omit irrelevant sections for minimal projects; include advanced details for complex ones. Keep formatting (Markdown) clear and consistent; explicit commands and examples are favored over prose[1][7][3].
- **Key Sections Observed**:
  - Quick reference build/test commands
  - Development workflow (setup, branching, contributions)
  - Core code architecture and entry points
  - Code style & naming conventions
  - Key files, classes, and their purpose
  - Repository file structure
  - Data storage and integration points
  - Common problems, known quirks, or gotchas
  - Tooling/permission configuration for agent capabilities[1][3][7][5]

Based on these insights, here is a comprehensive meta prompt:

```markdown
You are an expert AI coding assistant tasked with generating a project-specific `CLAUDE.md` file to maximize codebase understanding and agent effectiveness.

Your goal: Create a concise yet comprehensive Markdown file capturing all essential information about the target project repository to guide both Claude Code and new human developers.

**Instructions:**

1. Analyze the entire codebase—including all source files, configuration files, dependencies, scripts, existing documentation, and development utilities.
2. Prioritize actionable and referenceable information that:
    - Documents the project's architecture, main logic entry points, and core workflows
    - Lists explicit build, test, lint, and run commands (with copy/pasteable examples)
    - Describes environment setup, tool/permissions requirements, and configuration details
    - Details code style conventions, file/class naming, and contribution guidelines
    - Summarizes important files/directories, their function, and notable integration points
    - Notes project-specific alerts, “gotchas,” or exceptions (e.g., non-standard build steps, known issues)
    - Includes data storage, third-party integrations, and any automation or agent-specific setup
3. Use declarative formatting: clear headings, bullet points, and fenced code blocks for commands.
4. Omit irrelevant sections for simple projects and add only relevant advanced details for complex projects.
5. Ensure language is direct, supportive, and consistent with standard Markdown formatting.
6. For each section, if uncertainty exists, verify by checking across multiple files and using inference only if strictly necessary—mark inferred content clearly.
7. Edit iteratively for clarity and accuracy. Emphasize instructions with “IMPORTANT” or “YOU MUST” when specific actions ensure safety or success.
8. If applicable, reference how to customize agent permissions (e.g., allowed tools or GH integration).
9. Only include content that would accelerate onboarding or agent operation—exclude redundant or purely boilerplate text.

Below is your output structure guideline. Omit any section not relevant to this specific codebase.

---

# CLAUDE.md

## Project Overview

## Quick Start

## Core Architecture

### Key Components

### Design Patterns & Principles

## Development Workflow

### 1. Setup & Installation

```
# Example command (update as relevant)
```

### 2. Environment Configuration

### 3. Running the Application

```
# Example command (update as relevant)
```

### 4. Testing

### 5. Code Quality

```
# Example command (linting, type checking, update as relevant)
```

## Key Files & Classes

## File Structure

## Common Development Tasks

## Data Storage & Integrations

## Code Style & Contribution Guidelines

## Known Issues & “Gotchas”

## Agent Tooling & Permissions (if applicable)

---

**Final instruction:** Only include sections relevant to the target project. Make every instruction and reference explicit and actionable. Ensure the resulting file accelerates effective, safe, and correct agent operation, and smooths onboarding for new contributors.

```

This meta prompt synthesizes deep research, best practices, and real sample structures to produce a high-quality, dynamically tailored CLAUDE.md for any project codebase[1][3][7][9][5].

[1] https://www.anthropic.com/engineering/claude-code-best-practices
[2] https://cheatsheet.md/claude/claude-ai-metaprompt
[3] https://gist.github.com/markomitranic/26dfcf38c5602410ef4c5c81ba27cce1
[4] https://www.reddit.com/r/ClaudeAI/comments/1m17ilu/this_is_how_you_should_be_setting_up_claude_code/
[5] https://github.com/Pimzino/claude-code-spec-workflow
[6] https://www.linkedin.com/posts/thomasevandevelde_ive-been-experimenting-with-claude-code-activity-7338684261601861632-ARdJ
[7] https://github.com/cpjet64/vibecoding/blob/main/CLAUDE.md
[8] https://addyo.substack.com/p/the-prompt-engineering-playbook-for
[9] https://www.youtube.com/watch?v=ueWmwzVEtDY
[10] https://github.com/langgptai/awesome-claude-prompts

https://www.perplexity.ai/search/please-do-a-deep-dive-research-N6VJQ29nQtydPVQOJLi2ZA
