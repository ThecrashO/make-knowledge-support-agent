# Knowledge Support Agent — Setup Guide

This scenario turns a Telegram bot into an AI-powered customer support agent. It listens for incoming Telegram messages, has an AI agent answer them using your uploaded PDF documentation (with live web search as a fallback), remembers the conversation per user, and replies instantly in Telegram.

**Flow:** `Telegram (Watch Updates)` → `AI Agent (RAG + Web Search)` → `Telegram (Send Reply)`

---

## Prerequisites

Before importing, make sure you have:

- A [Make.com](https://www.make.com) account (Free tier works for testing)
- A Telegram bot created via [@BotFather](https://t.me/BotFather) — you'll need the **bot token**
- An AI provider account connected in Make (OpenAI, Google Gemini, Anthropic Claude, or another supported provider)
- Your company's knowledge documentation as a **PDF file** (store hours, policies, warranty terms, FAQs, product info, etc.) — this is what the agent will answer from

---

## Step 1 — Import the Template

You don't need to build the scenario from scratch. Choose one of the two options below.

### Option A — Import from file
1. Download `Knowledge Support Agent.blueprint.json` from this repository (or clone the repo: `git clone https://github.com/ThecrashO/make-knowledge-support-agent.git`).
2. Log in to Make.com and go to **Scenarios**.
3. Click **Create a new scenario**, then close the module picker.
4. Click the **⋮ (three dots)** menu in the bottom toolbar → **Import Blueprint**.
5. Select the downloaded `.json` file and click **Save**.

### Option B — Import via link
1. Open the [Make.com Shared Scenario Link](https://us2.make.com/public/shared-scenario/nLJkutefBEu/knowledge-support-agent).
2. Click **Clone Scenario** / **Use this template**.
3. Confirm the workspace/team you want to import it into.

Either way, you should now see 3 modules laid out on the canvas: **Watch Updates → AI Agent → Send Reply Message**.

---

## Step 2 — Connect Telegram (Trigger)

1. Open the **Telegram (Watch Updates)** module (module 2).
2. Under **Webhook**, click **Add**.
3. Paste in your **bot token** (from BotFather) and give the webhook a name.
4. Save. Make will register the webhook with Telegram automatically — no manual URL setup needed.

---

## Step 3 — Connect Telegram (Reply)

1. Open the **Telegram (Send Reply Message)** module (module 6).
2. Under **Connection**, click **Add** and either reuse the same bot connection or create a new one with the same bot token.
3. Leave **Chat ID** as `{{2.message.chat.id}}` — this makes sure replies go back to whichever user sent the message.

---

## Step 4 — Set Up the AI Agent

1. Open the **AI Agent** module (module 7).
2. Under **Connection**, click **Add** and connect your AI provider account (OpenAI, Google Gemini, Anthropic, etc.).
3. Choose a model your connected provider/plan supports.
4. Review the **Instructions (system prompt)** — it's pre-written to act as a polite male customer support representative replying in natural Burmese. Edit this to match your own business name, persona (male/female), tone, and any specific rules (e.g., what to say when information is missing).

### Upload your knowledge document
1. Inside the AI Agent module, open the **Agent knowledge** tool (module 9).
2. Under **Knowledge files**, remove the placeholder file reference and upload your own company PDF (policies, FAQs, product/service info, store details, etc.).
3. Save.

### Enable chat memory
1. Still inside the AI Agent module, confirm **Thread ID** is set to `{{2.message.chat.id}}` — this keeps each Telegram user's conversation separate and remembered.
2. Under **Model configuration**, set **Maximum conversation history** (e.g., `10` or `20`) to control how many past messages the agent recalls per user.

### Web Search tool
The **Web Search** tool (module 8) is set to only trigger when the knowledge base doesn't have the answer. No extra setup is normally required, but confirm it's enabled for your Make plan/region.

---

## Step 5 — Test the Scenario

1. Click **Run once** at the bottom of the Make canvas.
2. Open Telegram and send your bot a test message (e.g., "What are your store hours?").
3. Check each module's output (green checkmark = success). Confirm:
   - The AI Agent pulls an answer from your uploaded PDF
   - The reply appears in your Telegram chat, in the tone/persona you configured
   - Follow-up questions in the same chat get context-aware answers (memory working)

---

## Step 6 — Activate

1. Toggle the scenario **ON** (top-left switch).
2. Since this scenario is trigger-based (`instant: true`), it will respond to new Telegram messages in real time — no polling schedule needed.

---

## Troubleshooting

| Issue | Likely Cause |
|---|---|
| "Connection not set up" error | Telegram webhook, AI provider, or Telegram reply connection not authorized — repeat Steps 2–4 |
| Bot doesn't reply at all | Scenario isn't turned ON, or the webhook wasn't registered — try re-adding the Telegram connection |
| Agent gives generic/unrelated answers | Knowledge PDF not uploaded, or the document doesn't contain the relevant info |
| Agent forgets earlier messages | Thread ID isn't mapped to `{{2.message.chat.id}}`, or conversation history limit is too low |
| Agent mentions "PDF" / "document" / sounds robotic | Adjust the system prompt — it includes strict wording rules to keep the persona natural; check they weren't accidentally edited out |

---

Questions or issues? Open an issue in this repository.
