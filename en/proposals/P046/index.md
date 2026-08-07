# MCP 伺服器信任稽核平台：安裝前先掃描，給每個 MCP server 一個供應鏈安全評分

MCP 生態爆量，但裝一個來路不明的 server 等於把權限與資料交出去；本平台自動掃描並替每個 MCP server 打信任分數、列出紅旗，讓團隊安裝前先驗過。

**Monetization**：①免費『MCP 信任評分目錄』網站（掃描 modelcontextprotocol/servers 收錄的 server，公開風險分數與紅旗清單）衝自然流量，網頁端掛 Adsterra／Monetag 廣告；②團隊／企業版私有稽核 SaaS 月費：接上團隊實際連上的 MCP／SaaS 端點，持續監控供應鏈風險並產出稽核報告，依席次或受監控端點數計費；③本機 CLI／掃描器免費，進階規則庫與離線報告走 Ko-fi 贊助或包成 Mac App 買斷給獨立開發者。廣告只放網頁端，絕不碰任何 VPN 類聯盟。

**How it works**：排程持續抓 modelcontextprotocol/servers 官方收錄清單當掃描對象 → 對每個 server 用 mcptrustchecker 做靜態與行為掃描（過度權限、危險工具、可疑網路呼叫、憑證外洩、可疑相依），算出信任分數與紅旗清單 → 透過 modelcontextprotocol/python-sdk 把掃描器本身包成一個標準 MCP server，讓 Claude／Cursor 在安裝任何工具前先呼叫它查分，同時當公開評分網站的後端 → 團隊／企業版用 oomol-lab/open-connector 盤點該團隊實際連上的 SaaS／MCP 端點，把公開目錄的評分套到私有清單做持續稽核與告警。與 P017（給 AI 的 CVE／紅隊知識庫）定位不同：本案稽核的是『MCP 工具本身的供應鏈可信度』，賣點是安裝前的把關與持續監控。

**Difficulty**：medium · **Effort**：估 2–3 週做出能掃 servers 目錄並出信任分數的網站 MVP：mcptrustchecker 掃描管線＋分數計算約 1 週，python-sdk 包成 MCP 工具與網站後端約 1 週，公開目錄前端與私有清單稽核約 1 週。難點在掃描規則的準確度與誤報控制、持續跟上目錄更新，以及評分標準要能服眾（可解釋、可申訴）。

## Open-source parts

- [illiahaidar/mcptrustchecker](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/illiahaidar-mcptrustchecker/) — Security scanner for MCP (Model Context Protocol) servers — reads the real published npm/PyPI source, not jus…
- [modelcontextprotocol/servers](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/modelcontextprotocol-servers/) — Model Context Protocol Servers
- [modelcontextprotocol/python-sdk](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/modelcontextprotocol-python-sdk/) — The official Python SDK for Model Context Protocol servers and clients
- [oomol-lab/open-connector](https://cenxialiu7-cloud.github.io/ai-oss-daily/en/p/oomol-lab-open-connector/) — Open-source auth gateway connecting 1000+ SaaS providers to AI agents through SDK, CLI, MCP, HTTP, and OpenAP…
