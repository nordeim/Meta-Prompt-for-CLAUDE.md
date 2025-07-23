# 🧠 CLAUDE.md Prompt Generator

*A master-level prompt to help AI coding assistants deeply understand any codebase.*

---

> Tired of AI assistants asking you what your project does?  
> Wish your coding companion could "read the room" before writing code?  
> Let them *self-orient intelligently* with a single markdown file.

---

## 🧰 What is This?

This repo provides a **meticulously crafted meta-prompt** that enables any advanced AI assistant (Claude, ChatGPT, etc.) to generate a project-specific `CLAUDE.md` file — a self-contained knowledge base for navigating and understanding your codebase.

The `CLAUDE.md` helps AIs:

- Comprehend your architecture
- Identify key files and design patterns
- Understand how to run, test, and extend the code
- Provide relevant, context-aware answers

Whether you’re onboarding new devs or pairing with an AI, this tool accelerates *understanding* before *coding*.

---

## 🚀 Why Use It?

✅ Works with any programming language or framework  
✅ Saves time explaining repo structure  
✅ Elevates the quality of AI-generated code  
✅ Helps standardize documentation across teams  
✅ Zero setup — just copy the prompt and run it in your assistant

---

## 🧠 How It Works

This repository contains a single master prompt written in Markdown. It guides any AI assistant to:

1. Analyze the codebase intelligently
2. Identify and explain core components
3. Extract architecture patterns and dependencies
4. Generate a clean, structured, human-readable `CLAUDE.md`

---

## ✨ Prompt Preview

Here’s a snippet of what the meta-prompt asks the AI to do:

````markdown
You are a highly intelligent AI assistant tasked with generating a `CLAUDE.md` file for this codebase...

Produce a markdown file with these sections:
1. Project Overview
2. Setup & Installation
3. Architecture Overview
4. Key Classes & Methods
5. Environment Variables
...
`````

> 💡 Full prompt: [📄 `claude-prompt.md`](./claude-prompt.md)

---

## 🛠️ How to Use

### 📥 Step 1: Copy the Prompt

Copy the contents of [`claude-prompt.md`](./claude-prompt.md) to your clipboard.

### 💬 Step 2: Paste into Your AI Assistant

Paste into Claude, ChatGPT, or any coding assistant that can analyze codebases.
👉 Prompt the AI like this:

> “You are now going to generate a CLAUDE.md for this codebase. Use the following meta-prompt…”

### 📁 Step 3: Attach Your Codebase

* Upload a ZIP of your repo *or* point the assistant to the code (e.g., via GitHub)
* Let the assistant analyze and generate `CLAUDE.md`

### ✅ Step 4: Review & Commit

* Read the generated CLAUDE.md for accuracy
* Make edits if needed
* Commit it to your repo for future AIs (and humans)

---

## 📌 Sample Output

The AI will produce something like:

```markdown
# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview
AI-powered terminal app using Rich + OpenAI for chat and doc search...

## Main Components
- src/cli.py – TUI interface
- src/agent.py – Pydantic AI integration
...

## Setup
pip install -r requirements.txt
python src/cli.py
...

## Environment Variables
- OPENAI_API_KEY
- MODEL_NAME
...
```

> ✅ It’s everything your AI co-pilot needs — in one place.

---

## 🔍 When Should I Use This?

* When onboarding a new AI coding assistant to your project
* When maintaining large, unfamiliar legacy codebases
* When building dev tooling that interacts with AI
* When improving documentation automation workflows

---

## 🤖 Supported Assistants

* Claude (Anthropic)
* ChatGPT (OpenAI)
* GitHub Copilot Chat (via prompt injection)
* Any capable LLM with code understanding

---

## 🙌 Contributing

Got ideas for improving the prompt?
Want to add prompt variants for specific tech stacks (e.g., Node.js, Rust, monorepos)?

We welcome PRs and issues! Please see [CONTRIBUTING.md](./CONTRIBUTING.md).

---

## 📄 License

MIT License.
Feel free to fork, remix, and enhance.

---

## ❤️ Inspired By

* [Claude Code](https://claude.ai/code)
* [ChatGPT's Code Interpreter](https://chat.openai.com)
* The deep desire for AI assistants who *get it*.
