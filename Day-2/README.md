# AI Agents Workshop — Day 2: Prompts, Memory & Python for Agents

This repository contains the completed implementation for **Day 2 (Level 1 Fundamentals)** of the AI Agents Workshop. It demonstrates prompt engineering, few-shot classification, structured JSON extraction, manual conversation memory with trimming, and core Python patterns required for building reliable AI agents.

## 📋 Overview

Building on Day 1's single API call, this project transforms a stateless LLM into a rule-following, memory-enabled assistant using the **Sweet Crumbs Home Bakery** case study and extends the architecture to a custom business (**ByteFix Electronics Repair**).

### Core Concepts Covered
* **Message Roles:** `system`, `user`, and `assistant` message structures.
* **4-Part System Prompts:** Structuring prompts with **Role**, **Facts**, **Rules**, and **Format**.
* **Few-Shot Prompting:** Providing worked input/output examples to enforce consistent response shapes.
* **Structured Outputs (JSON):** Extracting fields from natural language and parsing them into Python dictionaries via `json.loads`.
* **Manual Chat Memory & Trimming:** Maintaining a `history` list and slicing recent turns (`MAX_TURNS`) to manage token usage.
* **Agent-Ready Python:** Dictionaries, typed & documented functions (for future tool-calling), `@functools.wraps` decorators, and graceful error handling with `try / except`.

---

## 🛠️ Setup & Prerequisites

1. **Environment:** Google Colab or local Python 3.8+ environment.
2. **Dependencies:** Install the official OpenAI Python SDK (used here with Groq's OpenAI-compatible endpoint):
   ```bash
   pip install openai
