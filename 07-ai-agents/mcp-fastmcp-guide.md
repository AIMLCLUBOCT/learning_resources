# 🤖 Hands-on Guide: Building Custom Model Context Protocol (MCP) Servers with FastMCP

> Learn how to build and expose custom tools to Claude, Antigravity IDE, Cursor, and autonomous AI agents using the official Python Model Context Protocol (MCP) SDK and FastMCP.

---

## 📌 What is the Model Context Protocol (MCP)?

The **Model Context Protocol (MCP)** is an open industry standard that enables Large Language Models (LLMs) and agentic coding environments to securely discover and call external tools, execute code, access databases, and read local files.

Rather than hard-coding one-off API integrations, MCP provides a unified client-server architecture:
- **MCP Host / Client:** The agent or IDE (e.g. Claude Desktop, Antigravity IDE, Cursor).
- **MCP Server:** A lightweight microservice that defines tools, resources, and prompts.

---

## 🚀 1. Installation & Environment Setup

FastMCP is the high-level, decorator-driven interface included in the official Python MCP SDK (`mcp>=1.2.0`).

```bash
# Create and activate a clean virtual environment
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate

# Install the official MCP SDK with FastMCP support
pip install "mcp[cli]>=1.2.0" pydantic
```

---

## 🛠️ 2. Creating Your First Tool Server (`server.py`)

Here is a complete, production-ready FastMCP server providing mathematical analysis, string hashing, and system inspection tools:

```python
"""
AIML Club OCT — FastMCP Reference Server
Exposes mathematical utilities and string hashing tools to AI agents.
"""

from mcp.server.fastmcp import FastMCP
from pydantic import BaseModel, Field
import hashlib
import math
import sys

# Initialize the FastMCP server instance
mcp = FastMCP("aiml-club-toolkit")


class StatisticalInput(BaseModel):
    numbers: list[float] = Field(
        ..., 
        description="List of numeric values to analyze.",
        min_length=1
    )


@mcp.tool()
def compute_statistics(payload: StatisticalInput) -> dict:
    """Compute mean, sample variance, standard deviation, and median for a list of numbers."""
    nums = sorted(payload.numbers)
    n = len(nums)
    mean = sum(nums) / n
    variance = sum((x - mean) ** 2 for x in nums) / (n - 1) if n > 1 else 0.0
    std_dev = math.sqrt(variance)
    median = (nums[n // 2] if n % 2 != 0 else (nums[n // 2 - 1] + nums[n // 2]) / 2)

    return {
        "count": n,
        "mean": round(mean, 4),
        "variance": round(variance, 4),
        "std_dev": round(std_dev, 4),
        "median": round(median, 4),
        "min": nums[0],
        "max": nums[-1],
    }


@mcp.tool()
def hash_text(text: str, algorithm: str = "sha256") -> str:
    """Hash a string using sha256, sha512, or md5."""
    algo = algorithm.lower()
    if algo not in {"sha256", "sha512", "md5"}:
        raise ValueError("Supported algorithms: sha256, sha512, md5")
    
    h = getattr(hashlib, algo)()
    h.update(text.encode("utf-8"))
    return h.hexdigest()


if __name__ == "__main__":
    # Start the standard stdio server loop
    mcp.run()
```

---

## 🔌 3. Connecting to Claude Desktop or Antigravity IDE

To connect your custom MCP server to **Claude Desktop**, edit `claude_desktop_config.json`:

- **Windows:** `%APPDATA%\Claude\claude_desktop_config.json`
- **macOS:** `~/Library/Application Support/Claude/claude_desktop_config.json`

Add the server configuration:

```json
{
  "mcpServers": {
    "aiml-toolkit": {
      "command": "python",
      "args": ["C:/absolute/path/to/server.py"]
    }
  }
}
```

Restart Claude Desktop, and the hammer icon 🔨 will appear with your `compute_statistics` and `hash_text` tools ready to run!

---

## 💡 Student Exercises
1. Add an `@mcp.tool()` that queries a SQLite database and returns the top 5 records.
2. Build an `@mcp.tool()` that takes a URL and extracts clean markdown using `readability` or `trafilatura`.
3. Open a PR in [`AIMLCLUBOCT/Projects`](https://github.com/AIMLCLUBOCT/Projects) to showcase your tool server!
