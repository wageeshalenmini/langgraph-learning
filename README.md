# LangGraph Learning Repository

A structured, hands-on collection of Jupyter notebooks for learning how to build AI agents using [LangGraph](https://github.com/langchain-ai/langgraph) and [LangChain](https://langchain.com/). Each notebook covers a specific agent pattern, progressing from simple conversational bots to full ReAct and RAG-based agents.

---

## Repository Structure

```
├── Agents/
│   ├── ChatBot.ipynb
│   ├── Conditional_Agent.ipynb
│   ├── Hello_World.ipynb
│   ├── Looping.ipynb
│   ├── Memory_Agent.ipynb
│   ├── Multiple_Inputs.ipynb
│   ├── RAG_Agent.ipynb
│   └── ReAct_Agent.ipynb
├── Exercises/
│   ├── Exercise_1.ipynb
│   ├── Exercise_2.ipynb
│   └── Exercise_3.ipynb
├── .gitignore
└── requirements.txt
```

---

## Agent Notebooks

### Hello_World.ipynb
The entry point of the repo. Covers the bare minimum to get a LangGraph graph running — defining a state, adding a single node, and compiling the graph. If you've never used LangGraph before, start here.

### ChatBot.ipynb
Builds a basic conversational chatbot using LangGraph's message state and a single LLM node. Introduces the `add_messages` reducer and how a conversation history accumulates across turns.

### Conditional_Agent.ipynb
Introduces conditional edges — the mechanism that lets a graph choose different next nodes based on the current state. This is the foundation for any non-trivial agent that needs to make decisions about what to do next.

### Looping.ipynb
Demonstrates how to create cycles in a LangGraph graph, allowing agents to repeat steps (e.g. retry a tool call, keep refining output) until a stopping condition is met. Also covers how to prevent infinite loops with counters or guards.

### Memory_Agent.ipynb
Covers how to give an agent persistent memory across conversation turns. Shows the difference between in-context memory (keeping the full message history) and external memory (writing key facts to a separate store and reading them back).

### Multiple_Inputs.ipynb
Demonstrates how to handle state with multiple input fields beyond a single message — defining a richer `State` TypedDict with several keys, and how different nodes read and write to different parts of shared state.

### RAG_Agent.ipynb
Builds a Retrieval-Augmented Generation (RAG) agent that retrieves relevant context from a document store before generating an answer. Introduces the retrieve → generate pattern and how to connect a vector store as a tool inside a LangGraph graph.

### ReAct_Agent.ipynb
Implements the full ReAct (Reason + Act) pattern — the core loop behind most production agents. The agent alternates between reasoning about what to do next and calling tools, looping until it has enough information to produce a final answer. This notebook ties together everything from the earlier notebooks.

---

## Exercises

Practice notebooks that reinforce the concepts covered in the `Agents/` folder. Attempt each one before checking solutions or asking for hints.

| Notebook | Focus Area |
|---|---|
| Exercise_1.ipynb | Basic graph construction and state management |
| Exercise_2.ipynb | Conditional edges and branching logic |
| Exercise_3.ipynb | Tool-calling and the ReAct loop |

---

## Setup

**1. Clone the repository**
```bash
git clone (https://github.com/wageeshalenmini/langgraph-learning)
cd <repo-folder>
```

**2. Install dependencies**
```bash
pip install -r requirements.txt
```

**3. Set your API key**

If you are using a hosted LLM (e.g. Anthropic Claude or OpenAI), set your API key as an environment variable:
```bash
# Anthropic
export ANTHROPIC_API_KEY=your_key_here

# OpenAI
export OPENAI_API_KEY=your_key_here
```

If you are using a local model via [Ollama](https://ollama.com/) (free, no API key needed):
```bash
ollama pull llama3.1
```

**4. Launch Jupyter**
```bash
jupyter notebook
```

---

## Recommended Learning Path

Follow this order to build up concepts progressively:

```
Hello_World → Multiple_Inputs → ChatBot → Conditional_Agent → Looping
    → Memory_Agent → ReAct_Agent → RAG_Agent
```

After each agent notebook, attempt the corresponding exercise before moving on.

---


## About

Built as a personal learning project to get hands-on with LangGraph agent patterns — working through each concept from scratch rather than just reading documentation.

---

## References

- [LangGraph Documentation](https://langchain-ai.github.io/langgraph/)
- [LangChain Documentation](https://docs.langchain.com/)
- [Ollama](https://ollama.com/)
- [arXiv API](https://arxiv.org/help/api/)
- [Tutorial / Video Followed](https://www.youtube.com/watch?v=jGg_1h0qzaM)
