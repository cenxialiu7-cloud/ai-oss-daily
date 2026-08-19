# 🧩 企業 MCP 治理閘道：內部 MCP 註冊表＋供應鏈安全評分＋統一權限稽核，一次管住全公司 AI 工具接口 🧩超級組合

企業導入 Claude／Cursor／Codex 之後，員工各自亂裝 MCP server 就是新的影子 IT：這套自架閘道讓 IT 先掃描評分、再上架到內部註冊表，所有 AI 工具呼叫都經過同一道有紀錄、可撤銷的關卡。

**🧩 組合自**：[P041 自架 AI 連接器與自動化閘道（Mac App／自架）：把 SaaS 一次接上任何 AI agent，省掉按人頭連接器月費](https://cenxialiu7-cloud.github.io/ai-oss-daily/proposals/P041/)、[P045 團隊共用程式碼記憶 MCP（自架）：一次索引全公司程式碼，讓 Claude／Cursor／Codex 每個 AI 工具都精準檢索、程式碼零外流](https://cenxialiu7-cloud.github.io/ai-oss-daily/proposals/P045/)、[P046 MCP 伺服器信任稽核平台：安裝前先掃描，給每個 MCP server 一個供應鏈安全評分](https://cenxialiu7-cloud.github.io/ai-oss-daily/proposals/P046/)

**怎麼變現**：①企業自架年度授權（依員工席次或接入的 MCP server 數計價）：賣的是治理與可稽核性，不是功能；②導入顧問費：協助盤點現有 MCP、建立內部註冊表與權限政策，一次性收費；③持續訂閱：安全評分規則庫更新、新 MCP server 上架前的自動複掃、每季稽核報告；④小團隊 Mac App 買斷版：單機閘道＋本機評分，給沒有 IT 部門的工作室；⑤公開的免費『MCP server 安全評分查詢』網頁版掛 Adsterra／Monetag 衝自然流量並放 Ko-fi，同時當作企業版的導流入口；⑥主機商與資安工具聯盟。不涉及任何 VPN 類聯盟。

**運作方式**：分成三層。安全層：illiahaidar/mcptrustchecker 對每個候選 MCP server 做供應鏈掃描（可疑指令、外連目的地、權限索取範圍、維護者活躍度），產出一個可解釋的信任分數；modelcontextprotocol/servers 作為官方參考基準庫，用來比對『這個 server 是不是官方版本的變體』並建立白名單基線。閘道層：用 modelcontextprotocol/python-sdk 自建一個代理型 MCP server，員工的 Claude／Cursor／Codex 只連這一個端點，由它依角色分派可用的下游 server 與工具，並記錄每一次工具呼叫（誰、何時、呼叫哪個工具、參數摘要、回傳大小），成為稽核軌跡與撤銷開關。編排層：Rath-Team/OpenRath 的多代理／多會話執行時負責把跨 server 的工作流串起來並隔離會話，避免某個 server 的回應污染其他任務的上下文；DeusData/codebase-memory-mcp 則作為閘道後面第一個示範性的高價值內部 server（全公司程式碼索引），示範『內部資產只經閘道存取、程式碼零外流』的標準做法。定位差異：P046 只做安裝前的單點掃描評分，P045 只做程式碼記憶這一個 server，P041 做的是接上更多 SaaS 的連接器閘道；本案把三者疊成企業 IT 真正要買的東西——一個有註冊表、有評分、有權限、有紀錄、能撤銷的中央管制點。

**難度**：high · **投入估計**：估 6–8 週做出能跑版本：代理型 MCP 閘道（協定轉發、工具過濾、呼叫紀錄）約 2–3 週，mcptrustchecker 整合與評分規則庫、白名單基線約 1.5 週，角色權限與內部註冊表 UI 約 1.5 週，OpenRath 會話隔離與跨 server 編排約 1 週，稽核報告輸出約 0.5 週。難點：一是協定相容性——MCP 規格與各家客戶端行為仍在變動，代理層要容忍版本差異且不能明顯增加延遲；二是評分要能服人，純靜態掃描容易誤判，需要人工複核流程與申訴機制，否則 IT 不敢用來擋人；三是這類產品的買家是資安／IT 部門，銷售週期長，需要先用免費評分查詢頁累積名聲再進企業。

## 用到的開源零件

- [illiahaidar/mcptrustchecker](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/illiahaidar-mcptrustchecker/) — 用於掃描 MCP 伺服器的安全工具，檢查潛在風險。
- [modelcontextprotocol/servers](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/modelcontextprotocol-servers/) — 提供模型上下文協議的伺服器。
- [modelcontextprotocol/python-sdk](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/modelcontextprotocol-python-sdk/) — 官方 Python SDK，用於 Model Context Protocol 伺服器和客戶端。
- [DeusData/codebase-memory-mcp](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/deusdata-codebase-memory-mcp/) — 高效能程式碼智慧伺服器，快速索引多種語言的程式碼庫。
- [Rath-Team/OpenRath](https://cenxialiu7-cloud.github.io/ai-oss-daily/p/rath-team-openrath/) — 開源、類似PyTorch的工作流程執行時環境，適用於多代理和多會話。
