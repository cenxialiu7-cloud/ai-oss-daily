# 本機口播配音棚（Mac App）：一段文字 → 你的克隆音色多語旁白

拖入講稿，全程離線用 GPU 跑出帶情緒、可多語的語音檔，做 YouTube/Podcast/教學旁白不上雲、不按秒計費。

**怎麼變現**：①Mac App 買斷（Gumroad/Lemon Squeezy MoR，台幣直入）：Free 單語＋提示浮水印，Pro 一次性解鎖多語/批次/字幕對齊匯出 SRT ②設定頁放 Ko-fi 贊助。主打『一次付清、無限生成、音檔不外流』打雲端 TTS per-character 計費 ③聯盟可帶麥克風/錄音介面/Podcast 主機商（不推 VPN）。網頁端落地頁掛 Adsterra/Monetag。

**運作方式**：貼上/拖入講稿 → 選音色與語言 → higgs-audio v3 為主引擎合成（中文場景切 MOSS-TTS）→ 低階 Mac 自動降級到 Supertonic-3 的 ONNX 版避免卡死 → 合成完用 nemotron ASR 對齊文字時間軸輸出帶時間碼 SRT/逐句檔。全程本機 Metal/GPU 跑，零 API。

**難度**：medium · **投入估計**：3–4 週（SwiftUI 殼＋模型權重下載器＋Sparkle/notarize 走既有發版 SOP）。

## 用到的開源零件

- [bosonai/higgs-audio-v3-tts-4b](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-bosonai-higgs-audio-v3-tts-4b/) — 將文本轉換為語音的合成器。
- [MOSS-TTS v1.5（開源語音合成）](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-openmoss-team-moss-tts-v1-5/) — 復旦 MOSS 團隊的開源 TTS 模型（pipeline: text-to-speech）。
- [Supertonic-3（語音合成 TTS）](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-supertone-supertonic-3/) — 文字轉語音模型，附 ONNX 版本利於部署（pipeline: text-to-speech）。
- [nvidia/nemotron-3.5-asr-streaming-0.6b](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-nvidia-nemotron-3-5-asr-streaming-0-6b/) — 即時語音識別系統，支援多語言。
