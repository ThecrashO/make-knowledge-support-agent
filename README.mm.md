🌐 [🇬🇧 English](./README.md) | **[🇲🇲 မြန်မာ](./README.mm.md)**

# 🤖 AI Knowledge Support Agent (Telegram Bot)

**Make.com** ပေါ်မှာ တည်ဆောက်ထားတဲ့ AI-powered customer support Telegram Bot တစ်ခုပါ။ **RAG (Retrieval-Augmented Generation)** စွမ်းရည်ပါဝင်တဲ့ **AI Local Agent** ကို သုံးပြီး company ရဲ့ upload လုပ်ထားတဲ့ PDF documentation ပေါ်မူတည်ကာ customer မေးခွန်းများကို ဖြေကြားပေးပါတယ်၊ real-time **Web Search** fail-safe နဲ့ **Multi-turn Conversational Memory** ကလည်း backup အနေနဲ့ ပါဝင်ပါတယ်။

---

## 🎯 ဘာကြောင့် ဒီ Tool ကို ဖန်တီးထားလဲ

Business သေးသေးလေးတွေရဲ့ Telegram/chat ထဲ ဝင်လာတဲ့ customer မေးခွန်း အများစုက "ဆိုင်ဖွင့်ချိန်ဘယ်လောက်လဲ"၊ "X မှာ branch ရှိလား"၊ "warranty policy ဘယ်လိုလဲ"၊ "Y ကို ဘယ်လိုပြင်ရမလဲ" — ဆိုပြီး ထပ်ခါထပ်ခါ ကျရောက်နေတဲ့ မေးခွန်းအမျိုးအစား အနည်းငယ်ပါပဲ။ ဒါတွေကို manual ဖြေရင် staff တစ်ယောက် online ရှိနေရမယ်၊ ဘယ်သူမှ မရှိတဲ့အချိန်ဆို customer စောင့်ရမယ်၊ တစ်ပတ်ကို အဖြေတူတူကို ဆယ်ချီပြီး ပြန်ရိုက်ပေးနေရမယ်။

ဒီ agent က ဒီထပ်ခါထပ်ခါလုပ်ရတဲ့ ဝန်ကို team ဆီက ဖယ်ရှားပေးပါတယ်။ Company ရဲ့ documentation (PDF policy, FAQ, product info) ကို ဖတ်ပြီး၊ customer မေးခွန်းကို ချက်ချင်းနဲ့ တိကျစွာ ဖြေပေးပါတယ်၊ document ထဲမှာ တကယ့်ကို အဖြေမရှိမှသာ live web search ဆီ ပြန်သွားပါတယ်။ စကားပြောနေတဲ့ အတိုင်း conversation ကို မှတ်ထားတဲ့အတွက် customer က ထပ်ရှင်းပြစရာ မလိုတော့ဘူး — ပြီးတော့ staff တကယ့်ကလေးက ရိုက်နေသလို သဘာဝကျတဲ့ ယဉ်ကျေးသော မြန်မာစကားနဲ့ ဖြေပေးပါတယ်။

**ဘယ်သူတွေအတွက်လဲ:** Telegram ကနေ ထပ်ခါထပ်ခါ customer မေးခွန်း ဝင်နေတဲ့ business သေးသေး၊ ဆိုင်ခွဲများနဲ့ service provider တွေအတွက် — support staff ထပ်မံငှားရမ်းစရာ မလိုဘဲ ချက်ချင်း၊ တိကျစွာ၊ အချိန်မရွေး ဖြေကြားပေးနိုင်တဲ့ tool လိုချင်သူများ။

---

## ✅ ဘာတွေ ရရှိမလဲ

- **၂၄ နာရီ အမြဲ ဖြေကြားနိုင်တယ်:** ရော့ ညအချိန်ပဲ ဖြစ်ဖြစ် team ထဲက ဘယ်သူမှ online မရှိစေဘဲ customer ကို ချက်ချင်း ဖြေပေးတယ်။
- **သင့်ရဲ့ document ပေါ်မူတည်ပြီး တိကျတဲ့ အဖြေ:** Agent က သင် upload လုပ်ထားတဲ့ PDF documentation ကို ဦးစားပေး သုံးတဲ့အတွက် AI က ကိုယ်ပိုင်ဖန်တီးပြီး မမှန်တဲ့ အဖြေမပေးဘဲ တိကျမှု ရှိနေစေတယ်။
- **အချက်အလက် ကျန်နေရင်လည်း Safety Net ရှိတယ်:** Document ထဲ မပါတဲ့ အကြောင်းအရာဆို ခန့်မှန်း/ဆိတ်ဆိတ်နေမယ့်အစား live web search ကို သွားရှာပေးတယ်။
- **သဘာဝကျတဲ့ ဆက်တိုက် စကားပြောနိုင်တယ်:** Customer တစ်ယောက်ချင်းရဲ့ chat history ကို မှတ်ထားလို့ ဆက်လက်မေးတဲ့ မေးခွန်းတွေကို context နဲ့ ချိန်ညှိပြီး ဖြေပေးတယ် (generic အဖြေ မဟုတ်ဘူး)။
- **Bot လိုမဟုတ်ဘဲ လူသားလို ဖြေကြားပေးတဲ့ rep:** Warm ပြီး ယဉ်ကျေးတဲ့ သဘာဝကျသော မြန်မာစကားနဲ့ ဖြေဖို့ ချိန်ညှိထားတဲ့အတွက် customer တွေက robot နဲ့ စကားပြောနေသလို မဟုတ်ဘဲ တကယ့် support experience ရရှိတယ်။

