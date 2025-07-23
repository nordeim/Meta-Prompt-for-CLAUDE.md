# Universal CLAUDE.md Generator Prompt

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A powerful, expertly crafted AI prompt designed to automatically generate comprehensive and accurate `CLAUDE.md` guidance files for any codebase.

## Overview

A `CLAUDE.md` file serves as a specialized guide for AI coding assistants (like Anthropic's Claude Code) to quickly understand and effectively work with a specific project's codebase. It typically includes summaries of the project's purpose, architecture, key files, setup commands, integrations, and other essential developer information.

Manually creating a detailed and accurate `CLAUDE.md` file is a time-consuming task that requires a deep understanding of the project. This repository provides a solution: a sophisticated AI prompt that instructs language models to analyze a given codebase and produce a high-quality `CLAUDE.md` file automatically.

## Key Features of Generated CLAUDE.md Files

When used with a capable AI, this prompt aims to generate `CLAUDE.md` files that include:

*   **Project Overview:** A concise summary of the project's purpose, core features, and key technologies.
*   **Quick Start / Setup Commands:** Clear, step-by-step instructions for environment setup and running the application/tests.
*   **Core Architecture & Components:** Explanation of main architectural layers, responsibilities, interactions, and design patterns.
*   **Key Files & Responsibilities:** Identification of critical source files/directories and their primary roles, potentially mentioning key classes/functions.
*   **Specific Integrations:** Details on external services, APIs, or libraries used and how they are integrated.
*   **Hotkeys / In-App Commands:** If applicable, lists special commands available within the application.
*   **Data Storage / Persistence:** Description of how the application handles data persistence.
*   **Environment Configuration:** Lists essential and optional environment variables.
*   **Common Development Tasks:** Outlines procedures for standard modifications (if identifiable).
*   **Testing Information:** Explains how to run tests and the testing framework used (if applicable).
*   **Performance Considerations:** Mentions significant performance notes (if notable).
*   **Clear Formatting:** Well-structured Markdown with headings, lists, tables, and code blocks for readability.

## Usage

1.  **Obtain the Prompt:** Copy the large AI prompt provided in the section below.
2.  **Provide Context to your AI:** Paste the prompt into your conversation with an advanced AI coding assistant (e.g., Claude Sonnet 4, Opus, GPT-4/4o).
3.  **Supply the Codebase:** Provide the AI with the codebase for which you want to generate the `CLAUDE.md`. This could involve:
    *   Uploading relevant files.
    *   Pasting key parts of the codebase.
    *   Providing a detailed description of the project structure and technologies if direct access isn't possible.
4.  **Request Generation:** Ask the AI to generate the `CLAUDE.md` file using the provided prompt and codebase information.

## Example

The prompt is designed to produce output similar to the `CLAUDE.md` examples provided in its context. These examples demonstrate the structure and depth of information the prompt aims to capture.

## The Master Prompt

Below is the comprehensive prompt designed to instruct an AI to generate a `CLAUDE.md` file. Copy everything inside the code block.

```
You are an expert and experienced linguist, particularly in English, and also an expert in science and technology, especially Artificial Intelligence. You excel at communicating complex technical subjects clearly and effectively. You are meticulous, accurate, and thorough in your analysis.

**Your Task:**
Generate a comprehensive `CLAUDE.md` guidance file for the **new project codebase** provided to you. This file should help AI coding assistants (like Claude Code) quickly understand and effectively work with this specific codebase.

**Instructions:**

1.  **Analyze the Provided Codebase:** Carefully examine all files, directories, dependencies (e.g., `requirements.txt`, `pyproject.toml`), configuration files, and documentation within the new project.
2.  **Use Samples as Structure Guides:** Refer to the structure, format, and types of information presented in the two sample `CLAUDE.md` files provided in the knowledge base. Your output should follow a similar *structure* and cover *similar categories* of information, but the *content* must be specific to the new project.
3.  **Generate Content Systematically:** Based on your analysis, extract and synthesize the following information for the `CLAUDE.md` file:
    *   **Project Overview:** A concise summary describing the project's main purpose, core features, and key technologies used.
    *   **Quick Start / Development Setup & Commands:** Clear, step-by-step instructions (using code blocks) for setting up the development environment, installing dependencies (mention tools like pip, Poetry, etc., if relevant), and running the main application or tests.
    *   **Core Architecture / Components:** Explain the main architectural components or layers of the system, their responsibilities, interactions, and any key design patterns implemented (e.g., Repository, Strategy, Agent patterns). Mention if it's async-based.
    *   **Key Files & Responsibilities:** List the most important source files/directories and succinctly describe their primary roles. If relevant and helpful, mention key classes or functions within them (potentially including approximate line numbers like `file.py:line_number`).
    *   **Specific Integrations:** Detail any significant external services, APIs, libraries, or servers the project integrates with (e.g., OpenAI, MCP servers, databases) and how the integration works (configuration, usage points).
    *   **Hotkeys / In-App Commands (if applicable):** List any special commands or keyboard shortcuts available within the application itself for user interaction.
    *   **Data Storage / Persistence:** Describe how the application handles data persistence (e.g., file formats like JSON, database types, storage locations, auto-save mechanisms).
    *   **Environment Configuration:** List the essential and optional environment variables needed for the application to function, including their purpose.
    *   **Common Development Tasks (if identifiable):** Briefly outline standard procedures for common modifications (e.g., adding a new command, theme, or extending functionality).
    *   **Testing (if applicable):** Explain how to run tests, the testing framework used, and any specific testing patterns or practices.
    *   **Performance Considerations (if notable):** Mention any significant performance optimizations or notes (e.g., async operations, data truncation).
4.  **Formatting Requirements:**
    *   Use clear Markdown formatting.
    *   Employ headings and subheadings to organize sections.
    *   Use bullet points for lists of items or steps.
    *   Use tables where appropriate (e.g., for Key Files & Responsibilities).
    *   Enclose all command-line instructions within `bash` code blocks (```bash ... ```).
    *   Use inline code formatting (backticks) for file names, class names, environment variables, and specific technical terms.
5.  **Accuracy & Thoroughness:** Ensure all information extracted from the codebase is accurate and presented comprehensively. Prioritize clarity for an AI assistant needing to understand the code quickly.
6.  **Final Output:** Present your generated `CLAUDE.md` content as a single, well-formatted Markdown document enclosed within ```markdown ... ``` tags.

Please proceed with analyzing the new project codebase and generating the `CLAUDE.md` file according to these instructions.
```

## Contributing

Contributions are welcome! If you have suggestions on how to improve the prompt to generate even better `CLAUDE.md` files, please feel free to open an issue or submit a pull request.

## License

This prompt is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
