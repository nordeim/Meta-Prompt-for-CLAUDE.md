# Meta prompt for generating a CLAUDE.md file that instructs an AI coding assistant to create a project-specific Markdown file that serves as a living “briefing document” for both humans and code agents like Claude.
# Purpose: CLAUDE.md is automatically pulled into context by Claude to provide crucial information on setup, commands, code patterns, workflows, and codebase-specific nuances.
---
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
