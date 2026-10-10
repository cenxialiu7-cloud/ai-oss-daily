# AI 可疑執行檔初篩室：外包交付／下載軟體上線前，沙盒內逆向分析並出具白話風險報告

丟進一個 .exe／.app／安裝包，AI 在隔離環境自動逆向、動態除錯，30 分鐘內交出『能不能裝、哪裡可疑』的白話報告。

**Monetization**：①按份計價的報告服務：中小企業／工作室／外包驗收方，每份可疑檔案初篩收費，高風險再升級人工複核；②顧問訂閱：資安顧問與接案工程師月費使用工作台，報告可掛自己品牌交付客戶；③Mac／Windows 桌面版買斷（本機分析、檔案不上傳）。廣告只放網頁端的檢測教學內容站（Adsterra/Monetag），搭配 Ko-fi 與沙盒／主機商聯盟。

**How it works**：1) 使用者上傳檔案，系統丟進一次性 Docker／VM 沙盒（decionis/docker 提供動作政策與人為批准閘門，危險動作如連外、寫系統需點頭）；2) rea 做靜態到原生碼的行為拆解，x64dbg-mcp-server 在 Windows 沙盒內讓 AI 下斷點、追呼叫、看載入的 API；3) 以 MCP python-sdk 把兩者包成統一工具集，由 LLM 代理依序執行並彙整證據；4) 輸出固定格式報告：行為摘要、可疑指標、網路／持久化跡象、建議（可裝／隔離／拒收）與證據截圖。定位為防禦性初篩，不提供改寫或攻擊功能。

**Difficulty**：high · **Effort**：約 4–6 週做出單檔可跑版本；難點在沙盒隔離的安全性、Windows 除錯環境自動化、避免誤判造成的責任，須在報告加免責與人工複核升級路徑。

## Open-source parts

- [morluto/rea](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/morluto-rea/) — Reverse engineer anything with agents, from app behavior down to native binaries.
- [duty1g/x64dbg-mcp-server](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/duty1g-x64dbg-mcp-server/) — x64dbg-MCP Server is a native MCP (Model Context Protocol) plugin for x64dbg that exposes the debugger's full…
- [decionis/docker](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/decionis-docker/) — Govern consequential AI agent actions in Docker with deterministic policy, human approval, and signed Decisio…
- [modelcontextprotocol/python-sdk](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/modelcontextprotocol-python-sdk/) — The official Python SDK for Model Context Protocol servers and clients
