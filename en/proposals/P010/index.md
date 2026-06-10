# AI 量化訊號台 ＋ 陪跑社群（把今日爆紅的 agentic 交易棧變訂閱服務）

用開源 agentic 量化棧每天跑出選股/進出場訊號＋多 agent 辯論解讀，做成付費電子報與 Telegram 訊號社群。

**Monetization**：①付費訂閱（月費電子報＋私有 Telegram 訊號群）②交易所/券商聯盟（OKX 等已有 agent 串接，加盟金優渥）③免費版網頁掛 Adsterra/Monetag、設定頁放 Ko-fi ④回測/因子深度報告單買。與你既有 TradingSystem 的資料/回測、以及 OSS Radar 已建好的 Telegram/電子報(AWeber)發佈基建直接共用，邊際成本低。

**How it works**：每日 Alpha Forge / Vibe-Trading 的 agent 跑 universe → zer0factor 產因子與訊號 → TradingAgents-Studio 多 agent 辯論輸出『為何買賣』白話解讀 → LLMQuant skills 標準化排版 → 沿用 OSS Radar 既有管線自動推 Telegram 訊號群＋AWeber 電子報。免費版導流、付費版給完整持倉與即時訊號；OKX kit 提供下單串接與交易所聯盟導流。

**Difficulty**：medium · **Effort**：2–3 週起步；資料/回測可直接接你既有 TradingSystem，發佈/電子報/Telegram 基建已現成(P009)，主要工在訊號品質與合規免責。

## Open-source parts

- [HKUDS/Vibe-Trading](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/hkuds-vibe-trading/) — "Vibe-Trading: Your Personal Trading Agent"
- [Liu-Ming-Yu/alpha-forge](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/liu-ming-yu-alpha-forge/) — Alpha Forge — an agentic AI operating system for systematic trading.
- [wjhccc/TradingAgents-Studio](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/wjhccc-tradingagents-studio/) — 可视化多智能体 LLM 交易研究平台 — 看见 Agent 怎么想、怎么辩、怎么拍板,而不只是最后那个 BUY/SELL。
- [LLMQuant/skills](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/llmquant-skills/) — Reusable Skills for LLMQuant Agent, Claude Code, Claude.ai, Cursor, Hermes Agent, OpenClaw and Codex, grounde…
- [zer0quant/zer0factor](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/zer0quant-zer0factor/) — 面向 A 股本地数据的 AI 因子研究工作台：因子生成、存储、注册、评估与报告。
- [PlaceNL2026/okx-agent-trade-kit](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/placenl2026-okx-agent-trade-kit/) — OKX trading MCP CLI cryptocurrency spot futures swap AI agent Model Context Protocol Cursor Claude npm automa…
