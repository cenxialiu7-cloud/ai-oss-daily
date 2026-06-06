# 本機隱私版・可視化交易研究台（Mac App）

全程在本機跑的多 agent 交易研究工具，看得到 AI 怎麼辯論決策，資料不出門。

**怎麼變現**：①Mac App 一次性買斷/訂閱 ②設定頁放 Ko-fi 贊助。屬『安全/隱私工具』類，絕不嵌第三方追蹤(自打嘴巴)，正合你的隱私慣例。

**運作方式**：Qwen3.6 GGUF 用 llama.cpp 本機推理 → Vibe-Trading 當 agent 大腦 → TradingAgents-Studio 把多 agent 辯論視覺化 → cutebacktests 驗證策略。全本機、無 API 金鑰外流。

**難度**：high · **投入估計**：4–6 週(含 Mac App 殼)；可直接複用你 TradingSystem 的資料與經驗。

## 用到的開源零件

- [Vibe-Trading（個人交易 Agent）](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/hkuds-vibe-trading/) — 港大資料科學實驗室(HKUDS)開源的「個人交易代理人」，全站投資理財最熱（9,027★）。
- [TradingAgents Studio（可視化多智能體交易研究）](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/wjhccc-tradingagents-studio/) — 可視化的多 agent LLM 交易研究平台 —— 看得到 agent 怎麼想、怎麼辯論、怎麼決策。
- [cutebacktests（選擇權回測框架）](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/cutemarkets-cutebacktests/) — 針對現代選擇權策略的回測框架。
- [Unsloth 版 Qwen3.6-27B（GGUF 量化）](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/model-unsloth-qwen3-6-27b-mtp-gguf/) — 由 Unsloth 釋出的 Qwen3.6-27B GGUF 量化權重，下載近 88 萬。
