# GEO 稽核機器人即服務（每月幫品牌站體檢「能不能被 AI 引用」）

用一套 agent skill 每月自動稽核客戶網站在 Google AI Overviews／Perplexity／ChatGPT 的可被引用性，產出可執行修復清單，做成訂閱型代操服務。

**怎麼變現**：①月費訂閱（基礎版自助報告／進階版我代操修復）②Gumroad/Lemon Squeezy MoR 賣『一次性站體檢報告』買斷做漏斗入口 ③報告頁內嵌工具聯盟（DataForSEO/排名工具等，非 VPN）④OSS Radar 公開站 footer/報告頁掛 Adsterra/Monetag＋Ko-fi。沿用既有 publish + Telegram/Email 發佈管線把『本月 AI 搜尋演算法變動』當電子報引流。

**運作方式**：客戶填網址 → codex-seo 工作流抓站＋串 DataForSEO 拿排名/AI 引用現況 → google-ai-search-optimization 與 superseo-skills 逐頁打分（標題結構/Schema/entity/可被 LLM 解析度）→ 以 specification.website 為客觀 rubric 計『AI 可引用分數』→ 產出帶優先級修復清單（Claude Code 本機跑，零 LLM API 費）→ 報告用 oss-radar 既有 Jinja2 模板輸出，每月自動重跑追蹤分數變化。

**難度**：medium · **投入估計**：2–3 週做出可賣 MVP（skill 串接＋報告模板＋Gumroad 上架）；代操服務同步開賣。

## 用到的開源零件

- [deepakness/google-ai-search-optimization](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/deepakness-google-ai-search-optimization/) — 依 Google 指引做 AI Overviews／AI Mode／SEO 稽核的 agent skill。
- [superseo-skills（11 個 SEO 技能）](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/inhouseseo-superseo-skills/) — 11 個給 Claude 用的 SEO 技能：頁面稽核、外鏈建立、文章撰寫。
- [jdevalk/specification.website](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/jdevalk-specification-website/) — 網站規格標準：HTML、無障礙、安全、SEO、agent 可讀性（Yoast 創辦人作品）。
- [codex-seo（Codex 優先 SEO 套件）](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/agricidaniel-codex-seo/) — Codex 優先的 SEO 技能套件：26 個工作流、24 個 TOML agent，串接 DataForSEO/Gemini/Google。
