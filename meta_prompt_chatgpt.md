<think>

Alright, let's carefully unpack this.

### Understanding the Task

The user has given two full examples of `CLAUDE.md` files. These files are designed to **help an AI coding assistant (Claude)** understand a codebase quickly and effectively, facilitating intelligent assistance, refactoring, and navigation. The two samples serve as a template that combines structured metadata, onboarding instructions, component overviews, design patterns, runtime commands, environment config, and testing protocols.

The user now wants a **meta-prompt** — a prompt that could be fed to an AI coding assistant (like Claude or ChatGPT) that, given *any* codebase, would guide the AI to generate a `CLAUDE.md` similar to the samples above.

That meta-prompt must:

1. Reflect the structure and level of detail seen in the two examples.
2. Be **sufficiently general** to work across different projects, but **specific enough** to extract meaningful project-level documentation.
3. Result in a file that makes an AI assistant “feel oriented” in the project space — almost like onboarding a junior developer quickly.

So I need to contemplate what this meta-prompt needs to ask for:

---

### Let's Begin with the *Purpose* of CLAUDE.md

Why does this file exist?

* It orients the AI assistant.
* It lists important files and explains their responsibilities.
* It describes architecture and key abstractions.
* It gives run/test instructions.
* It explains design patterns and architectural decisions.
* It contains useful CLI commands, env vars, storage layouts, and more.

So the meta-prompt needs to encourage generation of all those categories.

---

### Breaking Down the Structure of the Examples

Both samples share common **sections**:

1. **Purpose of the file** — upfront sentence saying "This file provides guidance to Claude..."
2. **Project Overview** — what is this project? what does it do?
3. **Quick Start** / **Setup & Running** — how to get it running
4. **Architecture Overview** — top-level components (files or modules), what they do
5. **Key Design Patterns** — often language-agnostic patterns (e.g., async/await, repository, agent pattern, strategy)
6. **File Descriptions** — what each file does, often with class/method/function details
7. **Environment Variables** — required values from `.env` or OS
8. **Testing Commands** — how to test, how to run individual files
9. **Common Development Tasks** — e.g., how to extend commands, add themes, change config
10. **File Structure** — tree of the repo
11. **Hotkeys/Shortcuts/Commands** (for CLI/TUI projects)
12. **Performance Notes** — e.g., autosaving, async behaviors

---

### Let’s Now Imagine What a Good Meta Prompt Would Look Like

The meta-prompt must *ask* the AI to read and analyze the repo *intelligently*, then output a document **structured like** the samples.

What are the components of the meta-prompt?

* Intent / Purpose — “You are generating a CLAUDE.md...”
* Scope — “Analyze the codebase, its files, and structure...”
* Output style — “Format your result in markdown...”
* Structure guidance — “Follow these sections: \[...]”
* Priorities — “Explain abstractions, roles, commands, key classes, etc.”
* Tone — “Use technical clarity, precise language, and practical organization”

Hmm...

Let me try to write this as a complete prompt that an AI assistant can ingest.

I’ll encapsulate it inside markdown code block for direct usability.

I’ll also echo the level of detail and precision seen in the two examples, ensuring that the prompt elicits comprehensive yet well-organized output.

</think>

\<final\_answer>

````markdown
# CLAUDE.md Generator Meta Prompt

You are a highly intelligent AI assistant tasked with generating a `CLAUDE.md` file for this codebase. This file will help other AI tools (such as Claude Code or ChatGPT) quickly understand the project's purpose, architecture, and operational mechanics.

Please analyze the repository or codebase carefully — review all files, subdirectories, configurations, and test files. Your goal is to produce a comprehensive, technically accurate, and clearly organized markdown document named `CLAUDE.md` that mirrors the structure and intent of professional CLAUDE.md examples.

## Output Format and Guidelines

Produce your result as a valid and well-structured markdown document, following this outline:

---

### 1. Purpose of File
Begin with a single-line statement like:
> This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

---

### 2. Project Overview
- What is this project?
- What does it do?
- What frameworks, platforms, or APIs does it use?
- Mention key technologies or design goals.

---

### 3. Quick Start / Setup
Provide clear setup instructions:
- How to install dependencies (pip/Poetry/npm/etc.)
- How to configure environment variables or `.env` files
- How to run the main entry point (CLI, web, etc.)
- Optional: any common gotchas

Use fenced code blocks for commands.

---

### 4. Core Architecture
Summarize the system’s key components:
- List and describe core files or modules (e.g., `agent.py`, `cli.py`, etc.)
- For each file, mention its role, important classes/functions, and any interactions
- Include design patterns used (e.g., Strategy, Factory, Observer, Async/Await)
- Identify external services/APIs the system depends on

Example format:

```markdown
### Main Components

- **Agent Layer** (`src/agent.py`) - Handles AI logic with OpenAI integration
- **CLI Interface** (`src/cli.py`) - Terminal UI with interactive commands
- **Config System** (`src/config.py`) - Manages environment variables and settings
````

---

### 5. Key Classes & Methods (optional)

For important classes, summarize:

* Class name and file path
* Core methods and their purposes
* Any relevant behavior (e.g., auto-saving, streaming, retry logic)

---

### 6. Environment Variables

List all required env vars and their purpose.
Include defaults if applicable.

```markdown
Required in `.env`:

- `OPENAI_API_KEY` – API key for OpenAI
- `DATABASE_URL` – Connection string for DB
- `MODEL_NAME` – Optional, defaults to gpt-4o
```

---

### 7. Running & Development

Include how to:

* Run the application (main CLI/Web/TUI entry point)
* Run with a different Python path
* Run interactively for debugging
* Common dev commands (linting, formatting, black, flake8, mypy)

---

### 8. Testing

* How to run all tests (pytest, unittest, etc.)
* Running individual test files
* Coverage analysis
* Async test setup if needed
* Mocking strategies if applicable

---

### 9. File Structure

Show an indented tree view of key directories and files.

```markdown
src/
├── agent.py         # AI agent logic
├── cli.py           # Terminal interface
├── config.py        # Env config
└── utils.py         # Shared utilities

tests/
├── test_agent.py
└── test_cli.py
```

---

### 10. Common Development Tasks (Optional but Useful)

Explain how to:

* Add new CLI commands
* Add themes (for TUI)
* Extend functionality or integrate new services
* Modify config or env behaviors
* Update test mocks or fixtures

---

### 11. Data Storage / Persistence

If the app stores data:

* Describe file formats used (e.g., JSON, SQLite, YAML)
* Mention paths and structure
* Explain autosave/backup behaviors
* Note performance considerations

---

### 12. Hotkeys / Slash Commands / UX Features (if interactive)

List interactive commands or keyboard shortcuts.

---

### 13. External Integrations

Describe external APIs, plugins, or servers (e.g., OpenAI, Context7 MCP, Firebase).
Note how they are configured and used.

---

### 14. Performance & Behavior Notes

Mention:

* Async usage
* Caching
* Streaming responses
* Autosave or retry logic
* Known performance bottlenecks

---

## Final Notes

* Keep explanations *precise*, *factual*, and *clear*.
* Write for an audience of *AI assistants* and *human developers* alike.
* Maintain a consistent and professional tone.
* Be exhaustive but not redundant — prioritize clarity and signal over noise.

```
</final_answer>
```
