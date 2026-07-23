# Podcast/會議 → 帶人名逐字稿 + 多語配音 SaaS

上傳音檔，自動產出標好發言人的逐字稿、多語翻譯與重新配音、社群封面。

**Monetization**：①SaaS 訂閱(按時數) ②單次付費 ③免費額度導流。網頁端可放 Adsterra，下載/工具站避開 AdSense。

**How it works**：pyannote 分離說話者 + (Whisper)轉錄 → Qwen3.6 摘要/翻譯 → supertonic 產多語配音 → Lens 生封面 → 打包成可分享成品。

**Difficulty**：medium · **Effort**：3–4 週；多為成熟零件串接，主要工在上傳/計費/前端。

## Open-source parts

- [pyannote/speaker-diarization-3.1](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-pyannote-speaker-diarization-3-1/) — automatic-speech-recognition · pyannote-audio, pyannote, pyannote-audio-pipeline
- [Supertone/supertonic-3](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-supertone-supertonic-3/) — text-to-speech · supertonic, onnx, text-to-speech
