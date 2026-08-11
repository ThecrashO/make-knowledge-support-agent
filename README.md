🌐 **[🇬🇧 English](./README.md)** | [🇲🇲 မြန်မာ](./README.mm.md)

# 🤖 AI Knowledge Support Agent (Telegram Bot)

An AI-powered automated customer support Telegram Bot built on **Make.com**. It leverages an **AI Local Agent** with **RAG (Retrieval-Augmented Generation)** to answer customer questions based on uploaded company PDF documentation, backed by a real-time **Web Search** fail-safe and **Multi-turn Conversational Memory**.

![Scenario Flow](./workflow-diagram.png)

---

## 🎯 Why This Exists

Most customer questions coming into a small business's Telegram or chat are the same handful of things over and over — "what are your store hours," "do you have a branch in X," "what's your warranty policy," "how do I fix Y." Answering these manually means a real staff member has to be online to reply, customers wait when no one's available, and the same answer gets typed out dozens of times a week.

This agent takes that repetitive load off your team. It reads your own company documentation (PDF policies, FAQs, product info), answers customer questions instantly and accurately based on it, and only falls back to a live web search if the answer genuinely isn't in your documents. It remembers the conversation as it goes, so customers don't have to repeat themselves — and it replies in natural, polite Burmese as if a real staff member were typing.

**Who it's for:** small businesses, retail shops, and service providers who get repetitive customer questions through Telegram and want instant, accurate, always-on answers without hiring extra support staff.

---

## ✅ What You Get

- **24/7 availability:** customers get answered instantly, day or night, without anyone on your team being online.
- **Answers grounded in your own docs:** the agent prioritizes your uploaded PDF documentation first, which keeps answers accurate and prevents the AI from making things up.
- **A safety net for gaps:** if something isn't covered in your documents, it can search the live web instead of guessing or going silent.
- **Natural, ongoing conversations:** it remembers each customer's chat history, so follow-up questions get context-aware answers instead of generic ones.
- **A human-sounding rep, not a bot:** tuned to reply in warm, polite, natural Burmese — customers get a real support experience, not a robotic one.

---

## 🔗 Quick Links

- **🚀 Make.com Shared Scenario (1-Click Import):** [Clone Scenario on Make.com](https://us2.make.com/public/shared-scenario/nLJkutefBEu/knowledge-support-agent)
- **📦 GitHub Repository:** [https://github.com/ThecrashO/make-knowledge-support-agent.git](https://github.com/ThecrashO/make-knowledge-support-agent.git)

---

## 🔄 Workflow Architecture

1. **Trigger:** `Telegram (Watch Updates)` — Captures incoming customer messages via Webhook.
2. **AI Processing:** `Make AI Local Agent` —
   - **Primary Source (RAG):** Searches internal company **PDF Documentation** using semantic vector search.
   - **Secondary Source (Fail-safe):** Uses **Make AI Web Search** if the PDF lacks the answer or if real-time web data is requested.
   - **Chat Memory:** Remembers conversation history per user using `Thread ID = {{2.message.chat.id}}`.
3. **Action:** `Telegram (Send Reply Message)` — Delivers clear, polite, and well-formatted answers back to the user instantly.

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
- **AI Provider Connection** (OpenAI, Google Gemini, Anthropic Claude, etc.)
- **Company Knowledge Document (PDF)**

---

## 🚀 How to Import & Setup on Make.com

### Method 1: 1-Click Import (Recommended)
1. Open the [Make.com Shared Scenario Link](https://us2.make.com/public/shared-scenario/nLJkutefBEu/knowledge-support-agent).
2. Click **Clone Scenario** to import it directly into your Make.com workspace.

### Method 2: Manual Blueprint Import
1. Clone this repository:
   ```bash
   git clone https://github.com/ThecrashO/make-knowledge-support-agent.git
   ```
2. In Make.com, create a new scenario and select **Import Blueprint** (from the three dots menu at the bottom toolbar).
3. Upload `Knowledge Support Agent.blueprint.json`.

---

## ⚙️ Configuration Steps

1. **Setup Connections:**
   - Connect your Telegram Bot Webhook (Module 2).
   - Connect your AI Provider (Module 7).
   - Connect your Telegram Bot Connection (Module 6).
2. **Upload Knowledge Document:**
   - Open Module 9 (Agent Knowledge) and upload your company policy/FAQ PDF.
3. **Enable Chat Memory:**
   - In Module 7, map Thread ID to `{{2.message.chat.id}}` and set Maximum conversation history to 10.
4. **Turn ON** the scenario schedule.

---

📘 For detailed, step-by-step setup instructions, see [`SETUP-GUIDE-EN.md`](./SETUP-GUIDE-EN.md) (English) or [`SETUP-GUIDE-MY.md`](./SETUP-GUIDE-MY.md) (Burmese).
