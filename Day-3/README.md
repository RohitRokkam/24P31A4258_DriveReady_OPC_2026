# AI Agents Workshop — Day 3: Your First Agent & LangChain

This repository contains the completed implementation for **Day 3 (Level 2: Single Agent, Session 1 of 3)** of the AI Agents Workshop. It transitions the custom business assistant (**ByteFix Electronics Repair**) from raw API calls to **LangChain**, adds automated regression testing (`tests.csv`), and explores agent architecture fundamentals.

## 📋 Overview

Building on Day 2's prompt engineering and manual chat memory, this project introduces **LangChain Expression Language (LCEL)** chains, prompt templates with placeholders, automated evaluation pipelines, and the `create_agent` preview.

### Core Concepts Covered
* **Chatbot vs. Agent:** Moving from text-only responses to goal-driven systems that select and execute tools.
* **The Four Parts of an Agent:** Brain (LLM), Instructions (System Prompt), Tools (Python functions), and Memory (Chat History).
* **The ReAct Agent Loop:** `Think → Act → Observe → Repeat` until a final answer is reached.
* **Three Levels of AI:** Traditional Software (fixed rules), Generative AI (content creation), and Agentic AI (autonomous planning and action).
* **LangChain Foundations:** `ChatGroq`, `ChatPromptTemplate`, `MessagesPlaceholder`, `StrOutputParser`, and piping (`prompt | llm | parser`).
* **Automated Evals (`tests.csv`):** Measuring pass rates across prompt iterations and temperature settings.

---

## 🛠️ Setup & Prerequisites

1. **Environment:** Google Colab or local Python 3.8+ runtime.
2. **Dependencies:** Install LangChain and the Groq integration:
   ```bash
   pip install -q langchain langchain-groq
