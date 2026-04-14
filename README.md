# Multi-Agent-System-With-LangGraph
This project implements an autonomous Multi-Agent System (MAS) designed to bridge the gap between real-time web data and structured content generation. Built using LangGraph and Google Gemini 2.5 Flash, the system orchestrates a collaborative workflow between specialized AI agents.

## The Architecture
The system is designed as a Stateful Directed Acyclic Graph (DAG) where data (the "State") is passed between nodes like a relay race.

## The Agent Team
**The Researcher (Search Node):** Utilizes DuckDuckGoSearchRun to perform real-time internet queries. It bypasses the "knowledge cutoff" of static LLMs by gathering live 2026 data.

**The Writer (Synthesis Node):** Consumes the "State" updated by the Researcher. Using Gemini 2.5 Flash, it synthesizes raw search results into a polished, Markdown-formatted blog post.

##Key Features
**Agentic Orchestration:** Uses LangGraph to manage complex state transitions and "hand-offs" between agents.

**Real-Time Grounding:** Eliminates hallucinations by grounding all generated content in live web search data.

**Stateful Design:** Implements a TypedDict shared memory, allowing agents to read and write to a common clipboard.

**Cloud-Native & Efficient:** Optimized for Google Colab environment using google.colab.userdata for secure secret management.

## Tech Stack
Orchestration: LangGraph

LLM: Google Gemini 2.5 Flash

Framework: LangChain

Search Engine: DuckDuckGo API

Environment: Google Colab

## How It Works
Initialization: User provides a topic.

**Step 1 (Research):** The Researcher agent identifies key facts and latest news from the web.

**Step 2 (Writing):** The Writer agent receives the research data and drafts an engaging post.

**Completion:** The system returns a finalized Markdown document.
