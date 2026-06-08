# 本機口播配音棚（Mac App）：一段文字 → 你的克隆音色多語旁白

拖入講稿，全程離線用 GPU 跑出帶情緒、可多語的語音檔，做 YouTube/Podcast/教學旁白不上雲、不按秒計費。

**Monetization**：①Mac App 買斷（Gumroad/Lemon Squeezy MoR，台幣直入）：Free 單語＋提示浮水印，Pro 一次性解鎖多語/批次/字幕對齊匯出 SRT ②設定頁放 Ko-fi 贊助。主打『一次付清、無限生成、音檔不外流』打雲端 TTS per-character 計費 ③聯盟可帶麥克風/錄音介面/Podcast 主機商（不推 VPN）。網頁端落地頁掛 Adsterra/Monetag。

**How it works**：貼上/拖入講稿 → 選音色與語言 → higgs-audio v3 為主引擎合成（中文場景切 MOSS-TTS）→ 低階 Mac 自動降級到 Supertonic-3 的 ONNX 版避免卡死 → 合成完用 nemotron ASR 對齊文字時間軸輸出帶時間碼 SRT/逐句檔。全程本機 Metal/GPU 跑，零 API。

**Difficulty**：medium · **Effort**：3–4 週（SwiftUI 殼＋模型權重下載器＋Sparkle/notarize 走既有發版 SOP）。

## Open-source parts

- [bosonai/higgs-audio-v3-tts-4b](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-bosonai-higgs-audio-v3-tts-4b/) — text-to-speech · transformers, safetensors, higgs_multimodal_qwen3
- [OpenMOSS-Team/MOSS-TTS-v1.5](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-openmoss-team-moss-tts-v1-5/) — text-to-speech · safetensors, moss_tts_delay, text-to-speech
- [Supertone/supertonic-3](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-supertone-supertonic-3/) — text-to-speech · supertonic, onnx, text-to-speech
- [nvidia/nemotron-3.5-asr-streaming-0.6b](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-nvidia-nemotron-3-5-asr-streaming-0-6b/) — automatic-speech-recognition · nemo, speech-recognition, cache-aware ASR
