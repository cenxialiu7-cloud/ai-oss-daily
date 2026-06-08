# 離線小鋼炮工作台（Mac App）：本機跑 LLM／翻譯／寫程式助手，資料零外流

一個 App 內建選好的端側模型，點一下就能在 Mac 上做摘要、翻譯、寫程式片段，不連網、不訂閱、不被計 token。

**Monetization**：①買斷制 Mac App（Gumroad/Lemon Squeezy MoR）：Free 內建 1 顆小模型＋基本聊天，Pro 解鎖模型切換/批次/自訂 Prompt 範本與情境包 ②設定頁 Ko-fi。賣點『付一次、永遠免月費、隱私不上雲』打雲端 LLM 訂閱疲勞 ③聯盟帶 Mac 周邊/外接 SSD（裝模型）等工具類（不推 VPN）。網頁端 Adsterra/Monetag。

**How it works**：啟動偵測 Mac 記憶體/晶片 → 推薦對應檔位（低階→MiniCPM5-1B、一般→LFM2.5 MoE）→ 選情境：通用聊天走 LFM2.5、寫程式切 Mellum2-Thinking、翻譯切 Hy-MT2-1.8B → 全部 GGUF/MoE 在本機推理，對話與檔案不出機。Pro 增加整個資料夾批次摘要/翻譯與情境 Prompt 庫。

**Difficulty**：medium · **Effort**：3–5 週（模型下載/量化管理＋推理後端整合＋SwiftUI；沿用 OSS Radar 已踩過的 Ollama/GGUF on M 系列經驗）。

## Open-source parts

- [openbmb/MiniCPM5-1B](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-openbmb-minicpm5-1b/) — text-generation · transformers, safetensors, llama
- [LiquidAI/LFM2.5-8B-A1B](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-liquidai-lfm2-5-8b-a1b/) — text-generation · transformers, safetensors, lfm2_moe
- [JetBrains/Mellum2-12B-A2.5B-Thinking](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-jetbrains-mellum2-12b-a2-5b-thinking/) — text-generation · transformers, safetensors, mellum
- [tencent/Hy-MT2-1.8B](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-tencent-hy-mt2-1-8b/) — translation · transformers, safetensors, hunyuan_v1_dense
