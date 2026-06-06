# AI 量化訊號台 ＋ 陪跑社群（把今日爆紅的 agentic 交易棧變訂閱服務）

用開源 agentic 量化棧每天跑出選股/進出場訊號＋多 agent 辯論解讀，做成付費電子報與 Telegram 訊號社群。

**怎麼變現**：①付費訂閱（月費電子報＋私有 Telegram 訊號群）②交易所/券商聯盟（OKX 等已有 agent 串接，加盟金優渥）③免費版網頁掛 Adsterra/Monetag、設定頁放 Ko-fi ④回測/因子深度報告單買。與你既有 TradingSystem 的資料/回測、以及 OSS Radar 已建好的 Telegram/電子報(AWeber)發佈基建直接共用，邊際成本低。

**運作方式**：每日 Alpha Forge / Vibe-Trading 的 agent 跑 universe → zer0factor 產因子與訊號 → TradingAgents-Studio 多 agent 辯論輸出『為何買賣』白話解讀 → LLMQuant skills 標準化排版 → 沿用 OSS Radar 既有管線自動推 Telegram 訊號群＋AWeber 電子報。免費版導流、付費版給完整持倉與即時訊號；OKX kit 提供下單串接與交易所聯盟導流。

**難度**：medium · **投入估計**：2–3 週起步；資料/回測可直接接你既有 TradingSystem，發佈/電子報/Telegram 基建已現成(P009)，主要工在訊號品質與合規免責。

## 用到的開源零件

- [Vibe-Trading（個人交易 Agent）](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/hkuds-vibe-trading/) — 港大資料科學實驗室(HKUDS)開源的「個人交易代理人」，全站投資理財最熱（9,027★）。
- [Alpha Forge（系統化交易 AI 作業系統）](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/liu-ming-yu-alpha-forge/) — 標榜 agentic 的系統化交易作業系統。
- [TradingAgents Studio（可視化多智能體交易研究）](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/wjhccc-tradingagents-studio/) — 可視化的多 agent LLM 交易研究平台 —— 看得到 agent 怎麼想、怎麼辯論、怎麼決策。
- [LLMQuant/skills](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/llmquant-skills/) — LLMQuant 的可重用量化 agent skills（Claude/Cursor/OpenClaw 通用）。
- [zer0quant/zer0factor](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/zer0quant-zer0factor/) — 面向 A 股本地資料的 AI 因子研究工作臺，用於生成、儲存、註冊、評估與報告因子。
- [OKX Agent 交易套件](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/placenl2026-okx-agent-trade-kit/) — 用 MCP/CLI 串接 OKX 現貨/合約的 AI agent 交易工具包。
