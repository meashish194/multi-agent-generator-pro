# multi-agent-generator-pro

<img width="1024" height="683" alt="image" src="https://github.com/user-attachments/assets/41a4210b-0184-435b-bfce-e44ebe0d479b" />

**Multi-Agent-Generator** is a low-code orchestration layer that compiles natural language prompts into optimized multi-agent configurations.

By leveraging **LiteLLM**, it provides a unified interface to deploy agent teams across **100+ Large Language Models (LLMs)**, including providers such as **WatsonX**, **Ollama**, and others.

The framework features an **optional Streamlit-based UI**, enabling rapid experimentation and visualization. It is designed to take users from **concept to a fully functional agentic workforce** with **zero manual coding**, making multi-agent system development fast, flexible, and accessible.

## Features

### Agent Generation

- Generate agent code for multiple frameworks:
  - **CrewAI**: Structured workflows for multi-agent collaboration
  - **CrewAI Flow**: Event-driven workflows with state management
  - **LangGraph**: LangChain’s framework for stateful, multi-actor applications
  - **Agno**: Agno framework for agents team orchestration
  - **ReAct (classic)**: Reasoning + Acting agents using `AgentExecutor`
  - **ReAct (LCEL)**: Future-proof ReAct built with LangChain Expression Language (LCEL)

- **Provider-Agnostic Inference via LiteLLM**:
  - Supports **OpenAI**, **IBM WatsonX**, **Ollama**, **Anthropic**, and more
  - Swap providers with a single CLI flag or environment variable
 
- **Flexible Output:
  - Generate Python code
  - Generate JSON configs
  - Or both combined

 ## Tool Auto-Discovery & Generation (NEW!)
 Create tools for your agents using plain English — no coding required:
 from multi_agent_generator.tools import ToolRegistry, ToolGenerator

# 1. Browse 15+ pre-built tools across 10 categories
registry = ToolRegistry()
web_tools = registry.list_by_category("web_search")
all_tools = registry.list_all()

# 2. Generate custom tools from natural language
generator = ToolGenerator()
tool = generator.generate_from_description("Create a tool that fetches weather data for a city")

# 3. Output the ready-to-use Python code
print(tool.code)
