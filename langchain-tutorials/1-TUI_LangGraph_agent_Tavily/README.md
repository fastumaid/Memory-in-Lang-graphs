# #1 Python and Node.js TUIs for a LangGraph agent with a web connection

## 📖 Description 📖

Python and Node.js TUIs for a LangGraph ReAct agent using OpenAI LLM and Tavily tool to get a web connection.

This directory has the following structure:

```
│   README.md
│
├───nodejs
│       node_modules
│       .env
│       .gitignore
│       package-lock.json
|       package.json
│       tui_langgraph_agent_tavily.js
│
└───python
        my-venv
        .env
        .gitignore
        requirements.txt
        tui_langgraph_agent_tavily.py
```

<br>

## 🧠 Learning goals 🧠

- **Building a [LangGraph](https://langchain-ai.github.io/langgraph/) agent:** LangGraph is an extension of LangChain designed to create highly customizable agents. In LangChain `v0.1`, agents were built using `AgentExecutor`. Now, in `v0.2`, it's recommended to use LangGraph instead. Although `AgentExecutor` is still available, it’s moving towards deprecating.
- **Understanding [ReAct](https://arxiv.org/abs/2210.03629) agents:** Our LangGraph agent will be of the ReAct type, which stands for "Reason" and "Act". This means the agent will go through a cycle of thinking and acting. Basically, the agent will decide whether to use tools or not and will keep repeating this _reason-and-act_ process until it finds an answer for the user.
- **Connecting an agent to the web with [Tavily](https://tavily.com/):** Our LangGraph agent will connect to the web using Tavily, a search engine optimized for LLMs and RAGs. This allows the agent to access real-time data beyond what the LLM the agent is using was originally trained on, enabling it to answer questions based on the latest information available.

<br>

## 🚀 Getting started 🚀

Before running [`tui_langgraph_agent_tavily.py`](https://github.com/rokbenko/ai-playground/blob/main/langchain-tutorials/1-TUI_LangGraph_agent_Tavily/python/tui_langgraph_agent_tavily.py) or [`tui_langgraph_agent_tavily.js`](https://github.com/rokbenko/ai-playground/blob/main/langchain-tutorials/1-TUI_LangGraph_agent_Tavily/nodejs/tui_langgraph_agent_tavily.js), follow the instructions below.

> [!NOTE]
> The instructions are specific to Windows. For macOS or Linux, please use the corresponding commands for your operating system.

### Python

1. Clone the repository: `git clone https://github.com/rokbenko/ai-playground.git`
2. Change the directory: `cd ai-playground/langchain-tutorials/1-TUI_LangGraph_agent_Tavily/python`
3. Create a virtual environment named `my-venv`: `python -m venv my-venv`
4. Activate the virtual environment `my-venv`: `my-venv/scripts/activate`
5. Install the dependencies: `python -m pip install -r requirements.txt`
6. Create an `.env` file to set up your environment variables
7. Run the Python script: `python tui_langgraph_agent_tavily.py`

> [!WARNING]
> Deactivate the virtual environment `my-venv` after you're finished by running the following command:
>
> ```
> deactivate
> ```

> [!IMPORTANT]
> Your `.env` file should contain the following environment variables:
>
> ```bash
> OPENAI_API_KEY = "sk-xxxxxxxxxxxxxxxxxxxxxxxxx"
> TAVILY_API_KEY = "tvly-xxxxxxxxxxxxxxxxxxxxxxxxx"
> ```

> [!TIP]
> You can verify that the virtual environment is _created_ successfully if you see a folder named `my-venv` inside the `python` directory.
>
> ```
> │   README.md
> │
> ├───nodejs
> │       node_modules
> │       .env
> │       .gitignore
> │       package-lock.json
> |       package.json
> │       tui_langgraph_agent_tavily.js
> │
> └───python
>         my-venv 👈
>         .env
>         .gitignore
>         requirements.txt
>         tui_langgraph_agent_tavily.py
> ```
>
> You can verify that the virtual environment is _activated_ successfully if you see `(my-venv)` at the beginning of your terminal prompt, like this:
>
> ```
> (my-venv) C:\your\path\to\ai-playground\langchain-tutorials\1-TUI_LangGraph_agent_Tavily\python
> ```
>
> You can verify that the virtual environment is _deactivated_ successfully if you don't see `(my-venv)` anymore at the beginning of your terminal prompt, like this:
>
> ```
> C:\your\path\to\ai-playground\langchain-tutorials\1-TUI_LangGraph_agent_Tavily\python
> ```

> [!NOTE]
> `venv` is a built-in Python module that allows you to create and manage virtual environments. If you have Python `3.3` or higher installed, you can start using `venv` right away.

### Node.js

1. Clone the repository: `git clone https://github.com/rokbenko/ai-playground.git`
2. Change the directory: `cd ai-playground/langchain-tutorials/1-TUI_LangGraph_agent_Tavily/nodejs`
3. Install the dependencies: `npm i`
4. Create an `.env` file to set up your environment variables
5. Run the Node.js script: `node tui_langgraph_agent_tavily.js`

> [!IMPORTANT]
> Your `.env` file should contain the following environment variables:
>
> ```bash
> OPENAI_API_KEY = "sk-xxxxxxxxxxxxxxxxxxxxxxxxx"
> TAVILY_API_KEY = "tvly-xxxxxxxxxxxxxxxxxxxxxxxxx"
> ```

<br>

## 🔥 Working example in Python 🔥

If you run [`tui_langgraph_agent_tavily.py`](https://github.com/rokbenko/ai-playground/blob/main/langchain-tutorials/1-TUI_LangGraph_agent_Tavily/python/tui_langgraph_agent_tavily.py), you should be able to chat with the agent in a terminal:

> User:<br>
> Hi, I'm Bob!
> <br><br>
> Agent:<br>
> Hello Bob! How can I assist you today?
> <br><br>
> User:<br>
> Did Slovenia qualify for the Top 16 countries in Euro 2024 football?
> <br><br>
> The agent is calling the tool 'tavily_search_results_json' with the query 'Slovenia Euro 2024 football Top 16 countries qualification'. Please wait for the agent's answer...
> <br><br>
> Agent:<br>
> Yes, Slovenia qualified for the Top 16 countries in Euro 2024 football as one of the four best third-placed teams along with Netherlands, Georgia, and Slovakia.
> <br><br>
> User:<br>
> Quit
> <br><br>
> Agent:<br>
> Have a nice day! 👋

### ⚒️ Tech stack ⚒️

OS:

- Windows `10`

Dependencies:

- [Python](https://www.python.org/) `3.11.8`
- [Dotenv](https://pypi.org/project/python-dotenv/) `1.0.1`
- [LangChain Python SDK](https://pypi.org/project/langchain/) `0.2.5`
- [LangChain Core Python SDK](https://pypi.org/project/langchain-core/) `0.2.9`
- [LangChain Community Python SDK](https://pypi.org/project/langchain-community/) `0.2.5`
- [LangChain OpenAI Python SDK](https://pypi.org/project/langchain-openai/) `0.1.9`
- [LangGraph Python SDK](https://pypi.org/project/langgraph/) `0.1.1`
- [Rich](https://pypi.org/project/rich/) `13.7.1`

<br>

## 🔥 Working example in Node.js 🔥

If you run [`tui_langgraph_agent_tavily.js`](https://github.com/rokbenko/ai-playground/blob/main/langchain-tutorials/1-TUI_LangGraph_agent_Tavily/nodejs/tui_langgraph_agent_tavily.js), you should be able to chat with the agent in a terminal:

> User:<br>
> Hi, I'm Bob!
> <br><br>
> Agent:<br>
> Hello Bob! How can I assist you today?
> <br><br>
> User:<br>
> Did Slovenia qualify for the Top 16 countries in Euro 2024 football?
> <br><br>
> The agent is calling the tool 'tavily_search_results_json' with the query 'Slovenia Euro 2024 football Top 16 countries qualification'. Please wait for the agent's answer...
> <br><br>
> Agent:<br>
> Yes, Slovenia qualified for the Top 16 countries in Euro 2024 football as one of the four best third-placed teams along with Netherlands, Georgia, and Slovakia.
> <br><br>
> User:<br>
> Quit
> <br><br>
> Agent:<br>
> Have a nice day!

### ⚒️ Tech stack ⚒️

OS:

- Windows `10`

Dependencies:

- [Node.js](https://nodejs.org/en) `21.2.0`
- [LangChain Node.js SDK](https://www.npmjs.com/package/langchain) `0.2.7`
- [LangChain Core Node.js SDK](https://www.npmjs.com/package/@langchain/core) `0.2.10`
- [LangChain Community Node.js SDK](https://www.npmjs.com/package/@langchain/community) `0.2.14`
- [LangChain OpenAI Node.js SDK](https://www.npmjs.com/package/@langchain/openai) `0.2.1`
- [LangGraph Node.js SDK](https://www.npmjs.com/package/@langchain/langgraph) `0.0.25`
- [Terminal Kit](https://www.npmjs.com/package/terminal-kit) `3.1.1`

<br>

## 📽️ Demonstration 📽️

![Demonstration of how to chat in a terminal with the LangGraph ReAct agent with a web connection through Tavily](https://github.com/rokbenko/ai-playground/blob/main/langchain-tutorials/1-TUI_LangGraph_agent_Tavily/demonstration.gif)
