# RadarMind MCP（給 AI agent 訂閱的每日 AI 開源情報 MCP）

把 OSS Radar 知識庫接上省 token 的程式碼搜尋與上下文壓縮，做成 AI agent 直接訂閱的 MCP server——使用者的 Claude/Cursor 一句話就查到去噪過、已判商用授權的最新樂高積木。

**Monetization**：①MCP server 分級訂閱（免費層查當日榜，付費層解鎖 suggest_combinations 深度提案＋歷史 diff＋商用授權判讀；走 Gumroad/Lemon Squeezy MoR 訂閱）②對外雙語內容站續接 Adsterra/Monetag＋Ko-fi ③可選聯盟（開發工具/主機商，非 VPN）。

**How it works**：OSS Radar 既有 SQLite 知識庫（含繁中、商用授權、TrueHeat 排序、語意去重、組合提案）→ llm-wiki 把每日榜編譯成結構化知識頁 → semble 提供省 token 庫內檢索 → lean-ctx 把回應壓縮成 agent 友善上下文 → 全部用 python-sdk 暴露為 MCP 工具（query_oss / suggest_combinations / check_commercial_use 分免費與付費層）。使用者 Claude/Cursor 直接連線消費，付費牆控制深度。

**Difficulty**：medium · **Effort**：2 週（OSS Radar MCP server 與知識庫已存在且握手測過，主要新工作是接 semble/lean-ctx 做省 token 層、加分級授權與訂閱閘門）。

## Open-source parts

- [MinishLab/semble](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/minishlab-semble/) — Fast and Accurate Code Search for Agents. Uses ~98% fewer tokens than grep+read
- [yvgude/lean-ctx](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/yvgude-lean-ctx/) — LeanCTX (Lean Context) — context intelligence for AI agents. One local binary that decides what your agents r…
- [nvk/llm-wiki](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/nvk-llm-wiki/) — LLM-compiled knowledge bases for any AI agent. Parallel multi-agent research, thesis-driven investigation, so…
- [modelcontextprotocol/python-sdk](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/modelcontextprotocol-python-sdk/) — The official Python SDK for Model Context Protocol servers and clients