---

## 🔗 Quick Links

- **🚀 Make.com Shared Scenario (1-Click Import):** [Clone Scenario on Make.com](https://us2.make.com/public/shared-scenario/nLJkutefBEu/knowledge-support-agent)
- **📦 GitHub Repository:** [https://github.com/ThecrashO/make-knowledge-support-agent.git](https://github.com/ThecrashO/make-knowledge-support-agent.git)

---

## 🔄 Workflow Architecture

1. **Trigger:** `Telegram (Watch Updates)` — Webhook ကနေ customer message ဝင်လာတာကို ဖမ်းယူတယ်။
2. **AI Processing:** `Make AI Local Agent` —
   - **Primary Source (RAG):** Semantic vector search သုံးပြီး company ရဲ့ internal **PDF Documentation** ထဲကို ရှာဖွေတယ်။
   - **Secondary Source (Fail-safe):** PDF ထဲ အဖြေမရှိရင် သို့မဟုတ် real-time web data လိုအပ်ရင် **Make AI Web Search** ကို သုံးတယ်။
   - **Chat Memory:** `Thread ID = {{2.message.chat.id}}` ကို သုံးပြီး user တစ်ယောက်ချင်းစီရဲ့ conversation history ကို မှတ်ထားတယ်။
3. **Action:** `Telegram (Send Reply Message)` — ရှင်းလင်း၊ ယဉ်ကျေးပြီး formatting လှတဲ့ အဖြေကို user ဆီ ချက်ချင်း ပြန်ပို့တယ်။

---

## ✨ အဓိက Feature များ

- Telegram ပေါ်မှာ **၂၄/၇ Automated Customer Support**။
- **RAG Architecture:** AI hallucination ကို ဖယ်ရှားဖို့ official company documentation ကို ဦးစားပေးသုံးတယ်။
- **Web Search Fallback:** Internal document ထဲ အချက်အလက် မရှိရင် live internet ထဲကို ရှာပေးတယ်။
- **Multi-turn Conversational Memory:** ယခင် user interaction တွေရဲ့ context ကို ဆက်လက် ထိန်းသိမ်းထားတယ်။
- **Humanized Persona:** Official male store representative ("ကျွန်တော်/ခင်ဗျာ") အနေနဲ့ သဘာဝကျ၊ ယဉ်ကျေးသော မြန်မာစကားနဲ့ ပြောစေဖို့ fine-tune လုပ်ထားတယ်။

---

## 🛠️ လိုအပ်ချက်များ (Prerequisites)

- **Make.com Account**
- **Telegram Bot Token** (`@BotFather` ကနေ ရယူရမယ်)
- **AI Provider Connection** (OpenAI, Google Gemini, Anthropic Claude, စသည်)
- **Company Knowledge Document (PDF)**

---

## 🚀 Make.com ထဲ Import & Setup လုပ်နည်း

### နည်းလမ်း ၁: 1-Click Import (အကြံပြုချင်တာ)
1. [Make.com Shared Scenario Link](https://us2.make.com/public/shared-scenario/nLJkutefBEu/knowledge-support-agent) ကို ဖွင့်ပါ။
2. **Clone Scenario** ကို click နှိပ်ပြီး သင့် Make.com workspace ထဲ တိုက်ရိုက် import လုပ်ပါ။

### နည်းလမ်း ၂: Manual Blueprint Import
1. ဒီ repository ကို clone လုပ်ပါ -
   ```bash
   git clone https://github.com/ThecrashO/make-knowledge-support-agent.git
   ```
2. Make.com ထဲမှာ scenario အသစ်တစ်ခု ဖန်တီးပြီး အောက်ခြေ toolbar ရဲ့ dots သုံးလုံး menu ကနေ **Import Blueprint** ကို ရွေးပါ။
3. `Knowledge Support Agent.blueprint.json` ကို upload လုပ်ပါ။

---

## ⚙️ Configuration အဆင့်များ

1. **Connection များ ချိတ်ဆက်ခြင်း:**
   - Telegram Bot Webhook ကို ချိတ်ပါ (Module 2)။
   - AI Provider ကို ချိတ်ပါ (Module 7)။
   - Telegram Bot Connection ကို ချိတ်ပါ (Module 6)။
2. **Knowledge Document Upload လုပ်ခြင်း:**
   - Module 9 (Agent Knowledge) ကို ဖွင့်ပြီး company policy/FAQ PDF ကို upload လုပ်ပါ။
3. **Chat Memory Enable လုပ်ခြင်း:**
   - Module 7 ထဲမှာ Thread ID ကို `{{2.message.chat.id}}` နဲ့ map လုပ်ပြီး Maximum conversation history ကို 10 လို့ သတ်မှတ်ပါ။
4. Scenario schedule ကို **ON** ပြောင်းပါ။

---

📘 အသေးစိတ် setup လမ်းညွှန်ကို [`SETUP-GUIDE-EN.md`](./SETUP-GUIDE-EN.md) (English) သို့မဟုတ် [`SETUP-GUIDE-MY.md`](./SETUP-GUIDE-MY.md) (မြန်မာ) မှာ ကြည့်ပါ။
