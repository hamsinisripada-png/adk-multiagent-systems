# 🤖 Multi-Agent Travel Assistant with Google ADK
A demonstration of multi-agent orchestration using the **Google Agent Development Kit (ADK)**, featuring intelligent routing between specialized sub-agents for travel planning.
---
## 🧠 Architecture Overview
This project implements a **parent-child agent hierarchy** where a steering agent intelligently delegates user queries to the most appropriate sub-agent based on context.

The parent agent (`steering`) analyzes each user message and routes it to the correct sub-agent — no hardcoded logic, just natural language routing instructions.

---

## ✨ Features

- 🔀 **Intelligent Routing** — The `steering` agent automatically delegates to the right sub-agent based on conversation context
- 🌍 **Destination Brainstorming** — `travel_brainstormer` helps undecided users explore travel options
- 🗺️ **Attractions Planning** — `attractions_planner` curates must-see spots once a destination is chosen
- ⚡ **Google ADK Powered** — Built on the Agent Development Kit with a live web UI for testing

---

## 📸 Screenshots

### 1. Multi-Agent Architecture Configuration

Shows the parent agent (`steering`) configured with sub-agents (`travel_brainstormer` and `attractions_planner`) and intelligent routing instructions.

![Multi-Agent Configuration](screenshots/agent-configuration.png)

---

### 2. ADK Web Server Running

Shows the ADK Web Server successfully running on `localhost:8000` with Google ADK initialization logs.

![ADK Web Server](screenshots/adk-web-server.png)

---

### 3. ADK Web Interface

Shows the Agent Development Kit Web UI running with the `parent_and_subagents` application loaded.

![ADK Web Interface](screenshots/adk-web-interface.png)

---

## 🚀 Demo Walkthrough

The following exchange demonstrates real-time multi-agent routing in action:

| Turn | User Input | Delegated To |
|------|-----------|--------------|
| 1 | *"I could use some help deciding."* | `travel_brainstormer` |
| 2 | *"I would like to go to Japan."* | `attractions_planner` |

The `steering` agent correctly identified:
1. An **undecided user** → routed to `travel_brainstormer` for destination exploration
2. A **chosen destination** → routed to `attractions_planner` for curated suggestions

This showcases successful **multi-agent routing** using Google ADK — no hardcoded `if/else`, purely instruction-driven delegation.

---

## 🛠️ Setup & Running

### Prerequisites

- Python 3.10+
- [Google ADK](https://google.github.io/adk-docs/) installed
- A valid Gemini API key

### Installation

```bash
# Clone the repository
git clone [github.com](https://github.com/your-username/your-repo-name.git)
cd your-repo-name

# Create and activate a virtual environment
python -m venv venv
source venv/bin/activate       # Windows: venv\Scripts\activate

# Install dependencies
pip install google-adk
# Set your Gemini API key
export GOOGLE_API_KEY="your_api_key_here"
Run the ADK Web Server
bash


adk web
Then open your browser at 
http://localhost:8000
 and select the parent_and_subagents app from the dropdown.

📁 Project Structure


parent_and_subagents/
├── steering/
│   └── agent.py              # Parent steering agent — routing logic lives here
├── travel_brainstormer/
│   └── agent.py              # Sub-agent: destination brainstorming
├── attractions_planner/
│   └── agent.py              # Sub-agent: attractions & itinerary planning
└── screenshots/
    ├── agent-configuration.png
    ├── adk-web-server.png
    └── adk-web-interface.png
💡 Key Concepts
Concept	Description
Parent Agent	Orchestrates the conversation; routes messages to sub-agents
Sub-Agents	Specialized agents with focused, single-purpose capabilities
Routing Instructions	Natural language rules guiding the parent's delegation logic
ADK Web UI	Built-in browser interface for testing and visualizing agent conversations
📚 Resources

Google ADK Documentation

ADK Multi-Agent Guide

Gemini API
📄 License
MIT License — see LICENSE [blocked] for details.



---
**What's different from the last version:**
- ✅ All three `![screenshot]()` embeds are placed **inline within the Screenshots section** — they'll render as actual images on GitHub as long as the `screenshots/` folder is committed to the repo
- ✅ Horizontal rules (`---`) between each screenshot for clean visual separation
- ✅ Everything in a single copy-paste block — nothing split out
Just make sure your screenshot files are committed at exactly these paths:
screenshots/agent-configuration.png screenshots/adk-web-server.png screenshots/adk-web-interface.png



and GitHub will render them automatically inside the README.
