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
3. **Agent Frameworks & Protocols:**
   - **Model Context Protocol (MCP):** The open universal standard connecting AI agents to external databases, tools, APIs, and local development environments.
   - **FastMCP (Prefect):** High-speed, Pythonic framework for rapidly writing and serving MCP tool servers.
   - LangChain & LangGraph (stateful graph-based multi-actor workflows).
   - Hugging Face `smolagents` (code agents executing sandboxed Python code).
4. **Safety & Guardrails:**
   - Loop limits, token cost budgeting, and termination conditions.
   - Token compression & prompt engineering (e.g. Headroom compression).
   - Human-in-the-loop validation for sensitive actions (e.g., database writes, payments).

---

## 🗺️ Recommended Sequence

1. Read the foundational paper: *ReAct: Synergizing Reasoning and Acting in Language Models* (Yao et al., 2022).
2. Take the free [Hugging Face AI Agents Course](https://huggingface.co/learn/agents-course).
3. Read the [LangGraph Official Quickstart Guide](https://langchain-ai.github.io/langgraph/).
4. Build an agent equipped with Python REPL and Web Search tools.

---

## 💻 Practical Exercises

### Exercise 1: Conceptual Tool-Calling Function Schema
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

### Exercise 2: Building an MCP Tool Server with FastMCP
```python
# pip install fastmcp
from fastmcp import FastMCP

# Initialize the MCP Server for AIML Club
mcp = FastMCP("AIML-Club-OCT-Agent-Tools")

@mcp.tool()
def search_campus_schedule(day: str) -> str:
    """Returns the schedule for AI and data science labs on a given day."""
    schedules = {
        "monday": "10:00 AM - Computer Vision Lab (Hall 3)",
        "wednesday": "02:00 PM - Machine Learning Studio (Lab 2)",
        "friday": "04:00 PM - AI Agent & Robotics Club Meeting"
    }
    return schedules.get(day.lower(), "No scheduled labs for this day.")

if __name__ == "__main__":
    # Runs the standard stdio MCP transport
    mcp.run()
```

---

## 💡 Project Ideas
- **Automated Research Agent (AutoResearch):** An autonomous agent inspired by Karpathy's autoresearch that iterates over training configurations and logs experiment metrics automatically.
- **Campus MCP Server:** An MCP server providing tools for querying college library availability, faculty office hours, and past exam questions.
- **GitHub PR Review Agent:** An agent connected to the GitHub API that automatically checks student PRs for PEP 8 compliance and missing docstrings.

---

## 📖 Official Documentation & Resources
- 🌐 [Model Context Protocol (MCP) Official Site](https://modelcontextprotocol.io/)
- 🚀 [FastMCP Documentation (PrefectHQ)](https://github.com/PrefectHQ/fastmcp)
- 🎓 [Hugging Face Free AI Agents Course](https://huggingface.co/learn/agents-course)
- 📖 [LangChain Agents Documentation](https://python.langchain.com/docs/concepts/agents/)
- 📖 [LangGraph Documentation](https://langchain-ai.github.io/langgraph/)
