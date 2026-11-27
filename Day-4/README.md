# AI Agents Workshop — Day 4: Tools, Structured Output & Google Sheets

This repository contains the completed implementation for **Day 4 (Level 2: Single Agent, Session 2 of 3)** of the AI Agents Workshop. It equips the custom business assistant (**ByteFix Electronics Repair**) with executable Python `@tool` functions, **Pydantic** structured data validation, and live persistence to **Google Sheets** via `gspread`.

## 📋 Overview

Building on Day 3's LangChain foundations, this project transforms a conversational chain into an action-taking agent capable of looking up live service rates, checking technician availability, validating customer records, and writing confirmed bookings directly into a Google Sheet.

### Core Concepts Covered
* **Function Calling / Tool Use:** How the model requests tool calls with arguments while Python executes the code and returns `tool` messages.
* **Writing Reliable Tools (`@tool`):** Defining clear `snake_case` names, type hints, descriptive docstrings, and graceful error messages.
* **Agent Execution (`create_agent`):** Orchestrating the `Think → Act → Observe` loop and inspecting execution traces via `.pretty_print()`.
* **Rate Limits & Resilience:** Handling HTTP `429` limits with `max_retries=3` and `try / except` blocks.
* **Structured Output (`Pydantic`):** Enforcing schemas, `Literal` constraints, and numeric bounds (`ge=1`) with `.with_structured_output()`.
* **Database Persistence (`gspread`):** Authenticating in Google Colab and appending validated rows to Google Sheets.

---

## 🛠️ Setup & Prerequisites

1. **Environment:** Google Colab (required for `google.colab.auth` Google Sheets authentication).
2. **Dependencies:** Install LangChain, Groq, Pydantic, and `gspread`:
   ```bash
   pip install -q langchain langchain-groq gspread pydantic
