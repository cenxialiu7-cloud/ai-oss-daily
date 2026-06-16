# AI 短影音工廠（批量產內容 → 流量變現）

一句話腳本 → 自動產出帶配音、配樂、封面的成品短影音，規模化經營流量帳號。

**怎麼變現**：①自營 TikTok/Reels/Shorts 帳號衝流量，影片描述掛工具/主機商聯盟（非 VPN）②代製接案 ③模板/prompt 包販售。網頁端掛 Adsterra/Monetag，廣告只放網頁端。

**運作方式**：選題 agent 產腳本 → Sulphur-2 生影片片段 → supertonic 配旁白 → stable-audio-3 配樂 → Lens 生封面 → 自動剪接上字幕 → 排程發佈。lanshu kit 提供現成 prompt 庫加速。

**難度**：medium · **投入估計**：2–3 週做出能跑的 pipeline；難點在剪接串接與發佈自動化，模型都現成。

## 用到的開源零件

- [Sulphur-2（文字生成影片模型）](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-sulphurai-sulphur-2-base/) — 輸入文字提示，直接生成影片片段的擴散模型（pipeline: text-to-video）。
- [Supertonic-3（語音合成 TTS）](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-supertone-supertonic-3/) — 文字轉語音模型，附 ONNX 版本利於部署（pipeline: text-to-speech）。
- [Stable Audio 3 Medium（文字生成音樂/音效）](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-stabilityai-stable-audio-3-medium/) — Stability AI 的文字生成音訊模型（pipeline: text-to-audio）。
- [Microsoft Lens（文字生成圖像）](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-microsoft-lens/) — 微軟釋出的文生圖擴散模型，另有 Lens-Turbo 加速版（pipeline: text-to-image）。
- [藍書 AI 影片工具包](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/cclank-lanshu-awesome-ai-video-kit/) — 做企業 AI 影片專案累積出的實戰工具包：411 個 prompt、15 個模型、7 個 Claude Skill。
