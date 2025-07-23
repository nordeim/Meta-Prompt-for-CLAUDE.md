You are to create a comprehensive `CLAUDE.md` file in markdown format to guide Claude Code (claude.ai/code) when working with the codebase of this project.

Your CLAUDE.md file must serve as a quick reference and deep contextual guide for the AI coding assistant. It should provide a clear project overview, architectural map, actionable setup and development instructions, and pointers to key files, classes, and patterns in the repository.

**Follow this structure and include all relevant sections where applicable:**

---

## 1. Purpose Statement

Begin the file with a brief statement that the document is intended to guide Claude Code (claude.ai/code) when working with this repository.

## 2. Project Overview

Summarize the project's core purpose, main features, goals, and intended users or use cases. Be concise but informative.

## 3. Architecture & Core Components

- List and describe the main architectural layers, modules, or components.
- For each component, include:
    - File location(s) (e.g., `src/agent.py`, with line numbers if possible)
    - Main responsibilities and relevant classes/functions/methods.
    - Brief notes on interactions between components.

## 4. Key Design & Implementation Patterns

- Enumerate the major design patterns, architectural approaches, and unique implementation choices (e.g., async/await, strategy pattern, event-driven, microservices, etc.).
- Note integration points with external services, frameworks, or libraries.

## 5. Development Commands & Workflow

- Provide actionable commands for:
    - Installing dependencies
    - Setting up the environment
    - Running the application
    - Testing
    - Formatting, linting, type-checking, and other development tasks
- Use code blocks for commands.

## 6. Environment Configuration

- List all required and optional environment variables, configuration files, and their purpose.
- Specify defaults or expected formats where applicable.

## 7. File Structure & Key Files

- Diagram or bullet the main directory and file structure.
- For each key file, describe its purpose, main classes/functions, and how it fits into the overall system.
- Use tables if helpful.

## 8. Special Integrations & Features

- Explain any important integrations (e.g., cloud services, databases, messaging systems).
- Describe user interface features, hotkeys, commands, or interaction patterns, if relevant.

## 9. Common Development & Extension Tasks

- Provide step-by-step guides for common tasks (e.g., adding a new feature, extending commands, modifying integrations).
- Reference specific files, classes, or methods.

## 10. Testing & Validation

- Detail how to run tests, what frameworks are used, and any relevant testing patterns.
- Note how to mock external dependencies or validate core logic.

## 11. Performance & Data Storage Notes

- Summarize any important performance considerations, data persistence mechanisms, formats, and locations.

---

**Formatting Guidelines:**

- Use markdown headings, bullet points, code blocks, tables, and diagrams as appropriate for clarity.
- Reference file paths and line numbers for key classes/methods if possible.
- Ensure the file is comprehensive but concise, enabling the AI assistant to quickly orient and work effectively with the codebase.

---

**Example Structure:**

See the provided sample CLAUDE.md files for inspiration. Match their clarity, depth, and actionable detail.

---

**Your output must be a markdown file named `CLAUDE.md`.**
