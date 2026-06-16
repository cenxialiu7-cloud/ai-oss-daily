# 🧩 開發者 AI 生產力套件（理解＋省錢＋情報＋資安）

給工程團隊的一站式 AI 套件：秒懂任何 codebase、砍 agent token 帳單、訂閱最新開源情報、即時資安稽核。

**🧩 組合自**：[P018 程式碼知識圖譜即服務：丟一個 repo → 可互動探索的架構地圖，加速 onboarding/code review](https://cenxialiu7-cloud.github.io/ai-oss-daily/proposals/P018/)、[P021 Agentic 開發成本殺手：給用 Claude Code/Cursor 的團隊砍 token 帳單的技能包＋本機外掛](https://cenxialiu7-cloud.github.io/ai-oss-daily/proposals/P021/)、[P013 RadarMind MCP（給 AI agent 訂閱的每日 AI 開源情報 MCP）](https://cenxialiu7-cloud.github.io/ai-oss-daily/proposals/P013/)、[P017 資安情報 MCP ＋ 桌面哨兵（綜效 MacSentinel）：給 Claude/Cursor 的即時 CVE/紅隊軍火庫](https://cenxialiu7-cloud.github.io/ai-oss-daily/proposals/P017/)

**怎麼變現**：①團隊席次訂閱（多模組綁定）②各模組可拆售（codebase 體檢報告/省 token 技能包/情報 MCP/資安 MCP，MoR）③省成本/資安導入顧問 ④工具聯盟（IDE/雲端額度，非 VPN）＋Ko-fi。

**運作方式**：把 P018(理解 codebase)＋P021(省 token)＋P013(情報 MCP)＋P017(資安 MCP) 綁成給工程團隊的套件：新人用知識圖譜秒懂專案 → ponytail/semble 砍開發 token 成本 → RadarMind 訂閱最新可商用開源積木 → cve-mcp 即時資安稽核。全部走 MCP 一次連線。

**難度**：high · **投入估計**：綁定四案的 MCP/技能；先做 P021(省錢，最硬訴求)＋P018，再疊情報/資安。

## 用到的開源零件

- [Egonex-AI/Understand-Anything](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/egonex-ai-understand-anything/) — 將程式碼轉換為可互動探索和查詢的知識圖形工具。
- [DietrichGebert/ponytail](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/dietrichgebert-ponytail/) — 讓AI代理程式以懶惰開發者的思維方式運作，減少程式碼編寫。
- [MinishLab/semble](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/minishlab-semble/) — 快速且精確的程式碼搜尋工具，比 grep+read 少用約 98% 的 token。
- [mukul975/cve-mcp-server](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/mukul975-cve-mcp-server/) — 為Claude提供21個API的安全情報工具集，涵蓋多種安全標準和資料來源。
- [modelcontextprotocol/python-sdk](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/modelcontextprotocol-python-sdk/) — 官方 Python SDK，用於 Model Context Protocol 伺服器和客戶端。
