# AI Agents Workshop — Day 5: Memory & RAG (Complete Single Agent)

This repository contains the completed implementation for **Day 5 (Level 2: Single Agent, Session 3 of 3)** of the AI Agents Workshop. It completes the **ByteFix Electronics Repair** single agent by adding **Retrieval-Augmented Generation (RAG)** over business policies via **ChromaDB** and multi-user conversation memory via **LangGraph's `InMemorySaver`** and `thread_id`.

## 📋 Overview

Building on Day 4's executable `@tool` functions and Google Sheets integration, this project equips the agent to search unstructured company policies on demand and maintain isolated, multi-turn conversations across concurrent customers.

### Core Concepts Covered
* **Three Types of Memory:** Short-term conversation memory (threads), long-term customer memory (cross-session records), and external knowledge (documents/RAG).
* **Thread-Based Checkpointing:** Using `InMemorySaver()` with `config={"configurable": {"thread_id": ...}}` to isolate user histories automatically.
* **Embeddings & Vector Search (`ChromaDB`):** Converting text chunks into semantic vectors and querying nearest neighbors with `.upsert()` and `.query()`.
* **Chunking Strategy:** Splitting knowledge into self-contained, single-topic chunks so retrieval stays focused and token-efficient.
* **RAG Tool Pattern (`Retrieve → Augment → Generate`):** Exposing vector search as a `@tool` (`search_bytefix_faq`) so the agent fetches policies only when needed and escalates unknown queries instead of hallucinating.
* **Single-Agent Sign-Off:** End-to-end regression testing across pricing, scheduling, policy lookup, memory recall, and out-of-scope handling.

---

## 🛠️ Setup & Prerequisites

1. **Environment:** Google Colab (continuing from the Day 4 notebook with `get_repair_cost`, `check_repair_slot`, `log_repair_booking`, and Google Sheets configured).
2. **Dependencies:** Install ChromaDB, LangChain, Groq, and LangGraph:
   ```bash
   pip install -q chromadb langchain langchain-groq langgraph
