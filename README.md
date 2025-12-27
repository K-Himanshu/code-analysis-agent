# Code Analysis Agent (Agentic AI)

This project demonstrates a **simple, framework-free agentic AI system**
built using plain Python and an LLM as a reasoning engine.

The agent analyzes a real codebase and produces:
- a concise summary
- key design notes
- potential risks and improvement areas

## Why this project

Most “AI agents” hide logic inside frameworks.
This project shows **how agentic behavior emerges from control flow**, not tools.

## Agent Architecture

The agent follows this loop:

1. **Goal**
   - Analyze a codebase
2. **Context Collection**
   - Clone a public repository
   - Read source files
3. **Context Reduction**
   - Trim files to fit token limits
4. **Reasoning Step**
   - Call an LLM with structured instructions
5. **Action**
   - Save structured analysis output
6. **Guardrails**
   - Throttling
   - Error handling

## How to run (Google Colab)

1. Open `notebooks/demo.ipynb`
2. Add your Gemini API key to Colab Secrets:
   - Name: `API_KEY`
3. Run all cells

## How to run locally

```bash
git clone https://github.com/<your-username>/code-analysis-agent.git
cd code-analysis-agent
pip install -r requirements.txt
export GEMINI_API_KEY=your_key_here
python agent.py
