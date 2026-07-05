# AI 投資委員會：13 位角色化 AI 分析師研究＋辯論＋風控 → 一份可下載的個股決策報告（非訊號推播）

輸入一檔股票，13 位角色化 AI 分析師分頭研究、互相辯論、跑風控壓力測試，產出一份附回測佐證與信心度的繁中買賣決策報告。

**Monetization**：①網頁端『免費基礎報告』（單檔精簡版）掛 Adsterra／Monetag 廣告引流；②付費深度報告（完整辯論記錄＋回測＋風控情境，Ko-fi 一次性解鎖）或 SaaS 月費（多檔追蹤、每日重算、PDF 匯出）；③行情數據商／看盤圖表工具／券商開戶工具聯盟分潤。全程附投資免責聲明，絕不碰任何 VPN 類聯盟。

**How it works**：gauss314/skills 當 AI agent 的行情與基本面資料消費層，抓進個股價量、財報與新聞 → helm-agents 啟動 13 位角色化 AI 分析師（基本面、技術面、籌碼、宏觀、空方等）分頭研究、辯論並跑風控壓力測試，收斂出買賣傾向與信心度 → tickflow-stock-panel 對該標的跑技術面選股訊號與歷史回測，提供量化佐證與勝率 → semble 高速檢索歷史報告與相似標的辯論記錄（比 grep+read 省約 98% token）→ 用 modelcontextprotocol/python-sdk 包成 MCP／CLI，網頁端輸出含辯論摘要、回測數據與免責聲明的繁中決策報告。與 P010 訊號台＋陪跑社群不同：本案是以多智能體辯論為核心的『單份決策報告產品』，非即時訊號推播或社群訂閱。

**Difficulty**：high · **Effort**：估 3–5 週做出能跑的 MVP：資料層接 gauss314 與多智能體編排各約一週；難點在 13 位 agent 的辯論成本與延遲控制、行情資料源穩定度、辯論結論與回測佐證的一致性校驗，以及投資免責與合規邊界設計。

## Open-source parts

- [QuantiaAI/helm-agents](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/quantiaai-helm-agents/) — 多智能体 LLM 股票/加密交易决策台 —— 13 位 AI 分析师研究、辩论、风控压测,收敛出可追溯、可实时观看的交易决策。 | Multi-agent LLM trading desk: 13 AI analyst…
- [shy3130/tickflow-stock-panel](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/shy3130-tickflow-stock-panel/) — 自托管、零运维的 A 股「选股 + 监控 + 回测」量化工作台 | 基于 TickFlow 数据源 | LLM能力驱使策略定制+个股分析+复盘 | 自由接入第三方个性化扩展数据 | 个人开源 ,非TickFlow官方项目
- [gauss314/skills](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/gauss314-skills/) — Financial market data consumption skills for claude code and AI agents
- [MinishLab/semble](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/minishlab-semble/) — Fast and Accurate Code Search for Agents. Uses ~98% fewer tokens than grep+read
- [modelcontextprotocol/python-sdk](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/modelcontextprotocol-python-sdk/) — The official Python SDK for Model Context Protocol servers and clients
