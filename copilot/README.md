# 📄 CLAUDE.md Generator

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)  
[![Python](https://img.shields.io/badge/Python-3.8%2B-green.svg)]()  
[![AI-Powered](https://img.shields.io/badge/AI-Powered-Yes-orange.svg)]()

Turn any codebase into a clean, consistent `CLAUDE.md` guide in seconds.

---

## 🎯 The Problem

Onboarding a new repository often means digging through folders, hunting for scripts, env vars, and key classes.  
Writing a structured guide for an AI assistant is tedious and error-prone.

---

## 🚀 Our Solution

Use a single **[master prompt](https://raw.githubusercontent.com/nordeim/claude-md-generator/refs/heads/main/copilot/meta_prompt.md)** to automatically generate a `CLAUDE.md` file tailored to your project.  
This meta-prompt:

- Scans modules, scripts, and config files  
- Extracts commands, patterns, and dependencies  
- Synthesizes a polished Markdown document  
- Follows proven conventions for fast AI assistance  

---

## ⚡ Quick Start

1️⃣ Clone your repo  
```bash
git clone https://github.com/nordeim/claude-md-generator.git
cd claude-md-generator
```

2️⃣ Install dependencies  
```bash
pip install claude-md-gen
```

3️⃣ Run the generator  
```bash
claude-md-gen --path . --output CLAUDE.md
```

---

## 🎬 Usage Example

```bash
# Generate a CLAUDE.md for the current codebase
claude-md-gen --path . --output CLAUDE.md

# Preview the first 20 lines
head -n 20 CLAUDE.md
```

_Result snippet:_  
```markdown
# sample CLAUDE.md

This file provides guidance to Claude Code when working with code in this repository.

## Project Overview
Context7 Agent is an AI-powered terminal chat application...
```

---

## 🛠 Full Master Prompt

<details>
<summary>Click to expand the complete meta-prompt</summary>

```markdown
You are an AI coding assistant. Your task is to generate a comprehensive `CLAUDE.md` file for a new project codebase, following the structure and style of proven `CLAUDE.md` samples.

Use these guidelines:

# CLAUDE.md Template

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

- **Name**: {{ProjectName}}  
- **Description**: A concise one-line summary of what this project does.

## Quick Start

\`\`\`bash
# Install dependencies
{{DependencyInstallCommand}}

# Set up environment
{{EnvSetupCommands}}  # e.g., copy `.env.example` to `.env` and fill in secrets

# Run the application
{{RunCommand}}
\`\`\`

## Core Architecture

### Main Components

- **{{ComponentName}}** (`{{relative/path/to/file.py}}`): 
  - Brief description of its responsibility.
- **...**

### Key Design Patterns

- **{{PatternName}}**: Describe how and where it’s used.
- **...**

## Development Commands

### Setup

\`\`\`bash
# with Poetry
{{PoetryInstallCommands}}
# or pip
{{PipInstallCommands}}
\`\`\`

### Running

\`\`\`bash
{{MainRunCommand}}
{{AltRunCommand}}
\`\`\`

## Environment Variables

- `VAR_NAME` – Description and default.
- `...`

## Key Files & Responsibilities

| File Path                     | Purpose                                | Key Classes / Functions         |
|-------------------------------|----------------------------------------|---------------------------------|
| `{{path/to/file.py}}`         | One-line summary                       | `ClassOrFunc1`, `ClassOrFunc2`  |
| `...`                         |                                        |                                 |

## Integrations (if applicable)

- **{{ServiceName}}** integration:
  - Library/package used.
  - Config file: `{{config.json}}`.
  - Wiring in code.

## Testing

\`\`\`bash
# Run all tests
{{TestCommand}}

# Specific tests
{{SelectiveTestCommand}}

# Coverage
{{CoverageCommand}}
\`\`\`

## File Structure

\`\`\`
src/
├── module1.py
├── subpkg/
│   └── module2.py
...
data/
└── ...
\`\`\`

## Common Development Tasks

1. **Adding a feature**  
2. **Extending commands**  
3. **Updating integrations**  
4. Lint / Format / Type-check  
\`\`\`bash
{{LintCommand}}
{{FormatCommand}}
{{TypeCheckCommand}}
\`\`\`

## Performance Notes / Data Storage

- Caching, async persistence, file formats.
- Known limits.
```

</details>

---

## ❓ FAQ & Troubleshooting

- **Q**: It didn’t detect my CLI commands.  
  **A**: Ensure your commands use Click, argparse, or a `main()` entry point.

- **Q**: Custom directories aren’t scanned.  
  **A**: Pass `--path path/to/src` to include nonstandard layouts.

---

## 🤝 Contributing

1. Fork & clone  
2. Create a feature branch  
3. Submit a pull request  

Please follow our [Code of Conduct](CODE_OF_CONDUCT.md).

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).
