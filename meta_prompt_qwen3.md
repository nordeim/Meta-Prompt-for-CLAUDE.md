<think>
Okay, I've received the instruction and the two sample `CLAUDE.md` files. My task is to analyze these samples and create a master/meta prompt that guides an AI assistant in generating a similar `CLAUDE.md` file for any new project codebase.

First, let's break down what a `CLAUDE.md` file is supposed to do based on the samples:
1.  **Provide Guidance:** It's specifically meant to guide Claude Code (or similar AI coding assistants) when working with the repository's code.
2.  **Project Overview:** Offers a concise summary of the project's purpose, key features, and main technologies used.
3.  **Quick Start / Development Commands:** Gives clear, copy-pasteable instructions for setting up the development environment, installing dependencies, and running the application or tests.
4.  **Core Architecture / Structure:** Explains the main components/modules of the system, their responsibilities, key design patterns used, and how they interact.
5.  **Key Files & Responsibilities:** Lists important files and their primary roles, sometimes including key classes or line numbers.
6.  **Specific Integrations:** Details important external integrations (like MCP in the samples) and how they are configured/used.
7.  **Hotkeys / Commands:** If applicable, lists interactive commands or hotkeys available within the application.
8.  **Data Storage:** Describes how data is persisted (e.g., file formats, locations).
9.  **Common Development Tasks:** Provides guidance on typical modifications like adding themes, extending commands, etc.
10. **Testing:** Information on how to run tests and testing patterns used.
11. **Environment Configuration:** Lists required and optional environment variables.
12. **Performance Notes:** Highlights any relevant performance considerations or optimizations.

Now, let's think about how to structure a meta-prompt to elicit this information from an AI assistant analyzing a new codebase:

1.  **Role Definition:** Clearly state the role of the AI (expert linguist, AI expert, great lecturer, meticulous analyst).
2.  **Objective:** Define the clear goal: Generate a `CLAUDE.md` file for the *new* project provided.
3.  **Reference Material:** Instruct the AI to use the provided sample `CLAUDE.md` files as templates for *structure* and *content type*, not content itself.
4.  **Analysis Steps:** Provide a systematic approach:
    *   Analyze the provided codebase files.
    *   Identify the project's purpose, main components, architecture, key classes/functions, dependencies, setup/run commands, integrations, data handling, etc.
5.  **Content Requirements:** List the specific sections that should typically be included, mirroring the elements found in the samples (Overview, Quick Start, Architecture, Key Files, etc.).
6.  **Formatting Guidelines:** Specify the use of Markdown, clear headings, bullet points, tables, code blocks for commands, and potentially line numbers for key classes/functions.
7.  **Accuracy & Thoroughness:** Emphasize the need for meticulous analysis and accurate representation of the codebase.
8.  **Final Output:** Request the final output to be the generated `CLAUDE.md` content enclosed in Markdown code block tags.

Let's draft this meta-prompt.
</think>

```markdown
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
