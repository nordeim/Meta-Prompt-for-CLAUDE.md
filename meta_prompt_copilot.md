<think>
I need to craft a meta-prompt that, when fed to an AI coding assistant, will produce a `CLAUDE.md` file mirroring the structure and style of the two samples. First, I’ll enumerate the common sections:

- Header with purpose.
- Project Overview (name + one-line summary).
- Quick Start (install, env setup, run).
- Core Architecture: Main Components + Key Design Patterns.
- Development Commands: setup, run, test, workflow.
- Environment Variables.
- Table of Key Files & Responsibilities.
- Integration Details (e.g., MCP, DB).
- Testing patterns.
- File Structure tree.
- Common Development Tasks.
- Performance Notes / Data Storage.
- Hotkeys or CLI commands (if CLI).
  
Then I’ll build a template prompting the AI to discover all this from the codebase. I must instruct it to:

- Scan code paths, identify modules, classes, scripts.
- Detect dependencies & commands.
- Extract environment var names.
- List commands in code (e.g., Click, argparse, npx).
- Summarize design patterns.
- Build file tree automatically.
- Use markdown headings, bullet lists, tables, code fences.
- Leave placeholders or auto-populate with project specifics.

I'll package that into a single master prompt wrapped in a Markdown code block.

</think>

```markdown
You are an AI coding assistant. Your task is to generate a comprehensive `CLAUDE.md` file for a new project codebase, following the structure and style of proven `CLAUDE.md` samples.  

Use these guidelines:

# CLAUDE.md Template

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

- **Name**: {{ProjectName}}  
- **Description**: A concise one-line summary of what this project does.

## Quick Start

```bash
# Install dependencies
{{DependencyInstallCommand}}

# Set up environment
{{EnvSetupCommands}}  # e.g., copy `.env.example` to `.env` and fill in secrets

# Run the application
{{RunCommand}}
```

## Core Architecture

### Main Components

- **{{ComponentName}}** (`{{relative/path/to/file.py}}`): 
  - Brief description of its responsibility.
- **...** Add one item per major module or layer.

### Key Design Patterns

- **{{PatternName}}**: Describe how and where it’s used in the code.
- **...** List all significant patterns (e.g., Repository, Strategy, Observer, Async/Await).

## Development Commands

### Setup

```bash
# Choose one package manager approach
{{PoetryInstallCommands}}
# or
{{PipInstallCommands}}
```

### Running

```bash
# Start the main app
{{MainRunCommand}}

# Alternative invocation
{{AltRunCommand}}
```

## Environment Variables

List all required or optional environment variables (as found in `.env.example` or code):

- `VAR_NAME` – Description and default (if any).
- `...`

## Key Files & Responsibilities

| File Path                     | Purpose                                | Key Classes / Functions         |
|-------------------------------|----------------------------------------|---------------------------------|
| `{{path/to/file.py}}`         | One-line summary                       | `ClassOrFunc1`, `ClassOrFunc2`  |
| `...`                         |                                        |                                 |

## Integrations (if applicable)

- **{{ServiceName}}** integration details:
  - Library/package used.
  - Config files (`{{config.json}}`).
  - How it’s wired in the code.

## Testing

```bash
# Run all tests
{{TestCommand}}

# Run specific tests
{{SelectiveTestCommand}}

# Coverage (if supported)
{{CoverageCommand}}
```

Mention testing tools (pytest, unittest, mocks, async support).

## File Structure

Automatically generate a directory tree of the `src/` (or project root) and key data directories:

```
src/
├── module1.py
├── subpackage/
│   └── module2.py
...
data/
└── ...
```

## Common Development Tasks

Describe how to extend or modify key features:

1. **Adding a new feature**  
   Step-by-step file locations and method hooks.
2. **Extending commands or CLI**  
3. **Updating integrations**  
4. **Running lint/format/type-check**  
   ```bash
   {{LintCommand}}
   {{FormatCommand}}
   {{TypeCheckCommand}}
   ```

## Performance Notes / Data Storage

- Describe any caching, async persistence, auto-save, file formats (JSON, SQLite), and known limits.

---

Follow these rules when filling the template:

- Use GitHub-flavored Markdown.
- Insert a blank line before and after every paragraph or list.
- Use headings (`##`, `###`) to separate logical sections.
- Use bullet lists (`-`) and numbered lists (`1.`) appropriately.
- Use fenced code blocks for commands.
- Create valid Markdown tables for key files or comparison sections.
- Populate every placeholder (`{{…}}`) with project-specific values extracted or inferred from the codebase.
```
