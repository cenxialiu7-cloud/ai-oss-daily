# 🧩 本機隱私 AI 全家桶（Mac App 套裝：文件＋語音＋LLM＋交易）

一個品牌、多個離線 Mac App：文件智能、口播配音、本機 LLM 助手、交易研究，全程不上雲，資料零外流。

**🧩 Bundles**: [P006 隱私版・本機文件智能 App（Mac，發票/合約/名片秒抽欄位）](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/proposals/P006/)、[P011 本機口播配音棚（Mac App）：一段文字 → 你的克隆音色多語旁白](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/proposals/P011/)、[P012 離線小鋼炮工作台（Mac App）：本機跑 LLM／翻譯／寫程式助手，資料零外流](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/proposals/P012/)、[P003 本機隱私版・可視化交易研究台（Mac App）](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/proposals/P003/)

**Monetization**：①Setapp 式套裝訂閱 或 各 App 買斷（Gumroad/Lemon Squeezy MoR）②設定頁 Ko-fi ③聯盟帶 Mac 周邊/外接 SSD（非 VPN）。主打『付一次、永遠免月費、隱私不上雲』打雲端 AI 訂閱疲勞。

**How it works**：把 P006(文件)＋P011(口播)＋P012(LLM)＋P003(交易) 收進同一個『本機隱私 AI』品牌殼，共用模型下載器、Sparkle/notarize 發版 SOP 與授權邏輯，做成套裝訂閱（像 Setapp）或單買；統一的離線隱私定位＋一致 UI。

**Difficulty**：high · **Effort**：各模組多已有獨立案；本案重點是『共用殼＋套裝商業化』，逐個 App 上架。

## Open-source parts

- [PaddlePaddle/PaddleOCR-VL-1.6](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-paddlepaddle-paddleocr-vl-1-6/) — image-text-to-text · PaddleOCR, safetensors, paddleocr_vl
- [bosonai/higgs-audio-v3-tts-4b](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-bosonai-higgs-audio-v3-tts-4b/) — text-to-speech · transformers, safetensors, higgs_multimodal_qwen3
- [LiquidAI/LFM2.5-8B-A1B](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-liquidai-lfm2-5-8b-a1b/) — text-generation · transformers, safetensors, lfm2_moe
- [HKUDS/Vibe-Trading](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/hkuds-vibe-trading/) — "Vibe-Trading: Your Personal Trading Agent"
