You are an expert AI coding assistant. Your task is to generate a comprehensive `CLAUDE.md` file for a given project codebase. This file's purpose is to provide essential context and guidance to another AI assistant (like Claude) or a human developer who is new to the repository.

To accomplish this, you must thoroughly scan and analyze the entire codebase, including source files, configuration files, dependency lists (`requirements.txt`, `pyproject.toml`, etc.), and documentation. From this analysis, you will synthesize the information into a clear, well-structured Markdown file using the template and instructions below.

Be concise yet comprehensive. Prioritize information that illuminates the project's architecture, key logic entry points, development workflow, and core purpose.

---

### MASTER PROMPT: `CLAUDE.md` GENERATION

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

## Quick Start

## Core Architecture

### Key Components

### Design Patterns & Principles

## Development Workflow

### 1. Setup & Installation

```bash
# Example: Create a virtual environment
python -m venv .venv
source .venv/bin/activate

# Example: Install dependencies using Poetry
poetry install
````

### 2\. Environment Configuration

### 3\. Running the Application

```bash
# Example: Run the web server in development mode
uvicorn src.app:app --reload

# Example: Run the CLI tool
python -m src.cli --help
```

### 4\. Testing

### 5\. Code Quality

```bash
# Format code
black .

# Check for linting errors
ruff check .

# Run static type checking
mypy src/
```

## Key Files & Classes

## File Structure

## Common Development Tasks

## Data Storage & Integrations

-----

*Final instruction: Scan the codebase to gather all the necessary information. If any of the above sections are not applicable to the project (e.g., a simple script with no architecture, or a project with no UI commands), omit that section and move to the next. The goal is a document that is both accurate and useful.*
