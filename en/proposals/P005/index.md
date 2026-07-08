# 本機數位人口播短影音工廠（真人感口播帳號）

用你克隆的音色＋數位人，把一句選題自動變成「真人口播」短影音，量產知識型/帶貨帳號。

**Monetization**：①自營知識型/帶貨數位人帳號衝流量，描述掛工具/帶貨聯盟（非 VPN）②數位人口播代製接案 ③你的音色/人設模板包販售。與你的短視頻變現策略直接對接。

**How it works**：選題 agent 產口播稿 → Qwen3-TTS 用你克隆的音色配音 → LongCat 生成數位人對嘴影片 → 自動上字幕、排程發佈。要做即時互動數位人客服則接 Patter。

**Difficulty**：medium · **Effort**：2–3 週；模型現成，難點在對嘴串接與發佈自動化。

## Open-source parts

- [Qwen/Qwen3-TTS-12Hz-1.7B-CustomVoice](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-qwen-qwen3-tts-12hz-1-7b-customvoice/) — text-to-speech · safetensors, qwen3_tts, text-to-speech
- [meituan-longcat/LongCat-Video-Avatar-1.5](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-meituan-longcat-longcat-video-avatar-1-5/) — · longcat-video-avatar-1.5, onnx, diffusers
- [PatterAI/Patter](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/patterai-patter/) — Open-source voice-AI SDK. The Vapi/Retell alternative for builders who want to own the stack. Give your AI ag…
