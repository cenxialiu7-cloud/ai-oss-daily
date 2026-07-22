# GEO 稽核機器人即服務（每月幫品牌站體檢「能不能被 AI 引用」）

用一套 agent skill 每月自動稽核客戶網站在 Google AI Overviews／Perplexity／ChatGPT 的可被引用性，產出可執行修復清單，做成訂閱型代操服務。

**Monetization**：①月費訂閱（基礎版自助報告／進階版我代操修復）②Gumroad/Lemon Squeezy MoR 賣『一次性站體檢報告』買斷做漏斗入口 ③報告頁內嵌工具聯盟（DataForSEO/排名工具等，非 VPN）④OSS Radar 公開站 footer/報告頁掛 Adsterra/Monetag＋Ko-fi。沿用既有 publish + Telegram/Email 發佈管線把『本月 AI 搜尋演算法變動』當電子報引流。

**How it works**：客戶填網址 → codex-seo 工作流抓站＋串 DataForSEO 拿排名/AI 引用現況 → google-ai-search-optimization 與 superseo-skills 逐頁打分（標題結構/Schema/entity/可被 LLM 解析度）→ 以 specification.website 為客觀 rubric 計『AI 可引用分數』→ 產出帶優先級修復清單（Claude Code 本機跑，零 LLM API 費）→ 報告用 oss-radar 既有 Jinja2 模板輸出，每月自動重跑追蹤分數變化。

**Difficulty**：medium · **Effort**：2–3 週做出可賣 MVP（skill 串接＋報告模板＋Gumroad 上架）；代操服務同步開賣。

## Open-source parts

- [deepakness/google-ai-search-optimization](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/deepakness-google-ai-search-optimization/) — Unofficial Agent Skill based on Google Search guidance for AI Overviews, AI Mode, and SEO audits.
- [inhouseseo/superseo-skills](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/inhouseseo-superseo-skills/) — 11 Claude skills for SEO: page audits, linkbuilding, article writing, E-E-A-T audits, semantic gap analysis, …
- [jdevalk/specification.website](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/jdevalk-specification-website/) — Website specification — HTML, accessibility, security, SEO, agent-readiness. Platform-agnostic, sourced, MIT.
- [AgriciDaniel/codex-seo](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/agricidaniel-codex-seo/) — Codex-first SEO skill suite. 26 workflows, 24 TOML agents, DataForSEO/Gemini/Google/Firecrawl integrations, G…
- [nowork-studio/NotFair](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/nowork-studio-notfair/) — Goal-driven, loop-powered marketing agents that crush your business goals 24/7
