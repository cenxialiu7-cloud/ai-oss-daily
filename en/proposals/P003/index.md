# 本機隱私版・可視化交易研究台（Mac App）

全程在本機跑的多 agent 交易研究工具，看得到 AI 怎麼辯論決策，資料不出門。

**Monetization**：①Mac App 一次性買斷/訂閱 ②設定頁放 Ko-fi 贊助。屬『安全/隱私工具』類，絕不嵌第三方追蹤(自打嘴巴)，正合你的隱私慣例。

**How it works**：Qwen3.6 GGUF 用 llama.cpp 本機推理 → Vibe-Trading 當 agent 大腦 → TradingAgents-Studio 把多 agent 辯論視覺化 → cutebacktests 驗證策略。全本機、無 API 金鑰外流。

**Difficulty**：high · **Effort**：4–6 週(含 Mac App 殼)；可直接複用你 TradingSystem 的資料與經驗。

## Open-source parts

- [HKUDS/Vibe-Trading](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/hkuds-vibe-trading/) — "Vibe-Trading: Your Personal Trading Agent"
- [wjhccc/TradingAgents-Studio](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/wjhccc-tradingagents-studio/) — 可视化多智能体 LLM 交易研究平台 — 看见 Agent 怎么想、怎么辩、怎么拍板,而不只是最后那个 BUY/SELL。
- [cutemarkets/cutebacktests](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/cutemarkets-cutebacktests/) — Backtesting framework for modern option strategies
- [unsloth/Qwen3.6-27B-MTP-GGUF](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/model-unsloth-qwen3-6-27b-mtp-gguf/) — image-text-to-text · transformers, gguf, unsloth
