# Module 07: Autonomous AI Agents & Tool Calling

> Move beyond static chat completions: Design autonomous AI agents that can reason, plan, use tools, call APIs, and execute complex multi-step tasks.

---

## 📋 Prerequisites
- Module 01 (Python OOP, asynchronous programming basics).
- Module 06 (Generative AI, prompt engineering, structured outputs).

---

## 🧠 Core Concepts

```
┌─────────────────────────────────────────────────────────────┐
│                   Autonomous Agent Loop                      │
│                                                             │
│       ┌──────────┐         ┌───────────┐                    │
│       │ Thought  ├────────►│  Action   │                    │
│       └────▲─────┘         └─────┬─────┘                    │
│            │                     │                          │
│            │                     ▼                          │
│       ┌────┴─────┐         ┌───────────┐                    │
│       │Observation◄────────┤ Tool Call │ (Search, DB, Calc) │
│       └──────────┘         └───────────┘                    │
└─────────────────────────────────────────────────────────────┘
```

1. **Agent Architecture Fundamentals:**
   - The ReAct Pattern (Reasoning + Acting).
   - Planning: Task decomposition, reflection, and self-correction.
   - Memory systems: Short-term (conversation buffer) vs. Long-term (vector memory).
2. **Tool Use & Function Calling:**
   - Providing function schemas (JSON schema) to the model.
   - Parsing structured function arguments and invoking Python execution.
   - Returning tool observations back to the LLM context window.
3. **Agent Frameworks:**
   - LangChain & LangGraph (stateful graph-based multi-actor workflows).
   - LlamaIndex Agents (query engines as tools).
   - Hugging Face `smolagents` (code agents executing sandboxed Python code).
4. **Safety & Guardrails:**
   - Loop limits and termination conditions.
   - Human-in-the-loop validation for sensitive actions (e.g., database writes, payments).

---

## 🗺️ Recommended Sequence

1. Read the foundational paper: *ReAct: Synergizing Reasoning and Acting in Language Models* (Yao et al., 2022).
2. Take the free [Hugging Face AI Agents Course](https://huggingface.co/learn/agents-course).
3. Read the [LangGraph Official Quickstart Guide](https://langchain-ai.github.io/langgraph/).
4. Build an agent equipped with Python REPL and Web Search tools.

---

## 💻 Practical Exercises

### Exercise: Conceptual Tool-Calling Function Schema
```python
import json

# Define a Python function
def calculate_grade_point(marks: list[float]) -> float:
    """Computes the CGPA from a list of numerical marks."""
    return round(sum(marks) / len(marks), 2)

# Tool schema exposed to the LLM
tool_schema = {
    "name": "calculate_grade_point",
    "description": "Computes the CGPA from a list of marks.",
    "parameters": {
        "type": "object",
        "properties": {
            "marks": {
                "type": "array",
                "items": {"type": "number"},
                "description": "List of course marks out of 100"
            }
        },
        "required": ["marks"]
    }
}

print("Tool Schema Ready for Agent Registration:")
print(json.dumps(tool_schema, indent=2))
```

---

## 💡 Project Ideas
- **Automated Research Agent:** An agent that takes a topic, searches ArXiv and Google Scholar, downloads the top 3 PDFs, synthesizes them, and generates an executive summary.
- **GitHub PR Review Agent:** An agent connected to the GitHub API that automatically checks student PRs for PEP 8 compliance and missing docstrings.

---

## 📖 Official Documentation & Resources
- 🎓 [Hugging Face Free AI Agents Course](https://huggingface.co/learn/agents-course)
- 📖 [LangChain Agents Documentation](https://python.langchain.com/docs/concepts/agents/)
- 📖 [LangGraph Documentation](https://langchain-ai.github.io/langgraph/)
