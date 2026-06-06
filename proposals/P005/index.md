# 本機數位人口播短影音工廠（真人感口播帳號）

用你克隆的音色＋數位人，把一句選題自動變成「真人口播」短影音，量產知識型/帶貨帳號。

**怎麼變現**：①自營知識型/帶貨數位人帳號衝流量，描述掛 VPN affiliate ②數位人口播代製接案 ③你的音色/人設模板包販售。與你的短視頻變現策略直接對接。

**運作方式**：選題 agent 產口播稿 → Qwen3-TTS 用你克隆的音色配音 → LongCat 生成數位人對嘴影片 → 自動上字幕、排程發佈。要做即時互動數位人客服則接 Patter。

**難度**：medium · **投入估計**：2–3 週；模型現成，難點在對嘴串接與發佈自動化。

## 用到的開源零件

- [Qwen/Qwen3-TTS-12Hz-1.7B-CustomVoice](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-qwen-qwen3-tts-12hz-1-7b-customvoice/) — Qwen3-TTS 自訂音色語音合成（1.7B，可克隆指定音色做配音）。
- [LongCat 數位人影片(美團)](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-meituan-longcat-longcat-video-avatar-1-5/) — 美團 LongCat 的數位人/虛擬主播影片生成模型(diffusers+onnx)。
- [PatterAI/Patter](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/patterai-patter/) — 開源語音 AI SDK，Vapi/Retell 的自主可控替代品（自建語音對話）。
- [Qwen3.6-27B（通義千問大模型）](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-qwen-qwen3-6-27b/) — 阿里 Qwen 系列大模型，下載量近 500 萬，中文社群採用度極高。
