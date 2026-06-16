# AI 短影音工廠（批量產內容 → 流量變現）

一句話腳本 → 自動產出帶配音、配樂、封面的成品短影音，規模化經營流量帳號。

**Monetization**：①自營 TikTok/Reels/Shorts 帳號衝流量，影片描述掛工具/主機商聯盟（非 VPN）②代製接案 ③模板/prompt 包販售。網頁端掛 Adsterra/Monetag，廣告只放網頁端。

**How it works**：選題 agent 產腳本 → Sulphur-2 生影片片段 → supertonic 配旁白 → stable-audio-3 配樂 → Lens 生封面 → 自動剪接上字幕 → 排程發佈。lanshu kit 提供現成 prompt 庫加速。

**Difficulty**：medium · **Effort**：2–3 週做出能跑的 pipeline；難點在剪接串接與發佈自動化，模型都現成。

## Open-source parts

- [SulphurAI/Sulphur-2-base](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-sulphurai-sulphur-2-base/) — text-to-video · diffusers, safetensors, gguf
- [Supertone/supertonic-3](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-supertone-supertonic-3/) — text-to-speech · supertonic, onnx, text-to-speech
- [stabilityai/stable-audio-3-medium](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-stabilityai-stable-audio-3-medium/) — text-to-audio · stable-audio-3, safetensors, audio-generation
- [microsoft/Lens](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-microsoft-lens/) — text-to-image · diffusers, safetensors, text-to-image
- [cclank/lanshu-awesome-ai-video-kit](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/cclank-lanshu-awesome-ai-video-kit/) — 做企业 AI 视频项目逼出来的工具包 · 411 prompt · 15 模型 · 7 Claude Skill · 14 篇方法论
