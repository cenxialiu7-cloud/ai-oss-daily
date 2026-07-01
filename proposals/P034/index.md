# AI 投資委員會：13 位角色化 AI 分析師研究＋辯論＋風控 → 一份可下載的個股決策報告（非訊號推播）

輸入一檔股票，13 位角色化 AI 分析師分頭研究、互相辯論、跑風控壓力測試，產出一份附回測佐證與信心度的繁中買賣決策報告。

**怎麼變現**：①網頁端『免費基礎報告』（單檔精簡版）掛 Adsterra／Monetag 廣告引流；②付費深度報告（完整辯論記錄＋回測＋風控情境，Ko-fi 一次性解鎖）或 SaaS 月費（多檔追蹤、每日重算、PDF 匯出）；③行情數據商／看盤圖表工具／券商開戶工具聯盟分潤。全程附投資免責聲明，絕不碰任何 VPN 類聯盟。

**運作方式**：gauss314/skills 當 AI agent 的行情與基本面資料消費層，抓進個股價量、財報與新聞 → helm-agents 啟動 13 位角色化 AI 分析師（基本面、技術面、籌碼、宏觀、空方等）分頭研究、辯論並跑風控壓力測試，收斂出買賣傾向與信心度 → tickflow-stock-panel 對該標的跑技術面選股訊號與歷史回測，提供量化佐證與勝率 → semble 高速檢索歷史報告與相似標的辯論記錄（比 grep+read 省約 98% token）→ 用 modelcontextprotocol/python-sdk 包成 MCP／CLI，網頁端輸出含辯論摘要、回測數據與免責聲明的繁中決策報告。與 P010 訊號台＋陪跑社群不同：本案是以多智能體辯論為核心的『單份決策報告產品』，非即時訊號推播或社群訂閱。

**難度**：high · **投入估計**：估 3–5 週做出能跑的 MVP：資料層接 gauss314 與多智能體編排各約一週；難點在 13 位 agent 的辯論成本與延遲控制、行情資料源穩定度、辯論結論與回測佐證的一致性校驗，以及投資免責與合規邊界設計。

## 用到的開源零件

- [QuantiaAI/helm-agents](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/quantiaai-helm-agents/) — 多智慧體LLM股票/加密交易決策平臺，13位AI分析師研究、辯論和風控測試。
- [shy3130/tickflow-stock-panel](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/shy3130-tickflow-stock-panel/) — 基於 TickFlow 的 A 股量化工作臺，提供選股、監控及回測功能。
- [gauss314/skills](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/gauss314-skills/) — 提供給Claude程式碼和AI代理使用的金融市場資料消費技能。
- [MinishLab/semble](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/minishlab-semble/) — 快速且精確的程式碼搜尋工具，比 grep+read 少用約 98% 的 token。
- [modelcontextprotocol/python-sdk](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/modelcontextprotocol-python-sdk/) — 官方 Python SDK，用於 Model Context Protocol 伺服器和客戶端。
