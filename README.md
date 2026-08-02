# 🤖 AI Knowledge Support Agent (Telegram Bot)

An AI-powered automated customer support Telegram Bot built on **Make.com**. It leverages **Google Gemini 3.1 Pro** with **RAG (Retrieval-Augmented Generation)** to answer customer questions based on uploaded company PDF documentation, backed by a real-time **Web Search** fail-safe and **Multi-turn Conversational Memory**.

---

## 🔗 Quick Links

- **🚀 Make.com Shared Scenario (1-Click Import):** [Clone Scenario on Make.com](https://us2.make.com/public/shared-scenario/GZmmJTjBnkz/knowledge-support-agent)
- **📦 GitHub Repository:** [https://github.com/ThecrashO/make-knowledge-support-agent.git](https://github.com/ThecrashO/make-knowledge-support-agent.git)

---

## 🔄 Workflow Architecture

1. **Trigger:** `Telegram (Watch Updates)` - Captures incoming customer messages via Webhook.
2. **AI Processing:** `Make AI Local Agent (Gemini 3.1 Pro)` -
   - **Primary Source (RAG):** Searches internal company **PDF Documentation** using semantic vector search.
   - **Secondary Source (Fail-safe):** Uses **Make AI Web Search** if the PDF lacks the answer or if real-time web data is requested.
   - **Chat Memory:** Remembers conversation history per user using `Thread ID = {{2.message.chat.id}}`.
3. **Action:** `Telegram (Send Reply Message)` - Delivers clear, polite, and well-formatted answers back to the user instantly.

---

## ✨ Key Features

- **24/7 Automated Customer Support** on Telegram.
- **RAG Architecture:** Prioritizes official company documentation to eliminate AI hallucinations.
- **Web Search Fallback:** Searches the live internet if internal documents lack information.
- **Multi-turn Conversational Memory:** Maintains context across previous user interactions.
- **Humanized Persona:** Fine-tuned to speak in natural, polite Burmese as an official male store representative ("ကျွန်တော်/ခင်ဗျာ").

---

## 🛠️ Prerequisites

- **Make.com Account**
- **Telegram Bot Token** (from `@BotFather`)
- **Google Gemini AI Provider Connection**
- **Company Knowledge Document (PDF)**

---

## 🚀 How to Import & Setup on Make.com

### Method 1: 1-Click Import (Recommended)
1. Open the [Make.com Shared Scenario Link](https://us2.make.com/public/shared-scenario/GZmmJTjBnkz/knowledge-support-agent).
2. Click **Clone Scenario** to import it directly into your Make.com workspace.

### Method 2: Manual Blueprint Import
1. Clone this repository:
   ```bash
   git clone https://github.com/ThecrashO/make-knowledge-support-agent.git

2.  In Make.com, create a new scenario and select Import Blueprint (from the
    three dots menu at the bottom toolbar).
3.  Upload Knowledge Support Agent.blueprint.json.

⚙️ Configuration Steps

1.  Setup Connections:
      - Connect your Telegram Bot Webhook (Module 2).
      - Connect your Gemini AI Provider (Module 7).
      - Connect your Telegram Bot Connection (Module 6).
2.  Upload Knowledge Document:
      - Open Module 9 (Agent Knowledge) and upload your company policy/FAQ PDF.
3.  Enable Chat Memory:
      - In Module 7, map Thread ID to {{2.message.chat.id}} and set Maximum
        conversation history to 10.
4.  Turn ON the scenario schedule.


---
