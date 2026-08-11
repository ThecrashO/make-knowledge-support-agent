# Knowledge Support Agent — တပ်ဆင်နည်း လမ်းညွှန် (Setup Guide)

ဒီ scenario ဟာ Telegram bot တစ်ခုကို AI-powered customer support agent တစ်ခု အဖြစ် ပြောင်းပေးပါတယ်။ ဝင်လာတဲ့ Telegram message တွေကို စောင့်ကြည့်ပြီး၊ AI agent က သင် upload လုပ်ထားတဲ့ PDF documentation ကို အခြေခံပြီး အဖြေပေးပါတယ် (document ထဲ အဖြေမရှိရင် live web search ကို fallback အနေနဲ့ သုံးပါတယ်)၊ user တစ်ယောက်ချင်းစီရဲ့ conversation ကို မှတ်ထားပြီး Telegram ထဲ ချက်ချင်း ပြန်ဖြေပေးပါတယ်။

**Flow:** `Telegram (Watch Updates)` → `AI Agent (RAG + Web Search)` → `Telegram (Send Reply)`

---

## လိုအပ်ချက်များ (Prerequisites)

Import မလုပ်ခင် အောက်ပါတွေ ပြင်ဆင်ထားပါ -

- [Make.com](https://www.make.com) account (Free plan နဲ့လည်း စမ်းသပ်လို့ရပါတယ်)
- [@BotFather](https://t.me/BotFather) ကနေ ဖန်တီးထားတဲ့ Telegram bot — **bot token** လိုအပ်ပါမယ်
- Make ထဲမှာ ချိတ်ဆက်ထားတဲ့ AI provider account (OpenAI, Google Gemini, Anthropic Claude, စသည်)
- သင့် company ရဲ့ knowledge documentation ကို **PDF file** အနေနဲ့ (ဆိုင်ဖွင့်ချိန်၊ policy၊ warranty terms၊ FAQ၊ product info စသည်) — agent က ဒီထဲကနေ အဖြေပေးမှာဖြစ်ပါတယ်

---

## အဆင့် ၁ — Template ကို Import လုပ်ခြင်း

Scenario ကို အစကနေ ပြန်ဆောက်စရာ မလိုပါဘူး။ အောက်က နည်းလမ်း ၂ ခုထဲက တစ်ခုကို ရွေးပါ။

### နည်းလမ်း A — File ကနေ Import လုပ်ခြင်း
1. ဒီ repository ထဲက `Knowledge Support Agent.blueprint.json` ကို download လုပ်ပါ (ဒါမှမဟုတ် repo ကို clone လုပ်ပါ - `git clone https://github.com/ThecrashO/make-knowledge-support-agent.git`)။
2. Make.com ထဲ login ဝင်ပြီး **Scenarios** သို့ သွားပါ။
3. **Create a new scenario** ကို click နှိပ်ပြီး module picker ကို ပိတ်လိုက်ပါ။
4. အောက်ခြေ toolbar ရဲ့ **⋮ (dots သုံးလုံး)** menu → **Import Blueprint** ကို နှိပ်ပါ။
5. Download လုပ်ထားတဲ့ `.json` file ကို ရွေးပြီး **Save** နှိပ်ပါ။

### နည်းလမ်း B — Link ကနေ တိုက်ရိုက် Import လုပ်ခြင်း
1. [Make.com Shared Scenario Link](https://us2.make.com/public/shared-scenario/nLJkutefBEu/knowledge-support-agent) ကို ဖွင့်ပါ။
2. **Clone Scenario** / **Use this template** ကို click နှိပ်ပါ။
3. Import လုပ်ချင်တဲ့ workspace/team ကို ရွေးချယ် confirm လုပ်ပါ။

နည်းလမ်း ဘယ်ဟာနဲ့ လုပ်လုပ် canvas ပေါ်မှာ module ၃ ခု တွေ့ရပါလိမ့်မယ် — **Watch Updates → AI Agent → Send Reply Message**။

---

## အဆင့် ၂ — Telegram ချိတ်ဆက်ခြင်း (Trigger)

1. **Telegram (Watch Updates)** module (module 2) ကို ဖွင့်ပါ။
2. **Webhook** အောက်မှာ **Add** ကို နှိပ်ပါ။
3. BotFather ကနေ ရထားတဲ့ **bot token** ကို ထည့်ပြီး webhook ကို အမည်တစ်ခု ပေးပါ။
4. Save လုပ်ပါ။ Make က webhook ကို Telegram နဲ့ အလိုအလျောက် register လုပ်ပေးပါလိမ့်မယ် — manual URL setup လုပ်စရာ မလိုပါဘူး။

---

## အဆင့် ၃ — Telegram ချိတ်ဆက်ခြင်း (Reply)

1. **Telegram (Send Reply Message)** module (module 6) ကို ဖွင့်ပါ။
2. **Connection** အောက်မှာ **Add** ကို နှိပ်ပြီး bot connection အတူတူကို ပြန်သုံးနိုင်သလို bot token အတူတူနဲ့ connection အသစ်လည်း ဖန်တီးနိုင်ပါတယ်။
3. **Chat ID** ကို `{{2.message.chat.id}}` အတိုင်း ထားလိုက်ပါ — ဒါမှသာ message ပို့တဲ့ user ဆီကို အဖြေ ပြန်ရောက်မှာဖြစ်ပါတယ်။

---

## အဆင့် ၄ — AI Agent ကို ချိန်ညှိခြင်း

1. **AI Agent** module (module 7) ကို ဖွင့်ပါ။
2. **Connection** အောက်မှာ **Add** ကို နှိပ်ပြီး သင့် AI provider account (OpenAI, Google Gemini, Anthropic, စသည်) ကို ချိတ်ဆက်ပါ။
3. သင့် provider/plan က support လုပ်တဲ့ model ကို ရွေးပါ။
4. **Instructions (system prompt)** ကို ပြန်ကြည့်ပါ — default အနေနဲ့ ယဉ်ကျေးတဲ့ male customer support representative အနေနဲ့ သဘာဝကျတဲ့ မြန်မာစကားနဲ့ ဖြေပေးအောင် ကြိုတင်ရေးထားပါတယ်။ ဒါကို သင့် business အမည်၊ persona (male/female)၊ tone၊ ပြီးတော့ specific rule များ (ဥပမာ - အချက်အလက်မရှိရင် ဘယ်လိုပြောရမလဲ) နဲ့ ကိုက်ညီအောင် ပြင်ဆင်ပါ။

### Knowledge Document Upload လုပ်ခြင်း
1. AI Agent module ထဲက **Agent knowledge** tool (module 9) ကို ဖွင့်ပါ။
2. **Knowledge files** အောက်မှာ placeholder file ကို ဖြုတ်ပြီး၊ သင့် company ရဲ့ PDF (policy, FAQ, product/service info, ဆိုင်အသေးစိတ် စသည်) ကို upload လုပ်ပါ။
3. Save လုပ်ပါ။

### Chat Memory Enable လုပ်ခြင်း
1. AI Agent module ထဲမှာပဲ **Thread ID** ကို `{{2.message.chat.id}}` အတိုင်း သတ်မှတ်ထားမလားဆိုတာ သေချာစစ်ပါ — ဒါမှ Telegram user တစ်ယောက်ချင်းစီရဲ့ conversation ကို သီးခြားစီ မှတ်ထားနိုင်မှာဖြစ်ပါတယ်။
2. **Model configuration** အောက်မှာ **Maximum conversation history** ကို (ဥပမာ - `10` သို့မဟုတ် `20`) သတ်မှတ်ပြီး user တစ်ယောက်ချင်းစီအတွက် agent က message ဟောင်း ဘယ်နှစ်ခုအထိ မှတ်ထားမလဲ ချိန်ညှိပါ။

### Web Search Tool
**Web Search** tool (module 8) ဟာ knowledge base ထဲမှာ အဖြေမရှိတဲ့အခါမှသာ အလုပ်လုပ်အောင် သတ်မှတ်ထားပါတယ်။ ပုံမှန်အားဖြင့် ထပ်မံ setup လုပ်စရာ မလိုပါဘူး၊ ဒါပေမဲ့ သင့် Make plan/region အတွက် enable ဖြစ်နေမနေ စစ်ဆေးပါ။

---

## အဆင့် ၅ — Scenario ကို စမ်းသပ်ခြင်း

1. Make canvas ရဲ့ အောက်ခြေက **Run once** ကို နှိပ်ပါ။
2. Telegram ဖွင့်ပြီး သင့် bot ကို test message တစ်ခု ပို့ကြည့်ပါ (ဥပမာ - "ဆိုင်ဖွင့်ချိန် ဘယ်လောက်လဲ")။
3. Module တစ်ခုချင်းစီရဲ့ output ကို စစ်ဆေးပါ (အစိမ်းရောင် check mark = အောင်မြင်ပါပြီ)။ အောက်ပါအတိုင်း ဖြစ်နေမနေ သေချာစစ်ပါ -
   - AI Agent က သင် upload လုပ်ထားတဲ့ PDF ကနေ အဖြေထုတ်ပေးမလား
   - Telegram chat ထဲမှာ သင်ချိန်ညှိထားတဲ့ tone/persona အတိုင်း အဖြေ ပေါ်လာမလား
   - Chat တစ်ခုတည်းထဲမှာ ဆက်တိုက်မေးတဲ့ မေးခွန်းတွေက context ကို သိပြီး ဖြေမလား (memory အလုပ်လုပ်နေတယ်ဆိုတာ)

---

## အဆင့် ၆ — Activate လုပ်ခြင်း

1. Scenario ကို activate လုပ်ဖို့ ဘယ်ဘက်အပေါ်ထောင့်က switch ကို **ON** ပြောင်းပါ။
2. ဒီ scenario ဟာ trigger-based (`instant: true`) ဖြစ်တဲ့အတွက် Telegram message အသစ် ဝင်လာတိုင်း real-time ပြန်ဖြေပါလိမ့်မယ် — polling schedule သတ်မှတ်စရာ မလိုပါဘူး။

---

## ပြဿနာဖြေရှင်းနည်း (Troubleshooting)

| ပြဿနာ | ဖြစ်နိုင်ချေအကြောင်းရင်း |
|---|---|
| "Connection not set up" error | Telegram webhook, AI provider, ဒါမှမဟုတ် Telegram reply connection ကို authorize မလုပ်ရသေးဘူး — အဆင့် ၂-၄ ကို ပြန်လုပ်ပါ |
| Bot က လုံးဝ ပြန်မဖြေဘူး | Scenario ON မပြောင်းရသေးဘူး၊ ဒါမှမဟုတ် webhook register မဖြစ်ဘူး — Telegram connection ကို ပြန်ထည့်ကြည့်ပါ |
| Agent က generic/မသက်ဆိုင်တဲ့ အဖြေတွေ ပေးနေတယ် | Knowledge PDF upload မလုပ်ရသေးဘူး၊ ဒါမှမဟုတ် document ထဲမှာ ဒီအချက်အလက် မပါဘူး |
| Agent က ယခင် message တွေ မေ့နေတယ် | Thread ID ကို `{{2.message.chat.id}}` နဲ့ map မလုပ်ရသေးဘူး၊ ဒါမှမဟုတ် conversation history limit နည်းလွန်းတယ် |
| Agent က "PDF" / "document" ဆိုပြီး ပြောနေတယ် / robot လို ဖြစ်နေတယ် | System prompt ကို ပြန်ကြည့်ပါ — persona ကို သဘာဝကျအောင် ထားတဲ့ strict wording rule တွေ ပါဝင်ပါတယ်၊ မှားယွင်း ဖျက်မိသလားလို့ စစ်ပါ |

---

မေးခွန်း သို့မဟုတ် ပြဿနာ ရှိရင် ဒီ repository မှာ issue တစ်ခု ဖွင့်ပေးပါ။
