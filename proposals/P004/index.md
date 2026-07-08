# Podcast/會議 → 帶人名逐字稿 + 多語配音 SaaS

上傳音檔，自動產出標好發言人的逐字稿、多語翻譯與重新配音、社群封面。

**怎麼變現**：①SaaS 訂閱(按時數) ②單次付費 ③免費額度導流。網頁端可放 Adsterra，下載/工具站避開 AdSense。

**運作方式**：pyannote 分離說話者 + (Whisper)轉錄 → Qwen3.6 摘要/翻譯 → supertonic 產多語配音 → Lens 生封面 → 打包成可分享成品。

**難度**：medium · **投入估計**：3–4 週；多為成熟零件串接，主要工在上傳/計費/前端。

## 用到的開源零件

- [pyannote 語者分離 3.1](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-pyannote-speaker-diarization-3-1/) — 業界最常用的開源「誰在何時說話」語者分離工具（近千萬下載）。
- [Supertonic-3（語音合成 TTS）](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-supertone-supertonic-3/) — 文字轉語音模型，附 ONNX 版本利於部署（pipeline: text-to-speech）。
- [Microsoft Lens（文字生成圖像）](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-microsoft-lens/) — 微軟釋出的文生圖擴散模型，另有 Lens-Turbo 加速版（pipeline: text-to-image）。
