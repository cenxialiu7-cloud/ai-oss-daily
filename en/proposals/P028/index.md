# AI 電話語音 Agent：自動接聽/外撥，幫在地服務業做預約、提醒、客服

用電信 API＋開源語音模型，做一支會講中文、能接聽與外撥的 AI 電話 agent，幫診所/餐廳/美容做預約確認、提醒與基本客服。

**Monetization**：①SaaS 月費（按分鐘/座席，賣給在地服務業/小型客服中心）②建置代設定服務一次性收費 ③模板/話術包買斷（MoR）④電信服務聯盟（號碼/分鐘數，非 VPN）。落地頁 Adsterra/Monetag＋Ko-fi。

**How it works**：Telnyx 接通電話/外撥 → nemotron 串流 ASR 把語音轉文字 → LFM2.5 本機 LLM 判斷意圖(預約/改期/問題)並查行事曆/FAQ → Inflect-Nano 低延遲 TTS 回話 → 需要時發 SMS 確認。全程可本機/私有部署，通話內容不外流。

**Difficulty**：high · **Effort**：4–6 週；難點在電話即時延遲(ASR↔LLM↔TTS 串接<1 秒)與中文語音品質，先做單一情境(預約提醒)MVP。

## Open-source parts

- [team-telnyx/telnyx-code-examples](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/team-telnyx-telnyx-code-examples/) — Production-ready code examples for Telnyx AI Communications Infrastructure — Voice AI, SMS, SIP, and IoT APIs
- [nvidia/nemotron-3.5-asr-streaming-0.6b](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-nvidia-nemotron-3-5-asr-streaming-0-6b/) — automatic-speech-recognition · nemo, speech-recognition, cache-aware ASR
- [LiquidAI/LFM2.5-8B-A1B](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-liquidai-lfm2-5-8b-a1b/) — text-generation · transformers, safetensors, lfm2_moe
- [owensong/Inflect-Nano-v1](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-owensong-inflect-nano-v1/) — text-to-speech · pytorch, text-to-speech, tts
